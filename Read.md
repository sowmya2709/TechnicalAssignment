Overview

The Test framework is developed in Selenium Webdriver, TestNG, Java and MAVEN. 
The focus of the simple yet robust framework is to highlight the framework features and its effectiveness rather than test scenario coverage.
The framework is modularized for reusability and is robust enough to be enhanced to include the Page Object model in the future.

Scenarios

I have automated following scenarios for demo purpose, however, we could automate more Banks Feed scenarios

    1) Created "ANZ (NZ)" Bank Accounts for different Account Types
    2) Tried creating a duplicate account

Other possible scenarios - Add Multiple accounts, Upload and Download files, Get Bank Feeds by linked bank account or uploading bank feeds etc

The root folder has the tests to execute the BankFeeds feature and here are the details of the folder structure

    "src/test/java/commonFunction"- has all the common functionalities of the website such as LoginMethods.java(login, logout),
                                    BankFeedsMethod.java(all functions for BankFeeds scenarios)
    "src/test/java/helpers"- this has all the non-functional helper classes such as listeners. It can also have different Json helpers,
                             Rest helpers etc if used for API testing 
    "src/test/java/testData- all the date provider classes can be stored here and tests can reference these using TestNG DataProvider class
    "src/test/java/resources"- browser drivers can be added here. I have used Chrome browser and the IDE can be found here
    "src/test/java/xeroTest" - the Bank Feed Application tests can be found here


Note: 
    The tests can be executed on a windows machine without and code changes. 
    To execute on MAC os you will have to change the chromebrowser IDE location path in "src/test/java/xeroTest/TestBase.java" file
    
Steps to execute the automation tests

    1) Please make sure JAVA_HOME, MAVEN_HOME is set correctly on a window PC or laptop
    2) Clone the maven project to a local folder and import it to IDE by specifying profile name
    3) Ensure “mvn clean install” runs successfully and all the dependencies are resolved. Make sure your organisation firewall doesn't block Maven repo download
    4) On command prompt navigate to the project root folder
    5) Run “mvn test”
    6) The test results can be found in the following path under root folder after execution “/target/surefire-reports”
    7) You can find the execution report under root folder in file “/target/surefire-reports/emailable-report”

How the framework can be enhanced?

    - Page Object Model can be created to record all the object of a page and different actions that can be performed and these objects can be reused
    - The automation suite can be integrated with Jenkins to run in different test environments.
    - Custom Annotations can be used to configure tests as Functional, Regression, Smoke etc and only those tests can be run locally or in Jenkins
    - If more behaviour driven model is preferred then the framework can be used with Cucumber to write behaviour drive tests
    - The same automation suite can have API tests with REST Assured Framework by adding rest helper classes etc
    - "*.properties" file can used to pass application URL, login credentials or other environment specific test data. 
        Currently its configured to run in Xero production URL for my dummy credentials(hard-coded)

Recommendation

    - Some of the pages and objects take more time to load, using Cypress can be another option to manage this limitation of the application.
    - Using "data-automationid" consistently for all objects. "Not all objects have "data-automationid" and in some cases, even this id wasn't consistently recognised.

Advantanges of this framework

    - As its java based test, it allows us to add BDD Framework, Rest Assured Test Framework to the same test suite
    - It can be kept as simple and can be enhanced to make as sophisticated as possible

