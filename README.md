# mcmsc-ci-cd
Go/Microservice Exercise for Continuous Delivery and Automation Course at FH Hagenberg

[![Test and Build Application](https://github.com/bemayr/mcmsc-ci-cd/actions/workflows/test-build.yml/badge.svg)](https://github.com/bemayr/mcmsc-ci-cd/actions/workflows/test-build.yml)

## Running
```bash
# Set the Environment Variables (they are used for docker-compose as well)
export APP_DB_USERNAME=postgres
export APP_DB_PASSWORD=postgres
export APP_DB_NAME=postgres

# Start the Database
docker-compose up -d

# Test the Go Application (inside products/)
go test -v

# Run the Go Application (inside products/)
go build -o build/app && ./build/app
```
