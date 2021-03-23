# backend-test-automation-postman
Backend test automation project with Postman and Newman for QA Automation Certification - Session 2

## CI/CD

Since storing API Keys in a repository is a bad practice, the below steps can be followed to execute the postman requests in a CI/CD pipeline:
1. First we need to get an Postman API Key to get the collection and env var URLs via Postman API, inside Postman there is an option to get them.
2. Then we will need to fetch & Get a `uid` of the collection and environment to construct the entire URLs.
3. Last to run Postman test in a CI/CD we can add a job which call Newman run commands, this job can be described in a .yml file with the URLS, newman commands, docker instructions, etc.



## For local execution you can follow the below steps:

### Pre-req
- [node js installed](https://nodejs.org/es/download/)


### Installation / How to

- Clone this repo
- Get Newman to run the Postman collections: `$ npm install -g newman`
- Install html reporter extra for Newman: `npm i newman-reporter-htmlextra`

### Run the collections using Newman

- From project's root folder run the command:
  `newman run <colelction_file>.postman_collection.json -e <env_file>.postman_environment.json -r htmlextra --reporter-htmlextra-title "<report_title>"`
  
  Example:
  `newman run temporary_block_list/temp_block_to_bl/Temporary_block_to_blacklist.postman_collection.json -e API_fraud_service.postman_environment.json -r htmlextra --reporter-htmlextra-title "Temporary Block List Regression Tests"`

- Output is an HTML report created inside the folder: reports