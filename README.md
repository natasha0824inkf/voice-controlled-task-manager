# voice-controlled-task-manager
A voice controlled to-do list - allows you to add, check off or delete tasks using voice command 

## Continuous Integration

This repository uses GitHub Actions for continuous integration. The workflow is defined in the `.github/workflows/main.yml` file and includes the following steps:

- **Checkout repository**: This step uses the `actions/checkout` action to clone the repository code into the runner.
- **Set up Node.js**: This step uses the `actions/setup-node` action to set up the Node.js environment based on the specified version.
- **Install dependencies**: This step runs `npm install` to install all the dependencies listed in the `package.json` file.
- **Run tests**: This step runs `npm test` to execute the tests defined in your project.

### What is a .yml file?

A `.yml` file, also known as a YAML file, is a human-readable data serialization standard that is often used for configuration files. In the context of GitHub Actions, `.yml` files are used to define workflows, which specify a series of steps to be executed on specified events, such as code pushes or pull requests.

### How to Set Up the Workflow

1. **Create a new workflow file**: Navigate to the `.github/workflows/` directory in your repository and create a new file named `main.yml`.
2. **Define the workflow**: Add the following content to the `main.yml` file:

```yaml
name: CI

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v2

      - name: Set up Node.js
        uses: actions/setup-node@v2
        with:
          node-version: '14'

      - name: Install dependencies
        run: npm install

      - name: Run tests
        run: npm test
Commit the changes: Commit the new workflow file to the repository. This will trigger the workflow on every push and pull request to the main branch.
By following these steps, you set up a continuous integration workflow that helps automate the process of testing your code whenever changes are made.



To test, rigger the Workflow Manually:

Make a small change in your repository (e.g., update the README.md file) and commit the changes to the main branch. This will trigger the workflow as defined by the on: push event in the main.yml file.
Check the Workflow Status:

Go to the Actions tab in your repository.
You should see the workflow run listed there. Click on it to view the details and check if all steps have completed successfully.
Review the Logs:

Click on the specific run to see the logs for each step. Ensure that all steps (checkout, setup Node.js, install dependencies, and run tests) completed without errors.
If everything runs successfully, your workflow is set up correctly. If there are error
