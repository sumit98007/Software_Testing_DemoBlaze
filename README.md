# Software Testing Assignment

This repository contains three comprehensive testing assignments for the Demoblaze.com e-commerce website:

## 📁 Project Structure

```
├── part1-jmeter/          # JMeter Performance Testing
├── part2-selenium/        # Selenium Web Automation Tests
├── part3-cucumber/        # BDD Testing with Cucumber
└── README.md             # This file
```

## 🎯 Assignment Overview

### Part 1: JMeter Performance Testing (9 Marks)
- **Objective**: Test performance of https://demoblaze.com with varying user loads
- **Thread Groups**: 1, 10, 20, and 50 users
- **Test Duration**: 20 seconds with 10-second ramp-up
- **Scenarios**: Sign up, Login, Browse categories, Shopping cart
- **Deliverables**: 
  - JMeter test plan (.jmx file)
  - Performance analysis report (max 2 pages)
  - Screenshots of results

### Part 2: Selenium Web Automation (22 Marks)
- **Objective**: Automated testing using Selenium WebDriver with Java
- **Framework**: Maven project with JUnit
- **Integration**: SpiraPlan for test management
- **Test Classes**: 6 classes covering all user workflows
- **Deliverables**:
  - Complete Maven project
  - SpiraPlan integration
  - PDF test report from SpiraPlan

### Part 3: BDD Testing with Cucumber (9 Marks)
- **Objective**: Behavior-driven testing using Gherkin language
- **Framework**: Cucumber with Selenium WebDriver
- **Scenarios**: Sign up, Login, Logout workflows
- **Deliverables**:
  - Feature files (.feature)
  - Step definitions
  - Test runner configuration

## 🚀 Getting Started

### Prerequisites
- Java 8 or higher
- Maven 3.6+
- IntelliJ IDEA (for Selenium and Cucumber)
- Apache JMeter (for performance testing)
- Chrome browser and ChromeDriver

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd software-testing
   ```

2. **For Part 1 (JMeter)**:
   - Download and install Apache JMeter
   - Import the test plan from `part1-jmeter/`
   - Follow the execution guide

3. **For Part 2 (Selenium)**:
   - Open `part2-selenium/` in IntelliJ IDEA
   - Maven will automatically download dependencies
   - Configure SpiraPlan credentials
   - Run tests from IntelliJ

4. **For Part 3 (Cucumber)**:
   - Open `part3-cucumber/` in IntelliJ IDEA
   - Run the test runner class
   - View Cucumber reports

## 📊 Test Website
All tests target: **https://demoblaze.com**

## 📝 Documentation
Each part contains detailed documentation:
- Setup instructions
- Execution guides
- Report templates
- Troubleshooting tips

## 🤝 Contributing
This is an academic assignment. Please follow the assignment specifications exactly.

## 📄 License
Academic use only.

---
**Note**: This assignment covers comprehensive software testing methodologies including performance testing, automated UI testing, and behavior-driven development.
