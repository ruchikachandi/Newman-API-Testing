# API Testing — JSONPlaceholder REST API

## About this project
This is my Week 2 API testing project where I built an automated API test suite using Postman and Newman. I tested a REST API covering all main HTTP methods and automated the execution using Newman CLI with GitHub Actions for CI/CD integration.

## Tools Used
- Postman — writing and organising API tests
- Newman — running tests from command line
- newman-reporter-htmlextra — HTML test reports
- GitHub Actions — automated test execution on push

## APIs Tested

| Method | Endpoint | What I tested |
|--------|----------|---------------|
| GET | /posts | Returns array, not empty, has required fields |
| GET | /posts/1 | Returns correct post, id matches |
| POST | /posts | Status 201, returns new id, title matches |
| PUT | /posts/1 | Status 200, record updated correctly |
| DELETE | /posts/1 | Status 200, returns empty object |

## Test Coverage
- Status code validation on all requests
- Response time under 2 seconds
- Response body field validation
- Data type checks
- Empty response validation

## How to Run Locally
1. Install Newman:
   npm install -g newman newman-reporter-htmlextra

2. Run tests:
   newman run postman/jsonplaceholder-collection.json

3. Generate HTML report:
   newman run postman/jsonplaceholder-collection.json -r htmlextra --reporter-htmlextra-export report.html

## CI/CD
Tests run automatically on every push to main branch via GitHub Actions. Report is saved as artifact.

## What I Learned
- How to write JavaScript test scripts in Postman
- How to run collections from command line using Newman
- How to generate HTML reports for stakeholders
- How to integrate API tests into a CI/CD pipeline using GitHub Actions
