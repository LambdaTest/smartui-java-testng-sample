# Run SmartUI Tests With TestNG On LambdaTest

![image](https://user-images.githubusercontent.com/70570645/171934563-4806efd2-1154-494c-a01d-1def95657383.png)

<p align="center">
  <a href="https://www.lambdatest.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium" target="_bank">Blog</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium" target="_bank">Docs</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium" target="_bank">Learning Hub</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/newsletter/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium" target="_bank">Newsletter</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/certification/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium" target="_bank">Certifications</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.youtube.com/c/LambdaTest" target="_bank">YouTube</a>
</p>
&emsp;
&emsp;
&emsp;

_Learn how to use TestNG framework to configure and run your Java automation testing scripts on the LambdaTest platform_

[<img height="58" width="200" src="https://user-images.githubusercontent.com/70570645/171866795-52c11b49-0728-4229-b073-4b704209ddde.png">](https://accounts.lambdatest.com/register?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)

## Table Of Contents

- [Pre-requisites](#pre-requisites)
- [Run Your First Test](#run-your-first-test)
- [Parallel Testing With TestNG](#executing-parallel-tests-using-testng)
- [Local Testing With TestNG](#testing-locally-hosted-or-privately-hosted-projects)

## Pre-requisites

Before you can start performing Java automation testing with Selenium, you would need to:

- Install the latest **Java development environment** i.e. **JDK 1.6** or higher. We recommend using the latest version.

- Download the latest **Selenium Client** and its **WebDriver bindings** from the [official website](https://www.selenium.dev/downloads/). Latest versions of Selenium Client and WebDriver are ideal for running your automation script on LambdaTest Selenium cloud grid.

- Install **Maven** which supports **JUnit** framework out of the box. **Maven** can be downloaded and installed following the steps from [the official website](https://maven.apache.org/). Maven can also be installed easily on **Linux/MacOS** using [Homebrew](https://brew.sh/) package manager.

### Cloning Repo And Installing Dependencies

**Step 1:** Clone the LambdaTest’s Java-TestNG-Selenium repository and navigate to the code directory as shown below:

```bash
git clone https://github.com/LambdaTest/smartui-java-testng-sample
cd smartui-java-testng-sample
```

You can also run the command below to check for outdated dependencies.

```bash
mvn clean compile
```

### Setting Up Your Authentication

Make sure you have your LambdaTest credentials with you to run test automation scripts. You can get these credentials from the [LambdaTest Automation Dashboard](https://automation.lambdatest.com/build?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium) or by your [LambdaTest Profile](https://accounts.lambdatest.com/login?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium).

**Step 2:** Set LambdaTest **Username** and **Access Key** in environment variables.

- For **Linux/macOS**:

  ```bash
  export PROJECT_TOKEN="xxxxx#java-sdk-testing"
  export LT_USERNAME="YOUR_USERNAME"
  export LT_ACCESS_KEY="YOUR ACCESS KEY"
  ```

  - For **Windows**:

  ```bash
  set PROJECT_TOKEN="xxxxx#java-sdk-testing"
  set LT_USERNAME="YOUR_USERNAME"
  set LT_ACCESS_KEY="YOUR ACCESS KEY"
  ```

### Execute SmartUI Java Tests using smartui-cli


#### Install the smartui-cli dependencies
```bash
npm i @lambdatest/smartui-cli
```

#### Create and Configure SmartUI Config
```bash
npx smartui config:create smartui-web.json
```

#### Use Local Hub
```bash
npx smartui exec -- mvn test -D suite=sdk-local.xml
```

#### Use Lambdatest Cloud Hub
```bash
npx smartui exec -- mvn test -D suite=sdk-cloud.xml
```

Your test results would be displayed on the test console (or command-line interface if you are using terminal/cmd) and on SmartUI dashboard.

### Executing SmartUI Test on Lambdatest Hub without smartui-cli

The tests can be executed in the terminal using the following command.

```bash
mvn test -D suite=smartui.xml
```

Your test results would be displayed on the test console (or command-line interface if you are using terminal/cmd) and on LambdaTest automation dashboard.

## Run Parallel SmartUI Tests Using TestNG

### Executing Parallel Tests Using TestNG

To run parallel tests using **TestNG**, we would have to execute the below commands in the terminal:
```bash
mvn test -D suite=smartui-parallel.xml
```

### Execute SmartUI Real Device Tests

The tests can be executed in the terminal using the following command.

```bash
mvn test -D suite=smartui-mobile.xml
```

## Testing Locally Hosted Or Privately Hosted Projects

You can test your locally hosted or privately hosted projects with LambdaTest Selenium grid using LambdaTest Tunnel. All you would have to do is set up an SSH tunnel using tunnel and pass toggle `tunnel = True` via desired capabilities. LambdaTest Tunnel establishes a secure SSH protocol based tunnel that allows you in testing your locally hosted or privately hosted pages, even before they are live.

Refer our [LambdaTest Tunnel documentation](https://www.lambdatest.com/support/docs/testing-locally-hosted-pages/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium) for more information.

Here’s how you can establish LambdaTest Tunnel.

Download the binary file of:

- [LambdaTest Tunnel for Windows](https://downloads.lambdatest.com/tunnel/v3/windows/64bit/LT_Windows.zip)
- [LambdaTest Tunnel for macOS](https://downloads.lambdatest.com/tunnel/v3/mac/64bit/LT_Mac.zip)
- [LambdaTest Tunnel for Linux](https://downloads.lambdatest.com/tunnel/v3/linux/64bit/LT_Linux.zip)

Open command prompt and navigate to the binary folder.

Run the following command:

```bash
LT -user {user’s login email} -key {user’s access key}
```

So if your user name is lambdatest@example.com and key is 123456, the command would be:

```bash
LT -user lambdatest@example.com -key 123456
```

Once you are able to connect **LambdaTest Tunnel** successfully, you would just have to pass on tunnel capabilities in the code shown below :

**Tunnel Capability**

```java
DesiredCapabilities capabilities = new DesiredCapabilities();
        capabilities.setCapability("tunnel", true);
```

## Tutorials 📙

Check out our latest tutorials on TestNG automation testing 👇

- [JUnit 5 vs TestNG: Choosing the Right Framework for Automation Testing](https://www.lambdatest.com/blog/junit-5-vs-testng/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [How To Install TestNG?](https://www.lambdatest.com/blog/how-to-install-testng-in-eclipse-step-by-step-guide/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [Create TestNG Project in Eclipse & Run Selenium Test Script](https://www.lambdatest.com/blog/create-testng-project-in-eclipse-run-selenium-test-script/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [A Complete Guide for Your First TestNG Automation Script](https://www.lambdatest.com/blog/a-complete-guide-for-your-first-testng-automation-script/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [How to Automate using TestNG in Selenium?](https://www.lambdatest.com/blog/testng-in-selenium/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [How to Perform Parallel Test Execution in TestNG with Selenium](https://www.lambdatest.com/blog/parallel-test-execution-in-testng/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [Creating TestNG XML File & Execute Parallel Testing](https://www.lambdatest.com/blog/create-testng-xml-file-execute-parallel-testing/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [Speed Up Automated Parallel Testing in Selenium with TestNG](https://www.lambdatest.com/blog/speed-up-automated-parallel-testing-in-selenium-with-testng/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [Automation Testing With Selenium, Cucumber & TestNG](https://www.lambdatest.com/blog/automation-testing-with-selenium-cucumber-testng/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [How to Run JUnit Selenium Tests using TestNG](https://www.lambdatest.com/blog/test-example-junit-and-testng-in-selenium/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [How to Group Test Cases in TestNG [With Examples]](https://www.lambdatest.com/blog/grouping-test-cases-in-testng/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [How to Set Test Case Priority in TestNG with Selenium](https://www.lambdatest.com/blog/prioritizing-tests-in-testng-with-selenium/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [How to Use Assertions in TestNG with Selenium](https://www.lambdatest.com/blog/asserts-in-testng/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [How to Use DataProviders in TestNG [With Examples]](https://www.lambdatest.com/blog/how-to-use-dataproviders-in-testng-with-examples/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [Parameterization in TestNG - DataProvider and TestNG XML [With Examples]](https://www.lambdatest.com/blog/parameterization-in-testng-dataprovider-and-testng-xml-examples/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [TestNG Listeners in Selenium WebDriver [With Examples]](https://www.lambdatest.com/blog/testng-listeners-in-selenium-webdriver-with-examples/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [TestNG Annotations Tutorial with Examples for Selenium Automation](https://www.lambdatest.com/blog/complete-guide-on-testng-annotations-for-selenium-webdriver/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [How to Use TestNG Reporter Log in Selenium](https://www.lambdatest.com/blog/how-to-use-testng-reporter-log-in-selenium/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [How to Generate TestNG Reports in Jenkins](https://www.lambdatest.com/blog/how-to-generate-testng-reports-in-jenkins/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)

## Documentation & Resources :books:

Visit the following links to learn more about LambdaTest's features, setup and tutorials around test automation, mobile app testing, responsive testing, and manual testing.

- [LambdaTest Documentation](https://www.lambdatest.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [LambdaTest Blog](https://www.lambdatest.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
- [LambdaTest Learning Hub](https://www.lambdatest.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)

## LambdaTest Community :busts_in_silhouette:

The [LambdaTest Community](https://community.lambdatest.com/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium) allows people to interact with tech enthusiasts. Connect, ask questions, and learn from tech-savvy people. Discuss best practises in web development, testing, and DevOps with professionals from across the globe 🌎

## What's New At LambdaTest ❓

To stay updated with the latest features and product add-ons, visit [Changelog](https://changelog.lambdatest.com)

## About LambdaTest

[LambdaTest](https://www.lambdatest.com/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium) is a leading test execution and orchestration platform that is fast, reliable, scalable, and secure. It allows users to run both manual and automated testing of web and mobile apps across 3000+ different browsers, operating systems, and real device combinations. Using LambdaTest, businesses can ensure quicker developer feedback and hence achieve faster go to market. Over 500 enterprises and 1 Million + users across 130+ countries rely on LambdaTest for their testing needs.

### Features

- Run Selenium, Cypress, Puppeteer, Playwright, and Appium automation tests across 3000+ real desktop and mobile environments.
- Real-time cross browser testing on 3000+ environments.
- Test on Real device cloud
- Blazing fast test automation with HyperExecute
- Accelerate testing, shorten job times and get faster feedback on code changes with Test At Scale.
- Smart Visual Regression Testing on cloud
- 120+ third-party integrations with your favorite tool for CI/CD, Project Management, Codeless Automation, and more.
- Automated Screenshot testing across multiple browsers in a single click.
- Local testing of web and mobile apps.
- Online Accessibility Testing across 3000+ desktop and mobile browsers, browser versions, and operating systems.
- Geolocation testing of web and mobile apps across 53+ countries.
- LT Browser - for responsive testing across 50+ pre-installed mobile, tablets, desktop, and laptop viewports

[<img height="58" width="200" src="https://user-images.githubusercontent.com/70570645/171866795-52c11b49-0728-4229-b073-4b704209ddde.png">](https://accounts.lambdatest.com/register?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)

## We are here to help you :headphones:

- Got a query? we are available 24x7 to help. [Contact Us](mailto:support@lambdatest.com)
- For more info, visit - [LambdaTest](https://www.lambdatest.com?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium)
