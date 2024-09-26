#### Maven Compile - *mvn validate*

go through your project at POX.xml file and check if it's a valid maven or has broken XML file
#### Maven Compile - *mvn compile*:

when you run the `mvn compile` command, it compiles your Java source files (`.java`) into bytecode, which is stored in `.class` files. These `.class` files are placed in the `target/classes` directory by default. This bytecode is what the Java Virtual Machine (JVM) interprets and executes.

#### Maven test -  *mvn test*: 

When you run the `mvn test` command, Maven executes the unit tests in your project. Here's what happens during this phase:

1. **Compilation of Test Code**: Maven first compiles the test code located in the `src/test/java` directory. The compiled test classes are stored in the `target/test-classes` directory.
    
2. **Execution of Tests**: Maven runs the compiled test classes using a test framework like JUnit or TestNG. These tests are typically used to verify that your code works as expected.
    
3. **Reporting**: After running the tests, Maven generates test reports. These reports provide information on which tests passed or failed, and any errors or failures encountered. The reports are usually stored in the `target/surefire-reports` directory.
    

Running `mvn test` is a common step in the build process to ensure that the code is functioning correctly before proceeding with further steps like packaging or deployment.

#### combine compile and test - (mvnw compile test)

The `mvnw` command is a wrapper for Maven, allowing you to run Maven commands without requiring a local Maven installation. The `mvnw` command works with the `mvnw` script provided in your project.

When you run `./mvnw compile test`, here's what happens:

1. **`mvnw compile`**:
    
    - The `compile` phase is executed, which compiles the source code in the `src/main/java` directory.
    - The `.java` files are compiled into bytecode, and the `.class` files are stored in the `target/classes` directory.
2. **`mvnw test`**:
    
    - After compiling the main code, Maven compiles the test code located in the `src/test/java` directory.
    - The test classes are stored in the `target/test-classes` directory.
    - Maven then executes the test cases using a test framework (e.g., JUnit or TestNG).
    - Test results are recorded, and a report is generated, typically stored in the `target/surefire-reports` directory.

By running `./mvnw compile test`, you're ensuring that both your main source code and test code are compiled and that the tests are executed to verify the functionality of your code. This is a common command sequence in Continuous Integration (CI) pipelines to validate code changes.

#### combine compile and test and package - (mvnw compile test package)

The command `./mvnw compile test package` is used to run a series of tasks in a Maven project. Here's a breakdown of what each part does:

### 1. **`./mvnw`**:

- **`mvnw`** (short for Maven Wrapper) is a script that ensures you are using a specific version of Maven for your project. This is useful because different projects might require different versions of Maven, and the wrapper ensures that everyone working on the project is using the same version.
- **`./mvnw`** is a command to run the Maven Wrapper script on Unix-like systems (Linux, macOS). For Windows, you would use `mvnw.cmd`.
- When you run `./mvnw`, it will download the required version of Maven if it's not already installed locally.

### 2. **`compile`**:

- This is a **Maven lifecycle phase** that compiles the project's source code.
- During this phase, Maven uses the configured Java compiler (like `javac`) to compile your `.java` files into `.class` files.
- It processes all the source code located in the `src/main/java` directory.

### 3. **`test`**:

- This is another **Maven lifecycle phase** that runs the tests for the project.
- Maven uses the test framework you’ve configured (like JUnit) to execute the tests located in the `src/test/java` directory.
- It ensures that the compiled code from the `compile` phase works as expected.
- If the tests fail, the build process will stop, and the next phases won’t be executed.

### 4. **`package`**:

- The **`package`** phase is responsible for packaging the compiled code into a distributable format, such as a JAR (Java ARchive) or WAR (Web Application Archive) file.
- By the time Maven reaches this phase, it will have already compiled the code and run the tests.
- The final output will typically be located in the `target` directory of your project.

### **Putting It All Together**:

When you run `./mvnw compile test package`, Maven performs the following sequence:

1. **Download Dependencies**: Maven downloads any required dependencies that your project needs to compile and run.
    
2. **Compile (`compile`)**: Maven compiles the source code in your project, turning the `.java` files into `.class` files.
    
3. **Test (`test`)**: Maven runs any tests you've written to ensure that your code behaves as expected.
    
4. **Package (`package`)**: If all tests pass, Maven packages the compiled code into a JAR or WAR file, which you can then deploy or distribute.
    

### **Why Use All Three Together?**:

Running these phases together is common in a continuous integration pipeline, where you want to ensure that the code compiles, the tests pass, and the project is packaged correctly, all in one go.

### **Note**:

If any phase fails (e.g., the tests fail during the `test` phase), Maven will stop executing subsequent phases, and the `package` phase will not be reached. This ensures that only code that passes all tests is packaged.