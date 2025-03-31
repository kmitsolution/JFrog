### 📌 **Installing Java and Maven on Ubuntu**  
Run the following commands to install Java 8 and Maven:  

```sh
sudo apt update
sudo apt install openjdk-8-jdk maven -y
```

Check versions:  
```sh
java -version
mvn -version
```

### 📌 **Maven Configuration File Location**  
When Maven is installed via `apt install maven`, the default **settings.xml** file is found at:  
```
/usr/share/maven/conf/settings.xml
```
For user-specific configurations, create or edit:  
```
~/.m2/settings.xml
```

### 📌 **Debugging Maven Commands**  
You can debug Maven commands by using the `-X` option, which enables verbose debugging output:  
```sh
mvn -X <command>
```
For example, to debug `compile`:  
```sh
mvn -X compile
```

---

## **🚀 Common Maven Commands Explained**

### 1️⃣ **Compile**  
```sh
mvn compile
```
- Compiles the source code (`src/main/java`).
- Outputs compiled `.class` files in `target/classes`.

### 2️⃣ **Test**  
```sh
mvn test
```
- Runs unit tests in `src/test/java` using JUnit/TestNG.
- If tests fail, Maven stops execution.

### 3️⃣ **Package**  
```sh
mvn package
```
- Compiles and packages the project into a JAR/WAR file.
- Output is stored in `target/` (e.g., `target/myapp.jar`).

### 4️⃣ **Install**  
```sh
mvn install
```
- Compiles, tests, and installs the package into the local repository (`~/.m2/repository`).
- This allows other projects on your machine to use it as a dependency.

### 5️⃣ **Deploy**  
```sh
mvn deploy
```
- Uploads the package to a remote repository (Nexus, Artifactory, etc.).
- Used in CI/CD pipelines to share artifacts across teams.
