Twitter's Take Home Assignment
====================

### Design Decisions

* I used Java, Spring Boot and Maven for this coding challenge. 
* The source code is in the `demo/src/main/java` directory. 
* The cve.csv data file is loaded into the `com.demo.vuln.repository.CVERepository` during server startup. 
The data from the csv file is saved in a HashMap for quick lookup. 
* The logic to compare versions is in `com.demo.vuln.model.Version`. I used a maven-artifact library for this comparision 
(since the use of additional libraries was allowed). 
* The controller `com.demo.vuln.controller.VulnController` contains the `/vuln` POST mapping. 
* The controller `com.demo.vuln.controller.VulnController` calls the service class `com.demo.vuln.service.impl.VulnManagementServiceImpl` to retrieve the names of CVEs affecting packages on that host.

### Tests

*  Test code is in the `demo/src/test/java` directory. 
* `com.demo.vuln.repository.CVERepositoryTest` - Unit test for the cve repository. 
* `com.demo.vuln.util.VersionComparatorTest` - Unit test for the version comparision logic. 
* `com.demo.vuln.service.VulnManagementServiceTest` - Unit test for the service class. 
* `com.demo.vuln.controller.VulnControllerTest` - Unit test for the controller class. 
* `com.demo.vuln.VulnComponentTest` - Component test for the vuln service. 


### Prerequisites

* Java 13 - Run `java -version` to verify this is already isntalled. This is already installed on most machines. This can also be installed using
brew or yum. Example `brew install openjdk`. It can also be downloaded and installed from https://www.oracle.com/java/technologies/javase-jdk13-downloads.html 
* Apache Maven - This can be installed on a Mac OS X using `brew install maven` .
Please see https://maven.apache.org/install.html for more information on installing
maven on other types of OS.

### Building

* Please unzip demo.zip 
* Please go to the home directory of the application `cd demo`
* Please execute `mvn clean install` to build the jar file. To skip tests while building the jar file please run `mvn clean install -DskipTests`
* The JAR file will be created in `demo/target/vuln-1.0.0.jar`

### Running Tests

* Please unzip demo.zip 
* Please go to the home directory of the application `cd demo`
* Please execute `mvn test` to run the tests

### Running

* Please execute `java -jar target/vuln-1.0.0.jar` from the demo directory. This will start the server  on the default port 8080.
* If you want to start the server on a different port (for example on 8083) then please execute `java -jar target/vuln-1.0.0.jar --server.port=8083`


_Thank you._
