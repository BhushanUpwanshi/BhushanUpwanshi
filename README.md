<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.svg">
  <img alt="Bhushan Upwanshi, SDET. Test automation for web, API and event-driven systems." src="assets/banner-light.svg" width="100%">
</picture>

<p>
  <a href="https://www.linkedin.com/in/bhushanupwanshi"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-bhushanupwanshi-0A66C2?style=flat-square"></a>
  <a href="mailto:shanupb9@gmail.com"><img alt="Email" src="https://img.shields.io/badge/Email-shanupb9%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white"></a>
  <a href="https://www.npmjs.com/package/playwright-standalone"><img alt="npm" src="https://img.shields.io/npm/v/playwright-standalone?style=flat-square&logo=npm&label=playwright-standalone&color=CB3837"></a>
</p>

I'm an SDET at Bajaj Finserv Health in Pune, with 2+ years testing health-insurance web platforms and the microservices behind them. Most of what I build is test automation in Playwright, TypeScript and Java that the team can trust to run on every release.

## At work

- Co-architected the move from Java/Selenium to Playwright + Node.js. Full regression went from **2 hours to 40 minutes**, so it now runs every release instead of every sprint.
- Wrote the framework's helper layer: a click that waits for its API response, condition-based waits, soft assertions, and handlers for feature toggles and files. It removed the old suite's timing-based flaky failures, and other teams now use its DB, API and messaging modules.
- Built API regression of **15,000+ data-driven validations across 5 microservices** in Java, TestNG and REST Assured.
- Built a Kafka testing framework on my own in Jest and Node.js. Adding a new topic only takes a config entry.
- Write Azure DevOps YAML pipelines that run suites in parallel and in shards and publish Allure and CTRF reports. Production monitors for the main user flows raise ELK alerts when they fail.

Here is how a Kafka test runs. The code stays at work, so this is only the pattern:

```mermaid
flowchart LR
    T[Test runs SQL<br/>in Oracle] --> TR[DB trigger fires]
    TR --> J[JMS]
    J --> K[Kafka topic]
    K --> V[Framework reads the<br/>message and checks it]
    V --> M[(MongoDB<br/>event log)]
```

## Projects

### [playwright-standalone](https://github.com/BhushanUpwanshi/playwright-standalone)

[![CI](https://github.com/BhushanUpwanshi/playwright-standalone/actions/workflows/ci.yml/badge.svg)](https://github.com/BhushanUpwanshi/playwright-standalone/actions/workflows/ci.yml)
[![npm](https://img.shields.io/npm/v/playwright-standalone?style=flat-square&color=CB3837)](https://www.npmjs.com/package/playwright-standalone)

An npm package that runs Playwright suites without a test runner. Playwright records one video per page, so a test that switches tabs leaves you with several files and frozen frames. This package records **one continuous video that follows the active tab** and stops at the step that failed. It also shortens long idle waits in the video, recovers when a page crashes mid-run, and writes Allure and CTRF reports itself.

`npm i playwright-standalone` is the whole setup: no peer dependencies, no system ffmpeg, no separate browser install. 55 unit tests run in GitHub Actions on Node 20, 22 and 24.

### [playwright-e2e-framework](https://github.com/BhushanUpwanshi/playwright-e2e-framework)

[![CI](https://github.com/BhushanUpwanshi/playwright-e2e-framework/actions/workflows/ci.yml/badge.svg)](https://github.com/BhushanUpwanshi/playwright-e2e-framework/actions/workflows/ci.yml)

A Playwright + TypeScript framework where the page objects don't import anything from a test runner. The same screens, locators and test data drive `@playwright/test` specs and runner-less journeys built on playwright-standalone. A build script fails if anything in `src/` imports the runner, so the separation can't quietly break. Tests run against Sauce Demo and the-internet.

### In progress

**restassured-api-framework**: an API test framework in Java, REST Assured, TestNG and Maven, built against public demo APIs. It goes up here when CI is green.

## Tools

**Languages**<br/>
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square)

**UI and API testing**<br/>
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=flat-square)
![Selenium WebDriver](https://img.shields.io/badge/Selenium_WebDriver-43B02A?style=flat-square&logo=selenium&logoColor=white)
![REST Assured](https://img.shields.io/badge/REST_Assured-5B8C3A?style=flat-square)
![TestNG](https://img.shields.io/badge/TestNG-E34F26?style=flat-square)
![Jest](https://img.shields.io/badge/Jest-C21325?style=flat-square&logo=jest&logoColor=white)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=flat-square&logo=postman&logoColor=white)

**Messaging and data**<br/>
![Apache Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![JMS](https://img.shields.io/badge/JMS-6E4C13?style=flat-square)
![Oracle](https://img.shields.io/badge/Oracle-F80000?style=flat-square)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)

**CI/CD and infrastructure**<br/>
![Azure DevOps](https://img.shields.io/badge/Azure_DevOps-0078D7?style=flat-square)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/AKS-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Helm](https://img.shields.io/badge/Helm-0F1689?style=flat-square&logo=helm&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-C71A36?style=flat-square&logo=apachemaven&logoColor=white)

**Reporting and monitoring**<br/>
![Allure](https://img.shields.io/badge/Allure-FF6A00?style=flat-square)
![CTRF](https://img.shields.io/badge/CTRF-555555?style=flat-square)
![ELK Stack](https://img.shields.io/badge/ELK_Stack-005571?style=flat-square&logo=elasticsearch&logoColor=white)

## Get in touch

Open to SDET and QA automation roles in Pune or remote. The quickest way to reach me is [LinkedIn](https://www.linkedin.com/in/bhushanupwanshi) or [email](mailto:shanupb9@gmail.com).

<sub>^..^</sub>
