---
title: API References
sidebar_position: 4
---

# Peekaboo SDK API Reference

This section provides a comprehensive reference for all the functions and methods available in the Peekaboo SDK. Use this guide to understand how to interact with the SDK programmatically.

---

## Table of Contents

1. [Initialization](#initialization)
2. [Creating Interactive Wait Experiences (IWE)](#creating-interactive-wait-experiences-iwe)
3. [Event Handling](#event-handling)
4. [Customization](#customization)
5. [Analytics](#analytics)
6. [Error Handling](#error-handling)

---

## Initialization

### Initialize the SDK

To use the Peekaboo SDK, you must first initialize it with your API key and project ID.

- **JavaScript**:
    ```javascript
    const Peekaboo = require('peekaboo-sdk');

    const peekaboo = new Peekaboo({
        apiKey: 'YOUR_API_KEY',
        projectId: 'YOUR_PROJECT_ID'
    });
    ```

- **Java**:
    ```java
    import com.peekaboo.sdk.Peekaboo;

    Peekaboo peekaboo = new Peekaboo("YOUR_API_KEY", "YOUR_PROJECT_ID");
    ```

- **Python**:
    ```python
    import peekaboo_sdk as peekaboo

    peekaboo.initialize(api_key='YOUR_API_KEY', project_id='YOUR_PROJECT_ID')
    ```

---

## Creating Interactive Wait Experiences (IWE)

### `createIWE`

Creates an Interactive Wait Experience (IWE) with specified parameters.

#### Parameters

- `options` (Object): Configuration options for the IWE.
  - `message` (String): The message to display.
  - `theme` (String): The visual theme of the IWE.
  - `interactivity` (Object): Interactive elements configuration (optional).

#### Example

- **JavaScript**:
    ```javascript
    peekaboo.createIWE({
        message: 'Hang tight! Great things are coming your way!',
        theme: 'default',
        interactivity: {
            type: 'quiz',
            questions: [
                {
                    question: 'What is your favorite color?',
                    options: ['Red', 'Blue', 'Green', 'Yellow']
                }
            ]
        }
    });
    ```

- **Java**:
    ```java
    peekaboo.createIWE("Hang tight! Great things are coming your way!", "default", new QuizInteractivity(...));
    ```

- **Python**:
    ```python
    peekaboo.create_iwe(
        message='Hang tight! Great things are coming your way!',
        theme='default',
        interactivity={
            'type': 'quiz',
            'questions': [
                {
                    'question': 'What is your favorite color?',
                    'options': ['Red', 'Blue', 'Green', 'Yellow']
                }
            ]
        }
    )
    ```

---

## Event Handling

### `on`

Registers an event listener for specific events.

#### Parameters

- `event` (String): The name of the event.
- `callback` (Function): The function to call when the event occurs.

#### Example

- **JavaScript**:
    ```javascript
    peekaboo.on('userInteraction', (event) => {
        console.log('User interacted:', event);
    });
    ```

- **Java**:
    ```java
    peekaboo.setEventListener(new PeekabooEventListener() {
        @Override
        public void onUserInteraction(Event event) {
            System.out.println("User interacted: " + event);
        }
    });
    ```

- **Python**:
    ```python
    def on_user_interaction(event):
        print('User interacted:', event)

    peekaboo.on('user_interaction', on_user_interaction)
    ```

---

## Customization

### `setTheme`

Sets a custom theme for the IWEs.

#### Parameters

- `theme` (String): The name of the theme.

#### Example

- **JavaScript**:
    ```javascript
    peekaboo.setTheme('customTheme');
    ```

- **Java**:
    ```java
    peekaboo.setTheme("customTheme");
    ```

- **Python**:
    ```python
    peekaboo.set_theme('customTheme')
    ```

### `setInteractivity`

Configures the interactive elements of the IWEs.

#### Parameters

- `interactivity` (Object): Configuration for interactivity.

#### Example

- **JavaScript**:
    ```javascript
    peekaboo.setInteractivity({
        type: 'game',
        config: { ... }
    });
    ```

- **Java**:
    ```java
    peekaboo.setInteractivity(new GameInteractivity(...));
    ```

- **Python**:
    ```python
    peekaboo.set_interactivity({
        'type': 'game',
        'config': { ... }
    })
    ```

---

## Analytics

### `getAnalytics`

Fetches real-time analytics data.

#### Returns

- `Promise` (JavaScript): Resolves with analytics data.
- `AnalyticsData` (Java): Returns analytics data.
- `dict` (Python): Returns analytics data.

#### Example

- **JavaScript**:
    ```javascript
    peekaboo.getAnalytics().then((data) => {
        console.log('Real-time analytics:', data);
    });
    ```

- **Java**:
    ```java
    AnalyticsData data = peekaboo.getAnalytics();
    System.out.println("Real-time analytics: " + data);
    ```

- **Python**:
    ```python
    data = peekaboo.get_analytics()
    print('Real-time analytics:', data)
    ```

---

## Error Handling

### `onError`

Registers an error handler to capture and handle errors.

#### Parameters

- `callback` (Function): The function to call when an error occurs.

#### Example

- **JavaScript**:
    ```javascript
    peekaboo.onError((error) => {
        console.error('An error occurred:', error);
    });
    ```

- **Java**:
    ```java
    peekaboo.setErrorListener(new PeekabooErrorListener() {
        @Override
        public void onError(Error error) {
            System.err.println("An error occurred: " + error);
        }
    });
    ```

- **Python**:
    ```python
    def on_error(error):
        print('An error occurred:', error)

    peekaboo.on_error(on_error)
    ```

---

Peekaboo SDK - Transforming wait times into delightful experiences.
