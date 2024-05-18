---
title: Getting Started
sidebar_position: 2
---

# Getting Started with Peekaboo SDK

Welcome to the Peekaboo SDK! This guide will help you get up and running quickly, so you can start transforming your users' waiting times into engaging and delightful experiences.

---

## Installation Guide

### Requirements

Before you begin, ensure you have the following prerequisites:

- Node.js (for JavaScript environments)
- Java Development Kit (JDK) (for Java environments)
- Python (for Python environments)
- Internet access to download the SDK

### Installation Steps

#### For JavaScript (Node.js)

1. **Install via npm**:
    ```bash
    npm install peekaboo-sdk
    ```

2. **Verify Installation**:
    ```bash
    npm list peekaboo-sdk
    ```

#### For Java (Maven)

1. **Add Dependency**:
    Add the following to your `pom.xml`:
    ```xml
    <dependency>
        <groupId>com.peekaboo</groupId>
        <artifactId>peekaboo-sdk</artifactId>
        <version>1.0.0</version>
    </dependency>
    ```

2. **Verify Installation**:
    Run `mvn clean install` and ensure there are no errors.

#### For Python

1. **Install via pip**:
    ```bash
    pip install peekaboo-sdk
    ```

2. **Verify Installation**:
    ```bash
    pip show peekaboo-sdk
    ```

---

## Quick Start Guide

Follow these steps to quickly integrate Peekaboo SDK into your project.

### Setup

1. **Import the SDK**:
    - **JavaScript**:
        ```javascript
        const Peekaboo = require('peekaboo-sdk');
        ```
    - **Java**:
        ```java
        import com.peekaboo.sdk.Peekaboo;
        ```
    - **Python**:
        ```python
        import peekaboo_sdk as peekaboo
        ```

2. **Initialize the SDK**:
    - **JavaScript**:
        ```javascript
        const peekaboo = new Peekaboo({
            apiKey: 'YOUR_API_KEY',
            projectId: 'YOUR_PROJECT_ID'
        });
        ```
    - **Java**:
        ```java
        Peekaboo peekaboo = new Peekaboo("YOUR_API_KEY", "YOUR_PROJECT_ID");
        ```
    - **Python**:
        ```python
        peekaboo.initialize(api_key='YOUR_API_KEY', project_id='YOUR_PROJECT_ID')
        ```

### Basic Integration

1. **Create an Interactive Wait Experience (IWE)**:
    - **JavaScript**:
        ```javascript
        peekaboo.createIWE({
            message: 'Hang tight! Great things are coming your way!',
            theme: 'default'
        });
        ```
    - **Java**:
        ```java
        peekaboo.createIWE("Hang tight! Great things are coming your way!", "default");
        ```
    - **Python**:
        ```python
        peekaboo.create_iwe(message='Hang tight! Great things are coming your way!', theme='default')
        ```

2. **Display the IWE during peak traffic**:
    Integrate the IWE creation call at points in your application where users typically experience wait times.

### Verification

Run your application and trigger a scenario where the IWE should appear. Ensure that the interactive content is displayed as expected.

---

## Integration Guide

Peekaboo SDK can be integrated with various environments. Choose the guide that matches your platform:

- **Frontend Integration**: [Frontend Integration Guide](docs/guides/frontend-integration.md)
- **Backend Integration**: [Backend Integration Guide](docs/guides/backend-integration.md)
- **Mobile Integration**: [Mobile Integration Guide](docs/guides/mobile-integration.md)

---

## Learn More

Explore more features and customization options in our detailed documentation:

- [Core Concepts](docs/concepts/core-concepts.md)
- [API Reference](docs/api-reference.md)
- [Customization Guide](docs/guides/customization.md)

---

## Need Help?

If you run into any issues, check out our [Troubleshooting and FAQ](docs/troubleshooting-and-faq.md) or reach out to our support team at [support@peekaboo.com](mailto:support@peekaboo.com).

---

Peekaboo SDK - Transforming wait times into delightful experiences.
