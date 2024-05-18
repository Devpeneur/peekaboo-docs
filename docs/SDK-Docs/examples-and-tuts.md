---
title: Examples and Tutorials
sidebar_position: 6
---

# Examples and Tutorials

Welcome to the Peekaboo SDK Examples and Tutorials section. Here, you'll find practical examples and step-by-step tutorials to help you get started with Peekaboo SDK and make the most out of its features.

---

## Table of Contents

1. [Basic Integration](#basic-integration)
2. [Advanced Customization](#advanced-customization)
3. [Handling User Interactions](#handling-user-interactions)
4. [Using Real-Time Analytics](#using-real-time-analytics)
5. [Error Handling and Debugging](#error-handling-and-debugging)

---

## Basic Integration

### Example: Basic IWE Creation

This example demonstrates how to create and display a simple Interactive Wait Experience (IWE).

- **JavaScript**:
    ```javascript
    import Peekaboo from 'peekaboo-sdk';

    const peekaboo = new Peekaboo({
        apiKey: 'YOUR_API_KEY',
        projectId: 'YOUR_PROJECT_ID'
    });

    peekaboo.createIWE({
        message: 'Hang tight! Great things are coming your way!',
        theme: 'default'
    });
    ```

- **Java**:
    ```java
    import com.peekaboo.sdk.Peekaboo;

    public class Main {
        public static void main(String[] args) {
            Peekaboo peekaboo = new Peekaboo("YOUR_API_KEY", "YOUR_PROJECT_ID");
            peekaboo.createIWE("Hang tight! Great things are coming your way!", "default");
        }
    }
    ```

- **Python**:
    ```python
    import peekaboo_sdk as peekaboo

    peekaboo.initialize(api_key='YOUR_API_KEY', project_id='YOUR_PROJECT_ID')

    peekaboo.create_iwe(
        message='Hang tight! Great things are coming your way!',
        theme='default'
    )
    ```

---

## Advanced Customization

### Tutorial: Creating a Custom Themed IWE

This tutorial walks you through creating a custom-themed IWE with interactive elements.

1. **Define the Custom Theme**:
    ```javascript
    const customTheme = {
        backgroundColor: '#123456',
        textColor: '#ffffff',
        fontSize: '18px',
        fontFamily: 'Verdana, sans-serif'
    };
    ```

2. **Create the Interactive Element**:
    ```javascript
    const interactivity = {
        type: 'poll',
        question: 'What feature would you like to see next?',
        options: ['New UI', 'More Games', 'Better Performance']
    };
    ```

3. **Create and Display the IWE**:
    ```javascript
    peekaboo.createIWE({
        message: 'We value your feedback!',
        theme: customTheme,
        interactivity: interactivity
    });
    ```

4. **Complete Code Example**:
    ```javascript
    import Peekaboo from 'peekaboo-sdk';

    const peekaboo = new Peekaboo({
        apiKey: 'YOUR_API_KEY',
        projectId: 'YOUR_PROJECT_ID'
    });

    const customTheme = {
        backgroundColor: '#123456',
        textColor: '#ffffff',
        fontSize: '18px',
        fontFamily: 'Verdana, sans-serif'
    };

    const interactivity = {
        type: 'poll',
        question: 'What feature would you like to see next?',
        options: ['New UI', 'More Games', 'Better Performance']
    };

    peekaboo.createIWE({
        message: 'We value your feedback!',
        theme: customTheme,
        interactivity: interactivity
    });
    ```

---

## Handling User Interactions

### Example: Capturing User Feedback

This example shows how to capture and handle user interactions within an IWE.

1. **Register Event Listener**:
    ```javascript
    peekaboo.on('userInteraction', (event) => {
        console.log('User interaction captured:', event);
    });
    ```

2. **Create an Interactive IWE**:
    ```javascript
    peekaboo.createIWE({
        message: 'Tell us your favorite color!',
        theme: 'default',
        interactivity: {
            type: 'quiz',
            question: 'What is your favorite color?',
            options: ['Red', 'Blue', 'Green', 'Yellow']
        }
    });
    ```

3. **Complete Code Example**:
    ```javascript
    import Peekaboo from 'peekaboo-sdk';

    const peekaboo = new Peekaboo({
        apiKey: 'YOUR_API_KEY',
        projectId: 'YOUR_PROJECT_ID'
    });

    peekaboo.on('userInteraction', (event) => {
        console.log('User interaction captured:', event);
    });

    peekaboo.createIWE({
        message: 'Tell us your favorite color!',
        theme: 'default',
        interactivity: {
            type: 'quiz',
            question: 'What is your favorite color?',
            options: ['Red', 'Blue', 'Green', 'Yellow']
        }
    });
    ```

---

## Using Real-Time Analytics

### Tutorial: Accessing and Displaying Real-Time Analytics

This tutorial demonstrates how to fetch and display real-time analytics data.

1. **Fetch Analytics Data**:
    ```javascript
    peekaboo.getAnalytics().then((data) => {
        console.log('Real-time analytics:', data);
    });
    ```

2. **Display Analytics in the UI**:
    ```javascript
    peekaboo.getAnalytics().then((data) => {
        document.getElementById('analytics').innerText = JSON.stringify(data, null, 2);
    });
    ```

3. **Complete Code Example**:
    ```javascript
    import Peekaboo from 'peekaboo-sdk';

    const peekaboo = new Peekaboo({
        apiKey: 'YOUR_API_KEY',
        projectId: 'YOUR_PROJECT_ID'
    });

    peekaboo.getAnalytics().then((data) => {
        document.getElementById('analytics').innerText = JSON.stringify(data, null, 2);
    });
    ```

4. **HTML Element for Displaying Analytics**:
    ```html
    <div id="analytics"></div>
    ```

---

## Error Handling and Debugging

### Example: Implementing Error Handling

This example shows how to implement error handling to capture and manage errors within Peekaboo SDK.

1. **Register Error Handler**:
    ```javascript
    peekaboo.onError((error) => {
        console.error('An error occurred:', error);
    });
    ```

2. **Trigger an Error for Testing**:
    ```javascript
    // Simulate an error
    peekaboo.createIWE({
        message: 'This will fail!',
        theme: 'nonexistentTheme'
    });
    ```

3. **Complete Code Example**:
    ```javascript
    import Peekaboo from 'peekaboo-sdk';

    const peekaboo = new Peekaboo({
        apiKey: 'YOUR_API_KEY',
        projectId: 'YOUR_PROJECT_ID'
    });

    peekaboo.onError((error) => {
        console.error('An error occurred:', error);
    });

    // Simulate an error
    peekaboo.createIWE({
        message: 'This will fail!',
        theme: 'nonexistentTheme'
    });
    ```

---

Peekaboo SDK - Transforming wait times into delightful experiences.
