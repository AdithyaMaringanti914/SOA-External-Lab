# MS1 GET Endpoint + YAML Contract Demo

This is a small Spring Boot project for the lab experiment "GET Endpoint Contract Definition using YAML".

## Requirements
- JDK 17 or later
- Maven 3.6+ (or use the Maven wrapper supplied by your IDE)

Check Java:
```bash
java -version
```

Check Maven:
```bash
mvn -version
```

## Run in IntelliJ IDEA
1. Extract `ms1-get-contract-project.zip`.
2. Open IntelliJ IDEA and choose **Open**.
3. Select the extracted project folder (the folder containing `pom.xml`).
4. If prompted, load/import the Maven project.
5. Set the Project SDK to JDK 17 or later.
6. Open `src/main/java/com/example/ms1/Ms1Application.java`.
7. Click the green Run icon beside `main()`.

## Run from terminal
Open a terminal in the folder containing `pom.xml` and run:
```bash
mvn spring-boot:run
```

Wait until the console says the application has started and Tomcat is listening on port 8080.

## Show the output
Open this URL in a browser:
```text
http://localhost:8080/ms1/add?a=5&b=10
```

Expected response:
```text
MS 1.1 - Additon = 15
```

You can also test it in Postman:
- Method: GET
- URL: `http://localhost:8080/ms1/add?a=5&b=10`
- Click **Send**
- Expected status: `200 OK`
- Expected body: `MS 1.1 - Additon = 15`

## Run the test
Stop the running application if needed, then run:
```bash
mvn test
```
The test checks the HTTP status, content type, and exact response body for `a=5` and `b=10`.

## Important note about the YAML file
`src/main/resources/contracts/ms1-contract.yml` is the YAML contract requested in the lab task. In this demo, it documents the agreed request/response format. Spring Boot does not automatically enforce an arbitrary YAML file just because it is present. The included automated test independently verifies that the endpoint returns the specified response. Full provider/consumer contract verification can be added with Spring Cloud Contract if required by your lab.

## Project structure
```text
ms1-get-contract-project/
├── pom.xml
├── README.md
└── src/
    ├── main/
    │   ├── java/com/example/ms1/
    │   │   ├── Ms1Application.java
    │   │   └── AddController.java
    │   └── resources/
    │       ├── application.properties
    │       └── contracts/ms1-contract.yml
    └── test/java/com/example/ms1/
        └── AddControllerTest.java
```
