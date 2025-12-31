# 🛒 Empik E-Commerce UI Automation Framework

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Selenium](https://img.shields.io/badge/Selenium-WebDriver-43B02A?style=for-the-badge&logo=selenium&logoColor=white)
![Pattern](https://img.shields.io/badge/Pattern-Page_Object_Model-orange?style=for-the-badge)
![Style](https://img.shields.io/badge/Style-Fluent_API-blue?style=for-the-badge)

## 📖 Overview

This repository contains a robust UI automation test suite for **empik.com**, one of the largest e-commerce platforms in Poland.

The primary goal of this project is to demonstrate **Senior-level test automation practices** in Python, specifically focusing on maintainability, readability, and scalability. The framework is built using **Selenium WebDriver** and strictly adheres to the **Page Object Model (POM)** design pattern with **Fluent Interface** implementation.

## 🛠 Tech Stack & Concepts

* **Language:** Python
* **Driver:** Selenium WebDriver
* **Design Pattern:** Page Object Model (POM) - ensuring separation of test logic from UI selectors.
* **Coding Style:** Fluent API (Method Chaining) - allowing for readable, sentence-like test execution flow.
* **Assertions:** PyTest / Unittest (zależnie co tam masz)
* **Waits:** Explicit Waits (WebDriverWait) for stability.

## 🏗 Architecture

The project is structured to minimize code duplication and maximize clarity:

1.  **Page Object Model (POM):** Each web page (Login, Search, Cart, Product Details) is represented by a separate class. These classes encapsulate the locators and methods to interact with the page.
2.  **Fluent API:** Methods return `self` or other Page Objects, enabling method chaining. This makes the test scenarios read like natural language.

### Example of Fluent API usage:

```python
# The framework allows writing concise and readable tests:
def test_user_can_purchase_book(self):
    HomePage(self.driver) \
        .open() \
        .search_for_product("Wiedźmin") \
        .select_first_result() \
        .add_to_cart() \
        .go_to_checkout() \
        .verify_item_in_basket("Wiedźmin")
'''
🧪 Test Scenarios Covered
The framework covers critical user journeys for an e-commerce platform:

✅ User Authentication: Login processes (valid/invalid scenarios).

✅ Search Functionality: Querying products and filtering results.

✅ Shopping Cart: Adding items, removing items, updating quantities.

✅ Product Navigation: Navigating from listing to product details.

