# 📘 Postman API Testing Portfolio

Welcome to my **Postman API Testing Portfolio**, a hands-on showcase of my API testing skills using Postman. This project covers:

* ✅ **Functional Testing** (Positive & Negative scenarios)
* 🔁 **Data-Driven Testing** (with JSON file)
* 🚀 **Performance Testing** (Register & Login APIs)
* 🔐 **Security Testing** (Brute Force Simulation)
* ⚙️ **CI/CD Integration with GitHub Actions** (for Functional and Data-Driven collections)
* 
----

## 📁 Project Structure

```
postman-api-testing-portfolio/
│
├── .github/workflows/
│   └── postman-ci.yml                 # GitHub Actions workflow for CI/CD
│
├── 1-FunctionalTests/
│   ├── functional_collection.json     # Collection for Functional API Tests with positive and negative scenarios
│   └── functional_environment.json    # Environment for Functional Tests
│
├── 2-DataDrivenTests/
│   ├── data.json                      # Test data for data-driven testing
│   ├── data_driven_collection.json   # Collection for Data-Driven Tests
│   └── data_driven_environment.json  # Environment for Data-Driven Tests
│
├── 3-PerformanceTests/
│   ├── performancetest-data.json     # Data for performance test scenarios
│   └── performancetest_collection.json  # Collection for Performance Testing
│
├── 4-SecurityTests/
│   ├── bruteforce-data.json              # Invalid password data set (brute force)
│   └── bruteforcesimulation_collection.json  # Brute force simulation collection
│
├── test results/
│   ├── functional_report.html              # Functional test report
│   ├── data-driven_report.html            # Data-driven test report
│   ├── registerUser-loadTest-report.html  # Performance: Register API test
│   ├── validUserLogin-loadTest-report.html# Performance: Login API test
│   └── bruteforcetest-report.html         # Security: Brute force attack simulation
│
└── README.md                              # Documentation and usage instructions

```
---

## ✅ Functional Testing

*Tool: Postman
*Tests: Positive and Negative test scenarios
* Covers API behavior validations like:
  Positive Tests: Valid Login, Valid Contact Add, Update Contact, Delete Contact  etc.
  Negative Tests: Invalid Login, Missing Fields, Unauthorized Access, Invalid format etc.
* Collection: `functional_collection.json`
* Environment: `functional_environment.json`
* Run with: `newman` via GitHub Actions (Included in `postman-ci.yml` workflow)
* Report: See test results/functional_report.html
---

## 🔁 Data-Driven Testing

*Tool: Postman + Collection Runner with JSON file
*Tested API: Add Contact
*Collection: data_driven_collection.json
*Data Source: data/data.json
*Environment: data_driven_environment.json
*Assertions: Validates fields like firstName, email, etc.
*Run with: GitHub Actions using Newman + JSON (Included in `postman-ci.yml` workflow)
*Report: See testresults/data-driven_report.html

---

## 🚀 Performance Testing

* Two high-load scenarios tested using Postman's built-in **Performance Run**:

### 1. **Register API Load Test**

* Endpoint: `/users`
* 20 unique users registered using `performancetest-data.json`
* Validated with 200/201 status checks, response time checks
* **Tool Used:** Postman → Collection → Performance tab
* **Result:** Attached in test results/registerUser-loadTest-report.html`

### 2. **Valid Login Load Test**

* Endpoint: `/users/login`
* Used 20 valid user credentials
* Test focuses on response time consistency and server throughput
* **Tool Used:** Postman → Collection → Performance tab
* **Result:** Attached in test results/validUserLogin-loadTest-report.html

---

## 🔐 Security Testing: Brute Force Simulation

* Simulates brute force login attempts using one valid email and 20 invalid passwords
* Goal: Detect whether the system blocks or rate-limits repeated invalid logins
* Collection: `bruteforcesimulation_collection.json`
* Data File: `bruteforce-data.json`
* **Tool Used:** Postman → Collection → Performance tab(upload the json file before starting run)
* **Result:** Attached in test results/bruteforcetest-report.html ``

### 🔍 Observations:

* Most responses returned quickly with error messages.
* No lockout or CAPTCHA detection was observed — potential improvement area for the API.

---

## ⚙️ CI/CD with GitHub Actions

* Automated test execution for Functional & Data-Driven tests
* Trigger: Every push to `main` branch

### 🔧 Workflow: `.github/workflows/postman-ci.yml`

Includes:

* `newman` run for both collections
* Generation of **HTML reports**
* Uploading test reports as workflow artifacts

---

## 📝 How to Run Locally

### Functional Collection

```
newman run collections/functional_collection.json \
    -e environments/functional_environment.json \
    -r cli,html --reporter-html-export reports/functional-report.html
```

### Data-Driven Collection

Use Postman Collection Runner:

* Select: `data_driven_collection.json`
* Environment: `data_driven_environment.json`
* Data File: `data/data.json`

### Performance & Security

Run using Postman’s Performance Run Tab (manually):

* `performancetest_collection.json`
* `bruteforcesimulation_collection.json`

---
💡 **Summary**
This API Testing portfolio demonstrates:
*Real-world test design with assertions
*Data-driven logic
*Basic performance and security concepts
*CI/CD with GitHub Actions
*Professional organization and documentation

🙋‍♀️ **About Me**

Reshma Sajeev🧪 ISTQB Certified | ✅ Postman Student Expert 🔗 https://www.linkedin.com/in/reshma-sajeev-889b7215b/
---

> ⭐ *This repository is part of my personal QA portfolio to demonstrate hands-on experience in API Testing using Postman, Data-driven strategies, and GitHub-based CI/CD.*
