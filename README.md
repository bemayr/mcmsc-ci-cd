# mcmsc-ci-cd
Go/Microservice Exercise for Continuous Delivery and Automation Course at FH Hagenberg

## Running
```bash
# Set the Environment Variables (they are used for docker-compose as well)
export APP_DB_USERNAME=postgres
export APP_DB_PASSWORD=postgres
export APP_DB_NAME=postgres

# Start the Database
docker-compose up -d

# Test the Go Application
go test -v
```