# Exercise 3

## References
- Repository: https://github.com/bemayr/mcmsc-ci-cd/
- This documentation file: https://github.com/bemayr/mcmsc-ci-cd/blob/main/_documentation/Exercise%203.md

## GitHub Actions

The following file produces the output beneath:

```yml
name: Test and Build Application

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  test-build:
    runs-on: ubuntu-latest
    env:
      APP_DB_USERNAME: postgres
      APP_DB_PASSWORD: postgres
      APP_DB_NAME: postgres
    steps:
    - name: Setup Go environment ๐
      uses: actions/setup-go@v3.2.0

    - name: Checkout ๐๏ธ
      uses: actions/checkout@v3

    - name: Start Docker Containers ๐
      run: docker-compose up -d

    - name: Test ๐งช
      run: go test -v
      working-directory: products

    - name: Build ๐ ๏ธ
      run: go build -o build/app
      working-directory: products
```

![GitHub Actions Successful Run](./Exercise%203.png)

## Status Badge

The status badge is included like the following:

```markdown
[![Test and Build Application](https://github.com/bemayr/mcmsc-ci-cd/actions/workflows/test-build.yml/badge.svg)](https://github.com/bemayr/mcmsc-ci-cd/actions/workflows/test-build.yml)
```
