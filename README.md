# JavaFX WebApp Starter

This project demonstrates how to create a simple JavaFX application that runs both on desktop and in the browser using JPro. It's a great starting point for developers looking to build JavaFX applications with cross-platform capabilitie

🛠️ **Technologies Used**
- **JavaFX**: Used for building the user interface of the application.
- **JPro**: Allows JavaFX applications to run in web browsers.
- **Gradle**: Used for build automation and dependency management.


### **Java (App.java)**
This file contains the main JavaFX code that initializes the application, sets up the primary stage, and adds the user interface components.

```java
package com.example;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class App extends Application {
    @Override
    public void start(Stage primaryStage) {
        Button button = new Button("Click Me!");
        button.setOnAction(e -> System.out.println("Button clicked!"));

        StackPane root = new StackPane(button);
        Scene scene = new Scene(root, 400, 300);

        primaryStage.setTitle("JavaFX Web App");
        primaryStage.setScene(scene);
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
  ```
### **Gradle Build Script (build.gradle)**
Here's the complete `build.gradle` configuration:

```groovy
plugins {
    id 'java'
    id 'application'
}

repositories {
    mavenCentral()
}

dependencies {
    implementation 'org.openjfx:javafx-controls:20.0.1'
    implementation 'com.jpro:jpro-web:2023.1.0'
}

application {
    mainClass = 'com.example.App'
}
```
🔧 **How to Run**

1. **Clone the Repository**  
   Clone this project to your local machine:
   ```bash
   git clone https://github.com/your-username/javafx-webapp-starter.git
   cd javafx-webapp-starter
   ```
2. **Install Dependencies**  
   Ensure you have Java 17+ installed. Add dependencies using Gradle:
   ```bash
   gradle build
   ```
3. **Run the Application**

   - **Desktop Mode**:
     ```bash
     gradle run
     ```

   - **Web Mode**:
     ```bash
     gradle jproRun
     ```
     Open your web browser and navigate to [http://localhost:8080](http://localhost:8080).
📝 **Customization**

- **Add UI Components**: Modify `App.java` to include more UI elements as needed.
- **Styles**: Customize `application.css` to change the appearance of the app.
- **Web Configuration**: Adjust the `jpro-web` settings for better integration with web servers.

💡 **Future Enhancements**

- **Responsive Design**: Implement CSS rules for better mobile and tablet support.
- **User Interaction**: Add more interactivity, such as keyboard shortcuts or additional buttons.
- **Database Connectivity**: Integrate a database to enable data storage and retrieval.


Make sure to replace `https://github.com/your-username/javafx-webapp-starter.git` and `https://github.com/your-username` with your actual repository URL and GitHub profile link.
