---
title: Core Concepts
sidebar_position: 3
---

# Core Concepts

Understanding the core concepts of Peekaboo SDK is crucial for effectively integrating and utilizing its features. This section covers the fundamental ideas and components that make up Peekaboo SDK.

---

## Interactive Wait Experiences (IWE)

### What is an IWE?

An Interactive Wait Experience (IWE) is a dynamic and engaging piece of content that is displayed to users during periods of high traffic or wait times. The goal of an IWE is to reduce user frustration by providing a positive and interactive experience while they wait.

### Key Components of an IWE:

- **Message**: The text or content that is displayed to the user.
- **Theme**: The visual style and appearance of the IWE, which can be customized to match your brand.
- **Interactivity**: Elements such as games, quizzes, or other interactive content to engage users.

### Creating an IWE

To create an IWE, you need to provide a message and optionally specify a theme and interactive elements. Here’s an example:

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

### What is Event Handling?

Event handling in Peekaboo SDK refers to the way the system manages and responds to user interactions during the display of an IWE. Events can include user actions such as clicks, form submissions, or interactions with interactive elements.

### Types of Events:

- **User Interaction**: Events triggered by user actions (e.g., clicking a button, answering a quiz).
- **System Events**: Automatically triggered events based on system conditions (e.g., wait time exceeds a threshold).

### Handling Events

To handle events, you can define callbacks or functions that execute when specific events occur. Here’s an example:

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

## Customization Options

### Why Customize?

Customization allows you to tailor the appearance and behavior of IWEs to match your brand identity and user preferences, ensuring a seamless and engaging user experience.

### Customization Parameters:

- **Themes**: Predefined visual styles that can be applied to IWEs.
- **Content**: Custom messages, images, and interactive elements.
- **Behavior**: Configurable actions based on user interactions and system events.

### Applying Customizations

To customize an IWE, you can specify various parameters during its creation:

- **JavaScript**:
    ```javascript
    peekaboo.createIWE({
        message: 'Your customized message!',
        theme: 'customTheme',
        interactivity: {
            type: 'game',
            config: { ... }
        }
    });
    ```

- **Java**:
    ```java
    peekaboo.createIWE("Your customized message!", "customTheme", new GameInteractivity(...));
    ```

- **Python**:
    ```python
    peekaboo.create_iwe(
        message='Your customized message!',
        theme='customTheme',
        interactivity={
            'type': 'game',
            'config': { ... }
        }
    )
    ```

---

## Real-Time Analytics

### What are Real-Time Analytics?

Real-time analytics provide insights into how users interact with IWEs, helping you understand user behavior and optimize the experiences accordingly.

### Key Metrics:

- **Engagement Rate**: The percentage of users who interact with the IWE.
- **Average Wait Time**: The average duration users spend on the IWE.
- **Interaction Types**: Breakdown of different types of interactions (e.g., quiz completions, game plays).

### Accessing Analytics

Peekaboo SDK offers an analytics API to fetch real-time data. Here’s an example:

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

## Summary

Peekaboo SDK's core concepts revolve around creating engaging Interactive Wait Experiences (IWEs), handling user and system events efficiently, providing extensive customization options, and offering real-time analytics to monitor and improve user interactions. Understanding these concepts will help you make the most out of Peekaboo SDK and deliver exceptional user experiences during peak traffic times.

---

Peekaboo SDK - Transforming wait times into delightful experiences.
