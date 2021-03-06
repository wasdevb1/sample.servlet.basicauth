Basic Authentication Sample [![Build Status](https://travis-ci.org/WASdev/sample.servlet.basicauth.svg?branch=master)](https://travis-ci.org/WASdev/sample.servlet.basicauth)
==============

The simple servlet sample with added security - it prompts you for credentials before displaying the test web page.

## Running in Eclipse

### Maven
1. Download and install [Eclipse with the WebSphere Developer Tools](https://developer.ibm.com/wasdev/downloads/liberty-profile-using-eclipse/).
2. Create a new Liberty Profile Server. See [step 3](https://developer.ibm.com/wasdev/downloads/liberty-profile-using-eclipse/) for details.
3. Clone this repository.
4. Import the sample into Eclipse using *File -> Import -> Maven -> Existing Maven Projects* option.
5. Right click on the project and go to *Properties > Project Facets* and select *Dynamic Web Module* (if not already selected).
6. Deploy the sample into Liberty server. Right click on the *servlet* sample and select *Run As -> Run on Server* option. Find and select the Liberty profile server and press *Finish*.
7. Go to: [http://localhost:9080/basicauth]

### Gradle
Eclipse will use the Eclipse Buildship Gradle Plugin for Gradle project management and accessibility to tasks.

1. Go to *Help > Eclipse Marketplace > Install Buildship Gradle Integration 2.0*
2. Clone this project and import into Eclipse as an 'Existing Gradle Project'.
3. Go to *Window > Show View > Other > Gradle Executions & Gradle Tasks*
4. Go to Gradle Tasks view and run `clean` in build folder, then `build` in build folder, then `libertyStart` in liberty folder.
5. You should see the following in the console: `Application basicauth started in XX.XX seconds.`
6. Go to: [http://localhost:9080/basicauth]

## Running from the Command-line

### Maven
This project can be built with Apache Maven. The project uses [Liberty Maven Plug-in] to automatically download and install the Liberty Java EE Web Profile  runtime from Maven Central. Liberty Maven Plug-in is also used to create, configure, and run the application on the Liberty server.

Use the following steps to run the application with Maven:

1. Execute full Maven build. This will cause Liberty Maven Plug-in to download and install Liberty profile server.
    ```bash
    $ mvn clean install
    ```

2. To run the server with the Servlet sample execute:
    ```bash
    $ mvn liberty:run-server
    ```

Once the server is running, the application will be available under [http://localhost:9080/basicauth].

### Gradle

This project can also be built and run with [Gradle]. The provided `build.gradle` file applies the [Liberty Gradle Plug-in] and is configured to automatically download and install the Liberty Java EE Web Profile 7 runtime from Maven Central. The Liberty Gradle Plug-in has built-in tasks that can be used to create, configure, and run the application on the Liberty server.

Use the following steps to run the application with Gradle:

1. Execute the full Gradle build. The Liberty Gradle Plug-in will download and install the Liberty server.
    ```bash
    $ gradle clean build
    ```

2. To start the server with the Servlet sample execute:
    ```bash
    $ gradle libertyStart
    ```

    Alternatively, execute the run command:
    ```bash
    $ gradle libertyRun --no-daemon
    ```

Once the server has started, the application will be available under [http://localhost:9080/basicauth].

3. To stop the server, execute:
    ```bash
    $ gradle libertyStop
    ```  

Please refer to the [ci.gradle] repository for documentation about using the Liberty Gradle Plug-in.

# Notice

© Copyright IBM Corporation 2017.

# License

```text
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
````

[Liberty Maven Plug-in]: https://github.com/WASdev/ci.maven
[Liberty Gradle Plug-in]: https://github.com/WASdev/ci.gradle
[ci.gradle]: https://github.com/WASdev/ci.gradle
[http://localhost:9080/basicauth]:http://localhost:9080/basicauth
[Gradle]: https://gradle.org
