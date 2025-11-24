# SmartUI SDK Sample for Selenium Java (TestNG)

Welcome to the SmartUI SDK sample for Selenium Java with TestNG. This repository demonstrates how to integrate SmartUI visual regression testing with Selenium Java using TestNG framework.

## Repository Structure

```
smartui-java-testng-sample/
├── src/
│   └── test/
│       └── java/
│           └── com/
│               └── lambdatest/
│                   └── sdk/
│                       ├── SmartUISDKCloud.java    # Cloud test
│                       └── SmartUISDKLocal.java    # Local test
├── sdk-cloud.xml                                    # TestNG suite for Cloud
├── sdk-local.xml                                    # TestNG suite for Local
├── pom.xml                                          # Maven dependencies
└── smartui-web.json                                # SmartUI config (create with npx smartui config:create)
```

## 1. Prerequisites and Environment Setup

### Prerequisites

- Java JDK 1.6 or higher (latest version recommended)
- Maven 3.6 or higher
- Node.js (for SmartUI CLI)
- LambdaTest account credentials (for Cloud tests)
- Chrome browser (for Local tests)

### Environment Setup

**For Cloud:**
```bash
export LT_USERNAME='your_username'
export LT_ACCESS_KEY='your_access_key'
export PROJECT_TOKEN='your_project_token'
```

**For Local:**
```bash
export PROJECT_TOKEN='your_project_token'
```

## 2. Initial Setup and Dependencies

### Clone the Repository

```bash
git clone https://github.com/LambdaTest/smartui-java-testng-sample
cd smartui-java-testng-sample
```

### Install Dependencies

The repository already includes the required dependencies in `pom.xml`. Build the project to download dependencies:

```bash
mvn clean compile
```

**Dependencies included:**
- `io.github.lambdatest:lambdatest-java-sdk` - SmartUI SDK for Selenium Java
- `org.testng:testng` - TestNG testing framework
- `org.seleniumhq.selenium:selenium-java` - Selenium WebDriver

### Install SmartUI CLI

```bash
npm i @lambdatest/smartui-cli
```

### Create SmartUI Configuration

```bash
npx smartui config:create smartui-web.json
```

## 3. Steps to Integrate Screenshot Commands into Codebase

The SmartUI screenshot function is already implemented in the repository.

**Cloud Test** (`src/test/java/com/lambdatest/sdk/SmartUISDKCloud.java`):
```java
driver.get("https://www.lambdatest.com");
SmartUISnapshot.smartuiSnapshot(driver, "screenshot");
```

**Local Test** (`src/test/java/com/lambdatest/sdk/SmartUISDKLocal.java`):
```java
driver.get("https://www.lambdatest.com");
SmartUISnapshot.smartuiSnapshot(driver, "screenshot");
```

**Note**: The code is already configured and ready to use. You can modify the URL and screenshot name if needed.

## 4. Execution and Commands

### Local Execution

```bash
npx smartui exec -- mvn test -D suite=sdk-local.xml
```

### Cloud Execution

```bash
npx smartui exec -- mvn test -D suite=sdk-cloud.xml
```

## Test Files

### Cloud Test (`SmartUISDKCloud.java`)

- Connects to LambdaTest Cloud using Selenium Remote WebDriver
- Reads credentials from environment variables (`LT_USERNAME`, `LT_ACCESS_KEY`)
- Uses TestNG framework
- Takes screenshot with name: `screenshot`

### Local Test (`SmartUISDKLocal.java`)

- Runs Selenium locally using Chrome
- Requires Chrome browser installed
- Uses TestNG framework
- Takes screenshot with name: `screenshot`

## Configuration

### Maven Config (`pom.xml`)

The Maven configuration file includes all necessary dependencies for SmartUI and TestNG.

### TestNG Suites

- `sdk-cloud.xml` - TestNG suite for Cloud execution
- `sdk-local.xml` - TestNG suite for Local execution

### SmartUI Config (`smartui-web.json`)

Create the SmartUI configuration file using:
```bash
npx smartui config:create smartui-web.json
```

## Parallel Testing

To run parallel tests using TestNG:

```bash
mvn test -D suite=smartui-parallel.xml
```

## Testing Locally Hosted Projects

You can test locally hosted or privately hosted projects with LambdaTest Selenium grid using LambdaTest Tunnel. Refer to the [LambdaTest Tunnel documentation](https://www.lambdatest.com/support/docs/testing-locally-hosted-pages/) for more information.

## View Results

After running the tests, visit your SmartUI project dashboard to view the captured screenshots and compare them with baseline builds.

## More Information

For detailed onboarding instructions, see the [SmartUI Selenium Java Onboarding Guide](https://www.lambdatest.com/support/docs/smartui-onboarding-selenium-java/).

## Resources

- [LambdaTest Documentation](https://www.lambdatest.com/support/docs/)
- [LambdaTest Blog](https://www.lambdatest.com/blog/)
- [LambdaTest Learning Hub](https://www.lambdatest.com/learning-hub/)
