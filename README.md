# Postman API Automation Integration with Github Actions #

This repository is a demonstartion for POC for integrating postman tests with Github Actions. The tests are written in Postman and they are executed on virtual machine with the help of newman and newman-reporter-htmlextra.
Github Actions will trigger the project execution on every push to the main branch.You can also execute the project manually using workflow_disptach . The project runs on a scheduled time with the help of cron job.

The HTML report is archived and kept in the artifact section for the team to download it. Along with that they can view the report directly from the github page : https://devi1129.github.io/Phoenix-InWarranty-Flow/
The latest report is mailed to the team members using GMAIL SMTP

## Testing Coverage ##
1. Happy Flow Testing
2. Negative Testing and Edge Case Testing
3. Token Testing
4. Data Driven Testing with CSV
5. Schema Validation
6. Secrets Management with Github Secrets
   

## Tech Stack ##
1. Postman
2. Node.js 22v
3. Newman
4. Newman-Reporter-HTMLextra
5. Github Actions
6. Gmail SMTP
7. Github Pages
8. CSV for Data Driven Testing
9. AWS EC2 Instance for Self Hosted Github Runner

## Github Pages ##
You can directly view the latest test report of the postman test at the GitHub Page Link: https://devi1129.github.io/Phoenix-InWarranty-Flow/

## HTML Report ##
The Report will be created in the newman folder 
![Postman Report](https://raw.githubusercontent.com/devi1129/Phoenix-InWarranty-Flow/static-content/NewmanReport.png)

## Project Structure ##

```
Phoenix InWarranty Flow
├─ In warranty -flow Collection Copy.postman_collection.json #collection File
├─ QA.postman_environment.json  #Environment File
└─ testdata.csv #TestData File

```

## How to run the Project? ##
You can run the project on your local system for that:
1. Clone the project on local system : https://github.com/devi1129/Phoenix-InWarranty-Flow.git
2. Install Node.js and npm from :  ``` https://nodejs.org/en/download ```
3. Install Newman using : ``` npm install -g newman ```
4. Install Newman-reporter-htmlextra : ``` npm install -g newman-reporter-htmlextra ```
5. Run the newman command :
   ```
    newman run "In warranty -flow Collection Copy.postman_collection.json" \
          -e QA.postman_environment.json \
          -d testdata.csv \
          -r cli,htmlextra \
          --reporter-htmlextra-export ./newman/index.html
   ```


   






