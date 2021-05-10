# Jest-Setup
Jest Stup for  LWC Testing framework


##  Create a Salesforce DX Project

The first step before testing is to create a Salesforce DX project to store your Lightning web components and Jest tests.

1.  In Visual Studio Code, open the Command Palette by pressing Ctrl+Shift+P (Windows) or Cmd+Shift+P (macOS).
2.  Enter sfdx.
3.  Select SFDX: Create Project. If you don’t see this option, complete the prerequisites from this module’s first unit before you go on.
4.  Select Standard.
5.  Enter test-lwc as the project name.
6.  Press Enter.
7.  Select a folder to store the project.
8.  Click Create Project and wait for the new Visual Studio Code window to open.
9.  Click View, then choose Terminal. This opens a terminal window inside Visual Studio Code. The terminal defaults to the top-level directory of the project. You need the terminal later to run commands in the working directory of this project.


##  Install Node.js and npm

1.  Install Node.js from https://nodejs.org/en/download/. We recommend using the LTS (long-term support) version.
2.  Confirm Node.js is installed. In the Visual Studio Code terminal we opened earlier, enter the following command.
  ```
    node --version
  ```
You should see output like v12.13.0 or a later version.

3.  When you install Node.js, npm also installs automatically.

In a terminal, enter the following command.
  ```
    npm --version
  ```
You should see output like 6.13.0 or a later version.


##  What Is Jest?

Jest is a powerful tool with rich features for writing JavaScript tests. Jest can collect code coverage information and supports mocking to help isolate tests from complex dependencies. Jest tests don’t run in a browser or connect to an org, so they run fast. Use Jest to write unit tests for all of your Lightning web components. To run Jest tests for Lightning web components, you need the @salesforce/sfdx-lwc-jest Node module in your Salesforce DX project.

##  Install sfdx-lwc-jest Node Module

The @salesforce/sfdx-lwc-jest Node module lets you write, run, and debug Jest tests for Lightning Web Components. The Salesforce CLI makes it easy to install Jest and its dependencies into the project.

In the Visual Studio Code terminal, run the following command in the top-level directory of your Salesforce DX project:
```
  sfdx force:lightning:lwc:test:setup

```

##  Run Jest Tests

Excellent, you set up your Salesforce DX project to be able to run the Jest tests that you write later in this module. There are several ways to run the Jest tests now that everything is set up. You can call the script directly, use npm commands, or you can use clicks in Visual Studio Code. You can run one test or all tests in a file or project. You can even run tests automatically when the code the test covers is changed.

Let’s take a look at the different ways you can run Jest tests.

The sfdx-lwc-jest Node Command
You can run the script directly from where it was installed in the project using the following Node command.

In the Visual Studio Code terminal, in the top-level directory of the Salesforce DX project, enter the following command.

  ```
    
    node node_modules/@salesforce/sfdx-lwc-jest/bin/sfdx-lwc-jest
    
  ```
  There are no Jest tests yet so you should see output like No tests found, exiting with code 1.
  
  ```
      
      Note
            If you get an “Invalid sourceApiVersion” error it is due to an updated VS Code Extension with the latest Salesforce release.
            error Invalid sourceApiVersion found in sfdx-project.json. Expected 49.0, found 50.0
            In Visual Studio Code, in the top-level directory, open sfdx-project.json.
            Update the line of code with “sourceApiVersion” to the Expected version from the error message you received.
            "sourceApiVersion": "49.0"
            Save the file.
   ```
   
   If you want to run all tests for your project, run this npm command from the base directory of your project.

  ```
    npm run test:unit
    
  ```
If you want to run tests in a specific directory, using the command above in a specific directory will run only the tests in that directory. This allows you to isolate what you are testing.

##  Run Tests Continuously During Development

For this option, Node relies on Git to “watch” the code. To use this option, be sure to have Git initialized for your project. To run all tests for a single component every time you save changes, change directories to the component directory and run the npm command below that utilizes sfdx-lwc-jest with the --watch parameter. As mentioned above you could also run this from the base of the project and have all tests in the project run for every change.

```
  npm run test:unit:watch

```
Jest now watches all component files for updates and runs all relevant tests every time it detects a change.

Run Tests in Jest Debug Mode

To run the project’s Jest tests in debug mode, use the npm command below that utilizes sfdx-lwc-jest with the --debug parameter. 
```
npm run test:unit:debug

```
For information about troubleshooting Jest issues, see Jest: Troubleshooting.

Run Tests and Display Code Coverage

To see the code coverage of the tests, use the --coverage option below. 
```
npm run test:unit:coverage
```

  
  
  
  
