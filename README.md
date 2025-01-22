# iOS Appium Workflow Action

This custom GitHub Action allows you to run Appium tests on iOS devices with Maven.

## Inputs

### `java_version`
- **Description**: The version of Java to install.
- **Required**: No
- **Default**: `22`

### `node_version`
- **Description**: The version of Node.js to install.
- **Required**: No
- **Default**: `21`

### `test_name`
- **Description**: The name of the test suite.
- **Required**: Yes

### `scripts`
- **Description**: The Maven commands to execute the test.
- **Required**: Yes

## Example Usage

```yaml
name: Run iOS Appium Tests
on: [push]

jobs:
  run-tests:
    runs-on: macos-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Run Appium Tests
        uses: ThangNguyen0495/execute-appium-ios-test@v1.0.0
        with:
          java_version: '17'
          node_version: '14'
          test_name: 'MyAppTestSuite'
          scripts: 'mvn test -DsuiteFile=TestNG.xml'
