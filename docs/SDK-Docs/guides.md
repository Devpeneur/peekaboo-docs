---
title: Guides
sidebar_position: 5
---

# Peekaboo SDK Guides

Welcome to the Peekaboo SDK Guides section. Here you will find detailed instructions and best practices for integrating and utilizing Peekaboo SDK in various environments. Follow these guides to ensure a smooth and effective implementation.

---

## Table of Contents

1. [Frontend Integration](#frontend-integration)
2. [Backend Integration](#backend-integration)
3. [Mobile Integration](#mobile-integration)
4. [Customization Guide](#customization-guide)
5. [Troubleshooting and FAQ](#troubleshooting-and-faq)

---

## Frontend Integration

### Overview

Integrating Peekaboo SDK into your frontend application allows you to display Interactive Wait Experiences (IWEs) directly to users in real-time. This guide covers the steps for adding Peekaboo SDK to popular frontend frameworks.

### Step-by-Step Guides

- **React.js**:
    1. **Install the SDK**:
        ```bash
        npm install peekaboo-sdk
        ```
    2. **Initialize the SDK**:
        ```javascript
        import Peekaboo from 'peekaboo-sdk';

        const peekaboo = new Peekaboo({
            apiKey: 'YOUR_API_KEY',
            projectId: 'YOUR_PROJECT_ID'
        });
        ```
    3. **Create and Display an IWE**:
        ```javascript
        peekaboo.createIWE({
            message: 'Hang tight! Great things are coming your way!',
            theme: 'default'
        });
        ```

- **Vue.js**:
    1. **Install the SDK**:
        ```bash
        npm install peekaboo-sdk
        ```
    2. **Initialize the SDK**:
        ```javascript
        import Peekaboo from 'peekaboo-sdk';

        export default {
            created() {
                this.peekaboo = new Peekaboo({
                    apiKey: 'YOUR_API_KEY',
                    projectId: 'YOUR_PROJECT_ID'
                });
            }
        }
        ```
    3. **Create and Display an IWE**:
        ```javascript
        this.peekaboo.createIWE({
            message: 'Hang tight! Great things are coming your way!',
            theme: 'default'
        });
        ```

---

## Backend Integration

### Overview

Integrating Peekaboo SDK into your backend allows you to manage and trigger IWEs based on server-side events and logic. This guide covers the steps for adding Peekaboo SDK to popular backend frameworks.

### Step-by-Step Guides

- **Node.js**:
    1. **Install the SDK**:
        ```bash
        npm install peekaboo-sdk
        ```
    2. **Initialize the SDK**:
        ```javascript
        const Peekaboo = require('peekaboo-sdk');

        const peekaboo = new Peekaboo({
            apiKey: 'YOUR_API_KEY',
            projectId: 'YOUR_PROJECT_ID'
        });
        ```
    3. **Trigger an IWE**:
        ```javascript
        peekaboo.createIWE({
            message: 'Hang tight! Great things are coming your way!',
            theme: 'default'
        });
        ```

- **Java (Spring Boot)**:
    1. **Add Dependency**:
        Add the following to your `pom.xml`:
        ```xml
        <dependency>
            <groupId>com.peekaboo</groupId>
            <artifactId>peekaboo-sdk</artifactId>
            <version>1.0.0</version>
        </dependency>
        ```
    2. **Initialize the SDK**:
        ```java
        import com.peekaboo.sdk.Peekaboo;

        @Service
        public class PeekabooService {
            private Peekaboo peekaboo;

            @PostConstruct
            public void init() {
                peekaboo = new Peekaboo("YOUR_API_KEY", "YOUR_PROJECT_ID");
            }

            public void triggerIWE() {
                peekaboo.createIWE("Hang tight! Great things are coming your way!", "default");
            }
        }
        ```

---

## Mobile Integration

### Overview

Integrating Peekaboo SDK into your mobile application allows you to display IWEs directly to users on their mobile devices. This guide covers the steps for adding Peekaboo SDK to popular mobile development frameworks.

### Step-by-Step Guides

- **Android**:
    1. **Add Dependency**:
        Add the following to your `build.gradle`:
        ```gradle
        implementation 'com.peekaboo:peekaboo-sdk:1.0.0'
        ```
    2. **Initialize the SDK**:
        ```java
        import com.peekaboo.sdk.Peekaboo;

        public class MainActivity extends AppCompatActivity {
            private Peekaboo peekaboo;

            @Override
            protected void onCreate(Bundle savedInstanceState) {
                super.onCreate(savedInstanceState);
                setContentView(R.layout.activity_main);

                peekaboo = new Peekaboo("YOUR_API_KEY", "YOUR_PROJECT_ID");
            }

            public void triggerIWE() {
                peekaboo.createIWE("Hang tight! Great things are coming your way!", "default");
            }
        }
        ```

- **iOS (Swift)**:
    1. **Add Dependency**:
        Add the following to your `Podfile`:
        ```ruby
        pod 'PeekabooSDK', '~> 1.0'
        ```
    2. **Initialize the SDK**:
        ```swift
        import PeekabooSDK

        class ViewController: UIViewController {
            var peekaboo: Peekaboo!

            override func viewDidLoad() {
                super.viewDidLoad()

                peekaboo = Peekaboo(apiKey: "YOUR_API_KEY", projectId: "YOUR_PROJECT_ID")
            }

            func triggerIWE() {
                peekaboo.createIWE(message: "Hang tight! Great things are coming your way!", theme: "default")
            }
        }
        ```

---

## Customization Guide

### Overview

Peekaboo SDK offers extensive customization options to tailor the appearance and behavior of IWEs to match your brand and user preferences. This guide covers how to customize themes, messages, and interactive elements.

### Customizing Themes

1. **Define a Custom Theme**:
    ```javascript
    const customTheme = {
        backgroundColor: '#ff5722',
        textColor: '#ffffff',
        fontSize: '16px',
        fontFamily: 'Arial, sans-serif'
    };
    ```

2. **Apply the Custom Theme**:
    ```javascript
    peekaboo.setTheme(customTheme);
    ```

### Customizing Messages

1. **Set a Custom Message**:
    ```javascript
    peekaboo.createIWE({
        message: 'Your personalized message here!',
        theme: 'customTheme'
    });
    ```

### Customizing Interactive Elements

1. **Define Interactive Elements**:
    ```javascript
    const interactivity = {
        type: 'survey',
        questions: [
            {
                question: 'How satisfied are you with our service?',
                options: ['Very Satisfied', 'Satisfied', 'Neutral', 'Dissatisfied', 'Very Dissatisfied']
            }
        ]
    };
    ```

2. **Apply the Interactive Elements**:
    ```javascript
    peekaboo.createIWE({
        message: 'We value your feedback!',
        theme: 'customTheme',
        interactivity: interactivity
    });
    ```

---

## Troubleshooting and FAQ

### Common Issues

1. **SDK Initialization Failure**
    - **Solution**: Ensure your API key and project ID are correct and have been properly set.

2. **IWE Not Displaying**
    - **Solution**: Check if the SDK is correctly initialized and the IWE creation method is called appropriately.

3. **Event Handlers Not Working**
    - **Solution**: Verify that event names are correct and callbacks are properly defined.

### Frequently Asked Questions

1. **How do I obtain an API key?**
    - **Answer**: Sign up on our [developer portal](https://peekaboo.com/developer) to obtain your API key.

2. **Can I customize the IWE themes?**
    - **Answer**: Yes, you can define and apply custom themes to match your brand.

3. **Is Peekaboo SDK compatible with mobile applications?**
    - **Answer**: Yes, Peekaboo SDK supports integration with both Android and iOS platforms.

For more detailed troubleshooting and frequently asked questions, visit our [support page](https://peekaboo.com/support).

---

Peekaboo SDK - Transforming wait times into delightful experiences.
