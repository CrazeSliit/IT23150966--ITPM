# SwiftTranslator – Playwright Automation Testing

## Project Information

* **Course:** IT3040 – IT Project Management (Semester 2)
* **Student ID:** IT23150966
* **Assignment:** Playwright Automation Testing (TypeScript)
* **System Under Test:** [https://www.swifttranslator.com](https://www.swifttranslator.com)
* **Tech Stack:** Playwright, TypeScript, Node.js
* **Design Pattern:** Page Object Model (POM)

---

## Project Overview

This project implements automated functional and UI testing for **SwiftTranslator**, a web-based application that performs real-time **Singlish to Sinhala transliteration**.

The test suite validates correct transliteration behavior, system robustness under invalid inputs, and real-time UI responsiveness using Playwright with TypeScript.

---

## Test Coverage Summary

| Test Category             | Specification File            | No. of Tests | Description                          |
| ------------------------- | ----------------------------- | ------------ | ------------------------------------ |
| Positive Functional Tests | `positive-functional.spec.ts` | 24           | Validates correct transliteration    |
| Negative Functional Tests | `negative-functional.spec.ts` | 10           | Evaluates robustness and limitations |
| UI Behavior Tests         | `ui.spec.ts`                  | 3            | Verifies real-time UI behavior       |

**Total Test Cases:** 37

---

## Project Structure

```
swifttranslator-playwright/
│
├── tests/
│   ├── positive-functional.spec.ts
│   ├── negative-functional.spec.ts
│   └── ui.spec.ts
│
├── pages/
│   └── translator.page.ts
│
├── test-data/
│   ├── positive-functional.json
│   ├── negative-functional.json
│   └── ui-tests.json
│
├── screenshots/
├── playwright-report/
├── test-results/
│
├── playwright.config.ts
├── package.json
├── package-lock.json
├── tsconfig.json
└── README.md
```

---

## Installation and Setup

### Prerequisites

* Node.js (v18 or higher)
* npm
* Git

### Install Dependencies

```powershell
npm install
```

### Install Playwright Browsers

```powershell
npx playwright install
```

---

## Test Execution

### Run All Tests

```powershell
npm test
```

### Run Individual Test Suites

```powershell
npm run test:positive
npm run test:negative
npm run test:ui
```

### Run Tests by Browser

```powershell
npm run test:chromium
npm run test:firefox
npm run test:webkit
```

### Debug and Interactive Modes

```powershell
npm run test:ui-mode
npm run test:headed
npm run test:debug
```

### Run a Specific Test Case

```powershell
npx playwright test -g "Pos_Fun_0001"
npx playwright test -g "Neg_Fun_0003"
```

---

## Test Reporting

### HTML Report

```powershell
npm run report
```

or

```powershell
npx playwright show-report
```

The report includes:

* Test execution results
* Failure screenshots
* Execution duration
* Detailed logs

---

## Test Design and Logic

### Positive Functional Tests

* Validate correct Singlish-to-Sinhala transliteration
* Data-driven using JSON
* Output compared against expected Sinhala text
* Screenshot captured on failure

**Example:**

* Input: `mama gedhara yanavaa`
* Expected Output: `මම ගෙදර යනවා`

---

### Negative Functional Tests

* Test system behavior with incorrect or inconsistent inputs
* Designed to expose system limitations
* Soft assertions used to continue execution
* Failures are acceptable and documented

**Example:**

* Input: `MaMa GeDaRa YaNaVa`
* Expected Output: `මම ගෙදර යනවා`
* Result: Fail (case normalization not supported)

---

### UI Behavior Tests

* Real-time output updates during typing
* No manual trigger required
* Input clear functionality
* Page responsiveness and stability
* Multiple conversion consistency

---

## Automation Best Practices Applied

* Page Object Model for maintainability
* Data-driven testing using external JSON files
* Clear step-by-step comments in test scripts
* Automatic screenshot capture on failures
* HTML and JSON reporting
* Strict TypeScript configuration

---

## Configuration Overview

### `playwright.config.ts`

* Browser configuration
* Timeouts
* Reporters
* Screenshot and video settings
* Parallel execution

### `tsconfig.json`

* ES6 target
* Strict type checking
* Node module resolution

---

## Sample Test Data Format

```json
[
  {
    "tcId": "Pos_Fun_0001",
    "input": "mama gedhara yanavaa",
    "expectedOutput": "මම ගෙදර යනවා"
  }
]
```

---

## Troubleshooting

**Browsers not installed**

```powershell
npx playwright install
```

**Timeout issues**

```ts
timeout: 60000
```

**Dependency errors**

```powershell
npm install
```

**TypeScript validation**

```powershell
npx tsc --noEmit
```

---

## Submission Checklist

* Page Object Model implemented
* External JSON test data
* Screenshots on failure
* Executable via `npm test`
* Proper folder structure
* TypeScript with strict typing
* README with setup and execution details

---

## Submission Details

* **GitHub Repository:** Public
* **ZIP File Name:** `IT23243026_PlaywrightAutomation.zip`
* Includes all source files and configuration

---

## License

This project is developed strictly for academic purposes as part of a university assignment.

---

## Conclusion

This automation project demonstrates structured test design, maintainable architecture, and practical Playwright automation aligned with university assessment requirements.

---
