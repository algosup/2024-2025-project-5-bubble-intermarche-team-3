# Test Plan for team 3 bubble web app project

## 1. Introduction

### Purpose
The primary objective of this document is to outline the various testing strategies and ensure that everyone understands the structure of quality assurance before the final version of the web app is released to users.

### Scope
This section clearly defines what will and will not be tested. 

1. **In-Scope:**
   - Wine and cheese suggestion algorithm
   - Meal selection interface
   - Search and filter functionality
   - Navigation and user flow
   - Mobile web responsiveness
   - User Interface
   - Wine and cheese selection interface
   - Language responsiveness
   - Cross-browser compatibility

2.  **Out-of-Scope:**
      - Third-party integrations
      - Backend database operation
      - Server-side performance
      - External API integrations
      - Desktop application
      
### Objectives

The testing process ensures that the web app is outlined clearly by the client's requirements. Ensuring that unnecessary information is removed, only relevant and important functionalities are implemented.

1. **Quality Assurance:**
   - Ensure 100% of critical functionalities work as per client requirements
   - Achieve zero critical defects in the production environment

2. **User Experience:**
   - Verify that the web app is intuitive for tourist users with a minimal learning curve
   - Ensure all user interactions have response times under 2 seconds
   - Validate that the wine and cheese suggestions are accurate and relevant

3. **Functionality:**
   - Test and verify all core features, including:
     * Meal selection interface
     * Wine and cheese suggestion algorithm
     * Search and filter functionality
     * Navigation system
     * Functional QR code scanning
   - Ensure all features work seamlessly across different mobile browsers

4. **Performance:**
   - Verify web app loads within 3-5 seconds on standard mobile networks
   - Ensure smooth operation with minimal lag during user interactions
   - Validate web app performance across different screen sizes and orientations
   - Test performance across different mobile browsers

5. **Compliance:**
   - Ensure the web app meets all specified language requirements
   - Verify compliance with web app best practices
   - Validate that all content is appropriate for the target audience
   - Ensure cross-browser compatibility

6. **Documentation:**
   - Maintain comprehensive test documentation
   - Track and report all defects with clear reproduction steps
   - Provide regular testing status updates.

## 2. Test Items

### Features to be Tested

1. **Wine and Cheese Suggestion Algorithm**
   - Wine pairing logic with different meal types
   - Cheese pairing logic with different meal types
   - Wine and cheese pairing logic with different meal types
   - Suggestion accuracy and relevance
   - Filtering options for preferences
   - Wine, cheese, and meal suggestions categorized by country specialties

2. **Meal Selection Interface**
   - Meal category selection
   - Meal type input
   - Meal suggestion
   - Clear images for meals

3. **Wine and cheese suggestion Interface:**
   - Categorised based on country specialities.
   - Clear images for wine and cheese.
   - Smooth Scrolling effect.
   - Favorite button display
   - Detailed information on each product

4. **Favorite Interface:**
   - Wine or cheese selected
   - Wine and cheese selected

5. **Search and Filter Functionality**
   - Search by wine type
   - Search by cheese type
   - Filter by price range
   - Filter wine by alcoholic or
   - Sort options(Ascending or descending order)

6. **Navigation and User Flow**
   - Home screen navigation
   - Menu navigation
   - Back button functionality
   - Screen transitions
   - Error handling
   - Loading states
   - Favorite button functionality
   - QR code functionality

7. **Browser Compatibility and Features**
   - Cross-browser compatibility testing
     * Safari on iOS
     * Chrome on Android
     * Firefox on Android
     * Chrome on iOS
     * Brave for Android

8. **Mobile Web Responsiveness**
   - Screen size adaptation
   - Touch interface
   - Gesture controls
   - Orientation changes
   - Responsive design elements

9. **User Interface**
   - Button functionality
   - Form validation
   - Error messages
   - Success notifications
   - Loading indicators
   - Color contrast
   - Font readability



### Features Not to be Tested

1. **Backend Operations**
   - Database operations
   - Server-side processing
   - API integrations
   - Data storage mechanisms

2. **External Systems**
   - Third-party services
   - External APIs
   - Authentication services

3. **Performance Metrics**
   - Server response time
   - Database query performance
   - Network latency
   - Load balancing

## 3. Testing Strategy

