# Log Analysis Project
This is a project for Udacity's [Full Stack Web Developer Nanodegree](https://www.udacity.com/course/full-stack-web-developer-nanodegree--nd004)
## Project Description:
Your task is to create a reporting tool that prints out reports (in plain text) 
based on the data in the database. This reporting tool is a Python program 
using the psycopg2 module to connect to the database.
### Questions to Answer:
1. **What are the most popular three articles of all time?** Which articles have been 
accessed the most? Present this information as a sorted list with the most popular 
article at the top.
2. **Who are the most popular article authors of all time?** That is, when you sum up 
all of the articles each author has written, which authors get the most page views? 
Present this as a sorted list with the most popular author at the top.
3. **On which days did more than 1% of requests lead to errors?**  The log table 
includes a column status that indicates the HTTP status code that the news site sent 
to the user's browser. 

## This Project Requires a Bit of Setup:
This project is run in a virutal machine created using Vagrant so there are a few steps
to get set up:
#### Installing the dependencies and setting up the files:
1. Install [Vagrant](https://www.vagrantup.com/)
2. Install [VirtualBox](https://www.virtualbox.org/)
3. Download the vagrant setup files from [Udacity's Github](https://github.com/udacity/fullstack-nanodegree-vm)
These files configure the virtual machine and install all the tools needed to run this project.
4. Download the database setup: [data](https://d17h27t6h515a5.cloudfront.net/topher/2016/August/57b5f748_newsdata/newsdata.zip)
5. Unzip the data to get the newsdata.sql file.
6. Put the newsdata.sql file into the vagrant directory
7. Download this project: [log analysis](https://github.com/anish8129/Logs_Analysis.git)
8. Upzip as needed and copy all files into the vagrant directory into a folder called log_analysis
#### Start the Virtual Machine:
9. Open Terminal and navigate to the project folders we setup above.
10. cd into the vagrant directory
11. Run ``` vagrant up ``` to build the VM for the first time.
12. Once it is built, run ``` vagrant ssh ``` to connect.
13. cd into the correct project directory: ``` cd /vagrant/log_analysis ```
#### Load the data into the database:
14. Load the data using the following command: ``` psql -d news -f newsdata.sql ```

## Run The Project Already!
1. You should already have vagrant up and be connected to it. 
2. If you aren't already, cd into the correct project directory: ``` cd /vagrant/log_analysis ```
3. Run ``` python loganalysisdb.py ```

Generating this information will take several seconds, but will now start loading. 

## Expected Output: 
    Calculating Results...
    TOP THREE ARTICLES BY PAGE VIEWS:
        (1) "Candidate is jerk, alleges rival" with 338647 views
        (2) "Bears love berries, alleges bear" with 253801 views
        (3) "Bad things gone, say good people" with 170098 views
    TOP THREE AUTHORS BY VIEWS:
        (1) Ursula La Multa with 507594 views
        (2) Rudolf von Treppenwitz with 423457 views
        (3) Anonymous Contributor with 170098 views
    DAYS WITH MORE THAN 1% ERRORS:
        July 17, 2016 -- 2.3% errors

