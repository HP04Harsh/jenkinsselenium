<img width="1024" height="572" alt="image" src="https://github.com/user-attachments/assets/22fadf54-d19f-4d6e-a8f7-493c1d868202" />


Project Description
-------------------

This project serves as a robust template for integrating **Selenium WebDriver** automation into a **Jenkins CI/CD pipeline**. It leverages **Maven** as the build tool to manage dependencies and execute test suites automatically upon code commits. The primary goal is to demonstrate a seamless "Commit-to-Test" workflow, ensuring that web application changes are validated through automated browser testing before moving further in the lifecycle.

Architecture Overview
---------------------

The project follows a standard DevOps pipeline where the source code is hosted on GitHub. Jenkins acts as the orchestrator, pulling the latest code, compiling it via Maven, executing the application, and finally running Selenium scripts to validate UI functionality.

Tech Stack
----------

**CategoryTechnologyPurposeLanguage**[Java](https://github.com/HP04Harsh/jenkinsselenium/search?l=java)Core programming language for application and tests.**Build Tool**[Maven](https://github.com/HP04Harsh/jenkinsselenium/blob/main/pom.xml)Dependency management and build automation.**Automation**[Selenium WebDriver](https://github.com/HP04Harsh/jenkinsselenium/blob/main/pom.xml)Web browser automation and UI testing.**CI/CD**[Jenkins](https://github.com/HP04Harsh/jenkinsselenium)Continuous Integration server for pipeline execution.**SCM**[GitHub](https://github.com/HP04Harsh/jenkinsselenium)Version control and source code management.**Testing Framework**TestNG / JUnitTest execution and assertion logic.


## Project Structure
```text
jenkinsselenium/
├── src/
│   ├── main/java/        # Application source code
│   └── test/java/        # Selenium automation test scripts
├── pom.xml               # Maven configuration (dependencies & plugins)
└── README.md             # Project documentation
```
Prerequisites
-------------

Before running this project, ensure you have the following installed:

*   **Java JDK 11 or higher**
    
*   **Apache Maven 3.6+**
    
*   **Jenkins Server** (Local or Cloud)
    
*   **Google Chrome** & **ChromeDriver** (matching versions)
    
*   **Git**
    

Installation & Setup
--------------------

1.  git clone https://github.com/HP04Harsh/jenkinsselenium.git
2.  cd jenkinsselenium
3.  mvn clean install
    

CI/CD Pipeline Flow (Jenkins)
-----------------------------

### 1\. GitHub Integration

The repository is connected to Jenkins via a Webhook. Any git push to the main branch triggers a build.

### 2\. Maven Build Lifecycle

Jenkins executes the following lifecycle phases:

*   clean: Removes the target folder.
    
*   compile: Compiles the source code.
    
*   test: Executes the Selenium tests defined in the test directory.
    

### 3\. Selenium Automation Testing

Tests are configured to run in **headless mode** (recommended for Jenkins) or via a virtual display. The pom.xml manages the specific browser drivers needed for execution.

How to Run
----------

### Local Execution

To run the tests manually on your machine:
mvn test

### Jenkins Execution

1.  Create a new **Freestyle Project** or **Pipeline**.
    
2.  Under **Source Code Management**, point to this [GitHub URL](https://github.com/HP04Harsh/jenkinsselenium).
    
3.  Add a **Build Step**: Invoke top-level Maven targets.
    
4.  Goals: clean install test.
    
5.  (Optional) Configure **Post-build Actions** to publish JUnit test result reports.
    

Troubleshooting
---------------

*   **Driver Mismatch:** Ensure your chromedriver version matches your installed Chrome browser version.
    
*   **Headless Mode:** If running on a Linux Jenkins node without a GUI, ensure Selenium is configured for --headless execution.
    
*   **Environment Variables:** Ensure JAVA\_HOME and MAVEN\_HOME are correctly set in Jenkins Global Tool Configuration.
    

Future Improvements
-------------------

*   \[ \] Integration with Docker for containerized test execution.
    
*   \[ \] Implementation of Page Object Model (POM) for better test maintainability.
    
*   \[ \] Adding Extent Reports for advanced visual reporting.
    
*   \[ \] Parallel test execution using TestNG.
    

Contributors
------------

*   [**CloudFolks HUB**](https://github.com/CloudFolksHUB)
    
*   [**Harsh Pardhi**](https://github.com/HP04Harsh)