### Types of Testing
  
  1. **Functional Testing**
      - Testing if the app works as intended
         * Wine and cheese suggestion algorithm
         * Meal selection interface
         * Search and filter functionality
         * Navigation system
         * QR code scanning

   2. **Usability Testing**
      - Testing how user-friendly the app is
         * Ease of finding wine/cheese suggestions
         * Clarity of the meal selection process
         * Intuitiveness of navigation
         * Readability of information
         * Easy user experience

   3. **Performance Testing**
      - Testing app speed and responsiveness
         * App loading time
         * Search response time
         * Image loading speed
         * Smooth scrolling
         * Transition animations

   4. **Compatibility Testing**
      - Testing across different devices
         * Different mobile devices
         * Different screen sizes
         * Different operating systems
         * Different browsers' compatibility.

   5. **Regression Testing**
      - Testing if new changes break existing features
         * Re-testing after updates
         * Verifying existing features
         * Checking for new bugs

### Test Levels

  1. **Unit Testing**
      - Testing individual components
         * Wine suggestion algorithm
         * Cheese pairing logic
         * Search functionality
         * Filter mechanisms

   2. **Integration Testing**
      - Testing how components work together
         * Wine and meal pairing
         * Cheese and meal pairing
         * Search and filter integration
         * Navigation flow

   3. **System Testing**
      - Testing the entire app
         * End-to-end user flows
         * Complete feature testing
         * System performance
         * Overall functionality

   4. **User Acceptance Testing (UAT)**
      - Testing with actual users
         * Real-world scenarios
         * User feedback collection
         * Usability assessment

## 4. Test Environment

### Hardware & Software Requirements

   | Device Type | Browser | OS Version | Screen Size | Priority |
   |-------------|---------|------------|-------------|----------|
   | iPhone      | Safari  | iOS 15+    | Various     | High     |
   | Android     | Chrome  | 11+        | Various     | High     |
   | iPhone      | Chrome  | iOS 15+    | Various     | High     |
   | Android     | Firefox | 11+        | Various     | Medium   |
   | iPad        | Safari  | iPadOS 14+ | Various     | Medium   |
   | Tablets     | Chrome  | Android 13+| Various     | Medium   |
   | Android     | Brave   | 11+        | Various     | Medium   |

### Network Conditions
  - 4G/5G mobile networks
  - Wi-Fi connections
  - Low bandwidth conditions (2G/3G)
  - Network switching scenarios

## 5. Test Schedule

### Milestones

|       Milestone        |                  Description               | Target Date |         Deliverables        |
|------------------------|--------------------------------------------|-------------|-----------------------------|
| Test Environment Setup | Complete setup of all testing environments | Week 2 & 3  | Functional test environment |
| Unit Testing           | Testing of individual components           | Week 4      | Unit test results report    |
| Integration Testing    | Testing of component interactions          | Week 4 & 5  | Integration test results    |
| System Testing         | End-to-end testing of the application      | Week 5 & 6  | System test report          |
| User Testing           | Testing with actual users                  | Week 6 & 7  | UAT feedback report         |
| Test Plan Document     | Final review and approval                  | Week 7      | Deliver test plan document  |
| Bug Fixing             | Resolution of identified issues            | Week 7      | Bug fix report              |
| Final Testing          | Regression testing after fixes             | Week 8      | Final test report           |
| Production Release     | Deployment to production                   | Week 9      | Production release report   |  

### Testing Phases

|     Phase     | Duration  |                                  Activities                            |               Team Members               |       Deliverables   |
| ------------- |-----------|------------------------------------------------------------------------|------------------------------------------|-----------------------|
| Planning      | Week 2    | - Test plan creation<br>- Resource allocation<br>- Tool setup          | QA Team<br>Project Manager               | Resource allocation document(templates) |
| Preparation   | Week 2-3  | - Environment setup<br>- Test data preparation<br>- Test case creation | QA Team<br>                       | Test environment<br>Test cases<br>Test data |
| Execution     | Weeks 3-6 | - Unit testing<br>- Integration testing<br>- System testing<br>- UAT   | QA Team<br>Development Team<br>End Users | Test results<br>Bug reports<br>UAT feedback |
| Bug Fixing    | Week 7    | - Test plan<br>- Bug analysis<br>- Fix implementation<br>- Fix verification | Development Team<br>QA Team         | Test plan<br>Bug fix report<br>Verification results |
| Final Testing | Week 8    | - Regression testing<br>- Performance testing<br>   | QA Team<br>Development Team                | Final test report<br>Performance metrics |
| Release       | Week 9    | - Production deployment<br>- Post-deployment verification              | Development Team<br>QA Team                        | Deployment report<br>Production verification |

## 6. Test Deliverables

### Documentation Deliverables

