
## Prerequisites

* Install [Git](https://github.com/saucelabs-training/demo-java/blob/master/docs/prerequisites.md#install-git)
* Install [IntelliJ (or another IDE)](https://github.com/saucelabs-training/demo-java/blob/master/docs/prerequisites.md#install-intellij)
* Install [JDK](https://github.com/saucelabs-training/demo-java/blob/master/docs/prerequisites.md#install-the-jdk)
* Install [Maven](https://github.com/saucelabs-training/demo-java/blob/master/docs/prerequisites.md#install-maven)

<br />

## Project Setup
* [Import the Project](#import-the-project)
* [Set Your Sauce Labs Credentials](#set-your-sauce-labs-credentials)
* [Run a Maven Test](#run-a-maven-test)
 
<br />


#### Import the Project

1. Create a directory on your machine.
2. Clone this repository into said directory.
    ```
    $ git clone https://github.com/saucelabs-training/demo-java.git
    ```
2. Import the project into your IntelliJ (or IDE of your choice) as a **Maven Project**.
3. Click through the prompts, and confirm when it asks to **Import from Sources**
4. Choose the **selenium3-testng-framework** directory as the **root** directory of the project.

#### Set Your Sauce Labs Credentials
1. Here are the credentials you need for sauce labs. (Contact Vinh)
2. Open a Terminal window (command prompt for Windows) and set your Sauce Labs Environment variables:   
   ###### Mac OSX:
   ```
   $ export SAUCE_USERNAME="username"
   $ export SAUCE_ACCESS_KEY="accessKey"
   ```
   ###### Windows:
   ```
   > set SAUCE_USERNAME="username"
   > set SAUCE_ACCESS_KEY="accessKey"
   ```
   > To set an environment variables permanently in Windows, you must append it to the `PATH` variable.
   
   > Go to **Control Panel > System > Windows version > Advanced System Settings > Environment Variables > System Variables > Edit > New**
   
   > Then set the "Name" and "Value" for each variable
   
9. Test the environment variables
    ###### Mac OSX:
    ```
    $ echo $SAUCE_USERNAME
    $ echo $SAUCE_ACCESS_KEY
    ```
    > ***WARNING FOR UNIX USERS!***:
    > If you have problems setting your environment variables, run the following commands in your terminal:
    ```
    $ launchctl setenv SAUCE_USERNAME $SAUCE_USERNAME
    $ launchctl setenv SAUCE_ACCESS_KEY $SAUCE_ACCESS_KEY
    ```
    ###### Windows:
    ```
    > echo %SAUCE_USERNAME%
    > echo %SAUCE_ACCESS_KEY%
    ```

<br />

#### Run a Maven Test

1. Run the following command to update any package dependencies:
    ```
    $ mvn dependency:resolve
    ```
2. Then run the following command to compile your test code:
    ```
    $ mvn test-compile
    ```
3. Finally, run the following test to see if you've properly configured the test environment:
    ```
    $ mvn test -Dtest=Module2TestNGTest -pl on-boarding-modules/testng

    ```

    > If you wish to run a specific test/sub-module in this emusim_testng use the following command:
    >   ```
    >   # for running a specific test:
    >   mvn test -Dtest=testname
    > 
    >   # for running all tests
    >   mvn test
    >   ```
