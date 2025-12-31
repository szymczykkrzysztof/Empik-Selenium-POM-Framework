# 🛒 Empik E-Commerce Automation Framework

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Selenium](https://img.shields.io/badge/Selenium-WebDriver-43B02A?style=for-the-badge&logo=selenium&logoColor=white)
![Architecture](https://img.shields.io/badge/Architecture-Page_Object_Model-orange?style=for-the-badge)
![Pattern](https://img.shields.io/badge/Pattern-Fluent_Interface-blue?style=for-the-badge)

## 📖 Overview

A professional-grade UI test automation framework designed for **empik.com**, one of the largest e-commerce platforms in Poland.

This project serves as a technical showcase of **Senior QA Automation** practices in Python. Unlike simple linear scripts, this framework treats test automation as a software project, focusing on **scalability, readability, and reliability**. It strictly implements the **Page Object Model (POM)** design pattern combined with a **Fluent Interface API**.

## 🏗 Key Architectural Highlights

### 1. Fluent Interface Implementation
The framework utilizes method chaining to create highly readable, sentence-like test scenarios. Each action method returns an instance of a Page Object (either `self` or the next logical page), allowing for a clean flow without repetitive instantiation.

**Code Example:**
```python
def test_purchase_flow(self):
    # The code reads like natural language:
    HomePage(self.driver) \
        .open() \
        .search_for_product("Wiedźmin") \
        .click_first_result() \
        .add_to_cart() \
        .go_to_checkout() \
        .verify_product_in_summary("Wiedźmin")
```
### 2. Robust Page Object Model (POM)
Separation of Concerns: UI locators are strictly separated from test logic.

Encapsulation: Interactions with web elements are wrapped in business-logic methods (e.g., login_as_user() instead of find_element(...).send_keys(...)).

Maintainability: Changes in the UI require updates in only one place (the specific Page class), not in the test scripts.

### 3. Synchronization Strategy
Eliminated flaky tests by avoiding hardcoded time.sleep().

Utilizes Explicit Waits (WebDriverWait) to dynamically wait for elements to be present, clickable, or visible before interaction.

## 🛠 Tech Stack
Language: Python 3.x

Core Library: Selenium WebDriver

Test Runner: PyTest

Design Patterns: Page Object Model, Fluent Interface

Locators: Xpath / CSS Selectors

## 🚀 Getting Started

### Prerequisites
Python 3.8+ installed.

Chrome Browser installed.
### Installation
Clone the repository:

```bash
git clone [https://github.com/szymczykkrzysztof/Empik-Selenium-POM-Framework.git](https://github.com/szymczykkrzysztof/Empik-Selenium-POM-Framework.git)
cd Empik-Selenium-POM-Framework
```
Create a virtual environment (Recommended):

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```
Install dependencies:

```bash
pip install -r requirements.txt
```
Running Tests
To execute the full regression suite:

```bash
pytest .\Tests\tests.py -n 4
```

## ⚖️ Disclaimer & Ethics
This project is created for portfolio and educational purposes only. It is not affiliated with, endorsed by, or connected to Empik S.A. The tests are designed to be non-destructive and should be executed responsibly to avoid creating unnecessary load on the production environment.