| Document Type | Description | Purpose | Owner |
|---------------|-------------|---------|--------|
| [Test Plan](/Document/QualityAssurance/TestPlan/testPlan.md) | Complete test strategy and approach | Guide the testing process | QA Lead |
| [Test Cases](https://docs.google.com/spreadsheets/d/1FRRR-pqVDcpOtigRMEDFn3zRUcitUpOYr0SL9AV_RSU/edit?gid=517605026#gid=517605026) | Detailed test scenarios and steps | Execute testing activities | QA Team |
| [Requirement Traceability Matrix](https://docs.google.com/spreadsheets/d/1FRRR-pqVDcpOtigRMEDFn3zRUcitUpOYr0SL9AV_RSU/edit?gid=0#gid=0) | Maps requirements to test cases and tracks coverage | Ensure all requirements are tested and validated | QA Team |
| [Test Results](https://docs.google.com/spreadsheets/d/1FRRR-pqVDcpOtigRMEDFn3zRUcitUpOYr0SL9AV_RSU/edit?gid=559831432#gid=559831432) | Results of test execution | Track testing progress | QA Team |
| [Bug Reports](https://docs.google.com/spreadsheets/d/1FRRR-pqVDcpOtigRMEDFn3zRUcitUpOYr0SL9AV_RSU/edit?gid=1758071504#gid=1758071504) | Detailed defect documentation | Track and resolve issues | QA Team |


### Quality Metrics

| Metric | Description | Target | Frequency |
|--------|-------------|---------|-----------|
| Test Coverage | Percentage of requirements covered by tests | 100% | Weekly |
| Defect Density | Number of defects per feature | < 5 | Weekly |
| Test Pass Rate | Percentage of passed test cases | > 95% | Daily |



## 7. Roles and Responsibilities

### Team Members and Responsibilities

| Role              | Name                   | Responsibilities |
|-------------------|------------------------|-----------------|
| Quality Assurance | Tsangue Vivien Bistrel | - Create and maintain test plan<br>- Design test cases<br>- Execute test cases<br>- Report defects<br>- Track test progress<br>- Verify bug fixes<br>- Generate test reports<br>- Maintain RTM |
| Program Manager   | Camille GAYAT          | - Provide resources for testing<br>- Communicate with stakeholders<br>- Review test results<br>- Final approval for production release |
| Project Manager   | Léna DE GERMAIN        | - Schedule activities<br>- Coordinate team members<br>- Risk management<br>- Issue resolution<br>- Status reporting<br>- Ensure deadlines are met<br> |
| Technical Lead    | Julian REINE           | - Provide technical guidance<br>- Review test cases for technical accuracy<br>- Assist with complex test scenarios<br>- Help diagnose complex issues<br>- Perform technical reviews<br>- Support test environment setup<br> |
| Software Engineer | Guillaume DESPAUX      | - Fix reported defects<br>- Assist in test environment setup<br>- Provide application knowledge<br>- Support in test data creation<br>- Clarify technical questions<br>- Perform code reviews<br>- Implement feature changes |
| Technical Writer  | Lucas Aubard           | - Review test documentation<br>- Create user guides<br>- Review bug reports for clarity<br>|

### Responsibility Matrix

|           Activity       | QA   | Program Manager | Project Manager | Technical Lead | Software Engineer | Technical Writer |
|--------------------------|------|-----------------|-----------------|----------------|-------------------|------------------|
| Test Planning            | R/A  |         A       |        C        |        C       |          I        |         I        |
| Test Case Development    | R/A  |         I       |        I        |        C       |         I/S       |         I        |
| Test Execution           | R/A  |         I       |        I        |        S       |          S        |         I        |
| Defect Reporting         | R/A  |         I       |        I        |        C       |          S        |         I        |
| Test Environment Setup   | C/R  |         I       |        M        |        S       |         S/C       |         I        |
| Test Report Generation   | R    |         C       |        C        |        I       |          I        |         S        |
| Product Release Approval | C    |         R       |        C        |        C       |          C        |         I        |

**Legend:** R = Responsible, A = Approver, C = Consulted, S = Supports, I = Informed, M = Monitors,

## 8. Defect Management


### Defect Lifecycle

| Status       | Description |
|--------------|-------------|
| New          | Defect has been identified but not yet validated |
| Validated    | Defect has been confirmed and verified |
| Assigned     | Defect has been assigned to a developer for resolution |
| In Progress  | Developer is actively working on the defect |
| Fixed        | Developer has completed the fix |
| Verification | QA is verifying the fix |
| Closed       | Defect has been resolved and verified |
| Rejected     | Defect was determined not to be valid |
| Deferred     | Defect is valid but will be fixed in a future release |
| Reopened     | Defect was marked as fixed but failed verification |

### Severity Levels

| Severity      | Description                                  | Resolution Time |
|---------------|----------------------------------------------|-----------------|
| Critical (S1) | Prevents app usage or causes data loss       | 24 hours        |
| High (S2)     | Major functionality broken or unusable       | 48 hours        |
| Medium (S3)   | Feature partially working, workaround exists | 72 hours        |
| Low (S4)      | Minor issues, cosmetic problems              | Next release    |

### Priority Levels

| Priority | Description |
|----------|-------------|
| P1       | Must fix immediately |
| P2       | Fix as soon as possible |
| P3       | Fix when time permits |
| P4       | Fix if time allows |

### Defect Reporting Process

1. **Discovery**
   - Defect is discovered during testing
   - Screenshot/screencast captured if applicable

2. **Documentation**
   - Create new GitHub Issue
   - Assign appropriate severity and priority
   - Include detailed reproduction steps
   - Add relevant screenshots/evidence
   - Tag relevant team members

3. **Triage**
   - QA review reported defects
   - Validate defect and reproduction steps
   - Adjust severity/priority if needed
   - Assign to developer

4. **Resolution**
   - Developer investigates and fixes the defect
   - Documents the fix and its implications
   - Updates the issue with resolution details
   - Changes status to "Fixed"

5. **Verification**
   - QA verifies the fix using original test case
   - Performs regression testing around affected area
   - Updates status to "Closed" or "Reopened"
   - Documents verification results

## 9. Risks and Mitigation

### Risk Assessment Table

| Risk ID | Risk Description                | Probability| Impact | Risk Level | Mitigation Strategy |
|---------|---------------------------------|------------|--------|------------|---------------------|
| R1      | Inadequate testing time         | Medium     | High   | High       | - Prioritize critical features<br>- Focus on high-risk areas<br> |
| R2      | Unstable test environment       | Medium     | High   | High       | - Document environment setup<br>- Regular environment checks |
| R3      | Incomplete requirements         | High       | Medium | High       | - Regular requirement reviews<br>- Clarify ambiguous requirements<br>- Update RTM continuously |
| R4      | Device compatibility issues     | High       | Medium | High       | - Test on priority devices first<br>- Use device emulators/simulators<br>- Focus on most common devices |
| R5      | Browser compatibility issues    | High       | Medium | High       | - Test on priority browsers first<br>- Use browser developer tools<br>- Focus on most common browsers |
| R6      | Changes in requirements         | Medium     | Medium | Medium     | - Impact analysis<br>- Update test cases promptly |
| R7      | Team member unavailability      | Low        | Medium | Low        | - Cross-training team members<br>- Document testing procedures<br>- Maintain up-to-date documentation |
| R8      | Bubble platform limitations     | Medium     | High   | High       | - Research limitations early<br>- Plan workarounds<br>- Adjust test cases accordingly |
| R9      | Performance issues              | Medium     | High   | High       | - Early performance testing<br>- Optimize web app design<br>- Set realistic performance expectations |

### Risk Monitoring

1. Review identified risks
2. Assess effectiveness of mitigation strategies
3. Identify new risks
4. Update risk assessment
5. Highlight high-risk items
6. Track risk mitigation progress
7. Escalate unresolved risks
8. Document emergency procedures
9. Identify alternative solutions

## 10. Approval

### Test Plan Approval

By signing below, stakeholders acknowledge they have reviewed and approved this test plan for implementation.

| Role              | Name                   | Signature          | Date |
|-------------------|------------------------|--------------------|------|
| Quality Assurance | Tsangue Vivien Bistrel | _______TCVB_______ | __05__/__14__/__2025__ |
| Program Manager   | Camille GAYAT          | ________CG________ | __06__/__06__/__2025__ |
| Project Manager   | Léna DE GERMAIN        | ________LNG________ | __06__/__06__/__2025__ |
| Technical Lead    | Julian REINE           | ________JR________ | __06__/__06__/__2025__ |

### Revision History

| Version | Date       | Author                 | Description of Changes |
|---------|------------|------------------------|------------------------|
| 1.0     | 05/14/2025 | Tsangue Vivien Bistrel | Baseline version       |
| 1.1     | 05/19/2025 | Tsangue Vivien Bistrel | Ameliorated version    |
| 1.2     | 06/06/2025 | Tsangue Vivien Bistrel | Latest version         | 