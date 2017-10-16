#### Prerequisites ####
Be sure you have the following installed on your development machine
  * Python >= 2.7
  * pip
  * virtualenv
  * Database:
    * Postgres
        *Create a database user and a database to use for development. Ensure that the default DATABASES url string in panconsumer/settings.py corresponds to your database.

#### Quickstart ####
* To setup a local development environment:
	<code>
	virtualenv panenv # Install virtualenv for panconsumer project 
	source panenv/bin/activate # Activate virtualenv 
	</code>

* Change to project directory:
	<code> cd api-consumer/panconsumer </code>

* For Changing login data:
    Stop the running api, change directory by cd api-consumer/panconsumer/panconsumer/settings.py. Change EMAIL, PASSWORD and save the changes.

* For installing all project related dependencies on virtual environment you have to install it from requirement.txt. 

* Install dependencies from requirement.txt by typing following command
	<code> pip install --upgrade -r requirements.txt </code>

* Setup database tables
	<code> python manage.py migrate </code>	

* Run the web application locally
	<code> python manage.py runserver </code>

#### Create Report ####

##### Create Report Manually ##### 
* For creating report manually for testing purpose, open Postman or any other Rest-API testing app. Make resource hit link POST http://127.0.0.1:8000/v1/report/ and then click on send.

* Report will be generated in directory api-consumer/panconsumer/.

##### Create Report Using Cron #####
* Add cron job by typing command:
	<code>python manage.py crontab add</code>
* To see added cron job type command:
	<code>python manage.py crontab show</code>
* To remove cron job type command:
	<code>python manage.py crontab remove</code>
*  After adding cron job, api is executed and you will see generated report in panconsumer folder(Ex: Lab_Instance_Report20171013-193501.csv). To stop api for further generating report, remove cron job.
*  By default, API is set to generate report at an interval of 1 minute. To change the report generation interval, go to directory
 cd api-consumer/panconsumer/panconsumer/settings.py. Under CRONJOBS alter the cronjob interval accordingly.

  



