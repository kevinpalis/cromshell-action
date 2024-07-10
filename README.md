# Cromshell Action


This GitHub Action allows you to run [Cromshell](https://github.com/broadinstitute/cromshell) commands directly within your GitHub workflows. Cromshell is a command-line tool for interacting with the Cromwell workflow execution engine.

## Features

- Easily integrate Cromshell commands into your CI/CD pipeline
- Supports all Cromshell commands
- Runs directly on the host machine, not in a Docker container

## Inputs

### `command`

**Required** The Cromshell command to execute.

## Example Usage

Add the following to your workflow file to use this action:

```yaml
name: Run Cromshell Command

on: [push]

jobs:
  run-cromshell:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout repository
      uses: actions/checkout@v2

    - name: Run Cromshell Action
      uses: kevinpalis/cromshell@v1
      with:
        command: 'cromshell -h'