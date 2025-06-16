# Road Map Of The Bubble Project

## Document Information

- **Author**: [Guillaume Despaux](https://github.com/guillaumedespaux)
- Last Updated: 06/16/2024
- **Version**: 1.0
- Website: [Bubble Project](https://project5-team3.bubbleapps.io/version-test)
- Website Debug: [Bubble Project Debug Mode](https://project5-team3.bubbleapps.io/version-test?debug_mode=true)
  
## Table of Contents

- [Road Map Of The Bubble Project](#road-map-of-the-bubble-project)
  - [Document Information](#document-information)
  - [Table of Contents](#table-of-contents)
  - [Project Overview](#project-overview)
  - [Key Components](#key-components)
  - [Pairing Systems](#pairing-systems)
    - [Meal Type / Wines Pairing](#meal-type--wines-pairing)
    - [Cheese / Wines Pairing](#cheese--wines-pairing)
  - [Bubble Project Overview](#bubble-project-overview)
    - [User Connection](#user-connection)
    - [Check Favorite Items \& Display Them](#check-favorite-items--display-them)
    - [ScannerPage](#scannerpage)
    - [Current Item Page + Pairing System](#current-item-page--pairing-system)
    - [Add Favorite Item](#add-favorite-item)
    - [Remove Favorite Item](#remove-favorite-item)
    - [Change Language](#change-language)
    - [Search Per Country](#search-per-country)
  - [States Management](#states-management)
    - [Home Page](#home-page)
    - [Search Page](#search-page)
      - [Group SeachForSingleElement](#group-seachforsingleelement)
      - [Group SeachForList Of Dishes (Country)](#group-seachforlist-of-dishes-country)
      - [Group SeachForList From SeachBar + Filters](#group-seachforlist-from-seachbar--filters)
    - [Favorite Page](#favorite-page)
    - [Scanner Page](#scanner-page)

## Project Overview

This document will provide a high-level overview of the logic and structure of the Bubble project highlighting the key components, their interactions, and the states.

## Key Components

- **Single Page Use**: This Bubble project is designed to be a single-page to prevent low Internet connection and/or no Internet connection from the final user.
- **Firebase Database**: Since the Bubble project in fremium version is limited to 200 "Things" in the database the need to use Firebase as a database is required to outpass this limitation.
- **Bar Code Scanner**: To help the user to find products the Bubble project will use a bar code scanner.
- **Local Storage**: To store information locally since the Bubble doesn't plan to use account to retrieve data we will use the local storage of the browser to store data:
  - **Language**: The language that the user has selected.
  - **Favorite Items**: the items that the user has selected as favorite.
- **Paring System (Cheese & Wine)**: The project will include a pairing system to suggest cheese and wine combinations based on meal types or specific cheese/wine selections.

## Pairing Systems

### Meal Type / Wines Pairing

![Meal Type / Wines Pairing](./img/meal-wine.png)
>[!NOTE]
> The pairing system will be based on the image above.
---
>[!IMPORTANT]
> Each dots corresponds to a score between type of meal and wine:
>
> - No Dot: 0
> - Small Dot: 1
> - Big Dot: 2

### Cheese / Wines Pairing

![Cheese / Wines Pairing](./img/whiteRedWineAndCheese.png)
>[!NOTE]
> The pairing system will be based on the image above.
---
>[!IMPORTANT]
> Each corelation corresponds to a fixed score of 1 between cheese and wine.

## Bubble Project Overview

### User Connection

```mermaid
sequenceDiagram
    participant Bob as User
    participant URL as URL
    participant LoadPage as Load Page
    participant Firebase as Firebase Database
    participant HomePage as Home Page

    Bob ->> URL: Open Bubble Project URL
    URL ->> LoadPage: Load Bubble Project Page
    LoadPage ->> LoadPage: Check Local Storage For Language + Favorite Items
    LoadPage -->> Firebase: Start Fetching Data From Firebase
    Firebase -->> LoadPage: Return Data From Firebase
    LoadPage ->> HomePage: Display Home Page With Data (Dishes)


```

### Check Favorite Items & Display Them

```mermaid
sequenceDiagram
    participant HomePage as Home Page
    participant FavoriteItems as Favorite Items
    participant DataProcessing as Data Processing
    participant SearchCurrent as Search Current

    HomePage ->> FavoriteItems: Check Local Storage For Favorite Items
    FavoriteItems -->> DataProcessing: Get Each ID's to find the current items
    DataProcessing ->> FavoriteItems: Return Favorite Items
    FavoriteItems ->> FavoriteItems: Display Favorite Items
    FavoriteItems ->> FavoriteItems: Click on Favorite Item
    FavoriteItems -->> DataProcessing: Check 3 Data Processing(dish, wine,cheese)
    DataProcessing ->> SearchCurrent: Search Current Item Using the current Data Processing when is no empty
```

### ScannerPage

```mermaid
sequenceDiagram
    participant HomePage as Home Page
    participant Scanner as Scanner
    participant DataProcessing as Data Processing
    participant OtherPage as Other Page
    participant SearchCurrent as Search Current

    HomePage ->> Scanner: Click on Scanner Button
    Scanner -->> Scanner: Open Scanner
    Scanner ->> OtherPage: Close Scanner Page
    Scanner -->> Scanner: Scan Bar Code
    Scanner -->> DataProcessing: Send Bar Code to Data Processing
    Scanner ->> DataProcessing: Check collection of the bar code when valid
    DataProcessing ->> SearchCurrent: Search Current Item Using the Bar Code
```

### Current Item Page + Pairing System

```mermaid
sequenceDiagram
    participant SearchCurrent as Search Current
    participant CurrentItem as Current Item
    participant PairingSystem as Pairing System
    participant DataProcessing as Data Processing

    SearchCurrent ->> CurrentItem: Display Current Item
    CurrentItem ->> PairingSystem: Check If Pairing System is Available
    PairingSystem -->> DataProcessing: Get Pairing System Data
    DataProcessing -->> PairingSystem: Return Pairing System Data
    PairingSystem ->> CurrentItem: Display Pairing System Data
```

### Add Favorite Item

```mermaid
sequenceDiagram
    participant CurrentItem as Current Item
    participant FavoriteItems as Favorite Items
    participant DataProcessing as Data Processing

    CurrentItem ->> FavoriteItems: Click on Add Favorite Item Button
    FavoriteItems -->> DataProcessing: Check If Item Already Exists in Local Storage
    DataProcessing -->> FavoriteItems: Return Result
    FavoriteItems ->> FavoriteItems: Add Item to Local Storage if not exists
    FavoriteItems ->> CurrentItem: Display New Icon
```

### Remove Favorite Item

```mermaid
sequenceDiagram
    participant CurrentItem as Current Item
    participant FavoriteItems as Favorite Items
    participant DataProcessing as Data Processing

    CurrentItem ->> FavoriteItems: Click on Remove Favorite Item Button
    FavoriteItems -->> DataProcessing: Check If Item Exists in Local Storage
    DataProcessing -->> FavoriteItems: Return Result
    FavoriteItems ->> FavoriteItems: Remove Item from Local Storage if exists
    FavoriteItems ->> CurrentItem: Display Old Icon
```

### Change Language

```mermaid
sequenceDiagram
    participant LoadPage as Load Page
    participant HomePage as Home Page
    participant Language as Language
    participant LocalStorage as Local Storage

    HomePage ->> Language: Click on Change Language Button
    Language -->> LocalStorage: Check Local Storage For Current Language
    LocalStorage -->> Language: Return Current Language
    Language ->> Language: Display Available Languages
    HomePage -->> LocalStorage: Save New Language in Local Storage
    Language ->> LoadPage: Change Language
    LoadPage ->> HomePage: Reload Home Page With New Language
```

### Search Per Country

```mermaid
sequenceDiagram
    participant HomePage as Home Page
    participant SearchPC as Search Per Country
    participant DataProcessing as Data Processing

    HomePage ->> Search: Click on Country
    Search -->> Search: Open Search Page Per Country
    Search ->> Search: Enter Country Name
    Search -->> DataProcessing: Send Country Name to Data Processing
    DataProcessing ->> SearchPC: Display Items Per Country
```

## States Management

Since this Bubble project is a single-page application all the name mentioned after are components that are used to create the visual part and store the states of the application.

---

### Home Page

- **index**:
  - currentCollection: text to keep track the current collection of items
  - currentSearch: text to keep track of the current ID of the item
  - currentLanguage: text to keep track of the current language (Default is English)
  - scanner: boolean to keep track if the scanner is open or not

- **Filters Options**:
  - maxPrice: number to keep track of the maximum price of the item (default is 100)
  - minPrice: number to keep track of the minimum price of the item (default is 1)
  - Type: list of texts to keep track of the types of research for the filter

- **ListOfLanguages**:
  - isOpen: boolean to keep track if the list of languages is open or not (default is no)

- **NavigationButtons**:
  - index: text to keep track of the current index of the navigation buttons (default is loading)

---

### Search Page

#### Group SeachForSingleElement

- **SearchPage**:
  - searchBar: boolean to keep track if the research have been done through the search bar or not (default is no)

- **FirestoreDataProcessor wine**:
  - bold_redName: text to keep track of the bold red wine ID
  - bold_redValue: number to keep track of the current bold red wine value for pairing
  - medium_redName: text to keep track of the bold white wine ID
  - medium_redValue: number to keep track of the current medium red wine value for pairing
  - light_redName: text to keep track of the light red wine ID
  - light_redValue: number to keep track of the current light red wine value for pairing
  - rich_whiteName: text to keep track of the rich white wine ID
  - rich_whiteValue: number to keep track of the current rich white wine value for pairing
  - dessertName: text to keep track of the dessert wine ID
  - dessertValue: number to keep track of the current dessert wine value for pairing
  - light_whiteName: text to keep track of the light white wine ID
  - light_whiteValue: number to keep track of the current light white wine value for pairing
  - sparklingName: text to keep track of the sparkling wine ID
  - sparklingValue: number to keep track of the current sparkling wine value for pairing
  - sweet_whiteName: text to keep track of the sweet wine ID
  - sweet_whiteValue: number to keep track of the current sweet wine value for pairing
  - sortingList: list of texts to keep track of the sorting list of wines using map:json format.

- **FirestoreDataProcessor cheese**:
  - blueVeinedName: text to keep track of the blue-veined cheese ID
  - blueVeinedValue: number to keep track of the current blue-veined cheese value for pairing
  - cookedPressedName: text to keep track of the cooked pressed cheese ID
  - cookedPressedValue: number to keep track of the current cooked pressed cheese value for pairing
  - freshName: text to keep track of the fresh cheese ID
  - freshValue: number to keep track of the current fresh cheese value for pairing
  - goatName: text to keep track of the goat cheese ID
  - goatValue: number to keep track of the current goat cheese value for pairing
  - uncookedPressedName: text to keep track of the uncooked pressed cheese ID
  - uncookedPressedValue: number to keep track of the current uncooked pressed cheese value for pairing
  - processedName: text to keep track of the processed cheese ID
  - processedValue: number to keep track of the current processed cheese value for pairing
  - softBloomyName: text to keep track of the soft bloomy cheese ID
  - softBloomyValue: number to keep track of the current soft bloomy cheese value for pairing
  - softWashedName: text to keep track of the soft washed cheese ID
  - softWashedValue: number to keep track of the current soft washed cheese value for pairing
  - sortingList: list of texts to keep track of the sorting list of cheeses using map:json format.
  - bestChoice: First item of the sorting list split by(,):last item of sortingList.

- **FirestoreDataProcessor dish**:
  - sortingList: list of texts to keep track of the sorting list of dishes using map:json format.

- **Group Image+Infos Dish**:
  - currentFoodSubCatCount: number to keep track of the current food sub-category count in the dish
  - currentPairingCount: number to keep track of the current pairing count in the dish

>[!NOTE]
> This count down is used for each iteration to count the right amount of wineStyle matching with the dish.

#### Group SeachForList Of Dishes (Country)

- **Group SeachForList Of Dishes (Country)**:
  - currentCountry: text to keep track of the current country selected

#### Group SeachForList From SeachBar + Filters

- **Group SeachForList From SeachBar + Filters**:
  - currentSearch: text to keep track of the current search in the search bar

---

### Favorite Page

- **Group ContentPage**:
  - favoriteList: list of texts to keep track of the favorite items in the local storage

---

### Scanner Page

- **Group DetectedItem**:
  - scannerResult: text to keep track of the scanned item result
