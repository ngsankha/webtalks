#WebTalks

One place for all the web conferences

##Setup

Clone the repository from 

	git clone https://github.com/sankha93/webtalks

Make sure python version is 2.7 and install App Engine SDK for python

Create [virtualenv][0] 

	virtualenv env

Activate the virtualenv environment

	source ./env/bin/activate

Install packages (Only Django!). Will need to copy most packages, App Engine doesn't support pip or easy_install
	
	pip install -r requirements.txt

To run the development server

	cd src/webtalks
	python manage.py runserver

To run app engine development server, from the **src/** dir run

	dev_appserver.py .

To deploy to appengine, from the **src/** dir run. I'd suggest we not use git for deployment on App Engine.
	
	appcfg.py update webtalks
	
To avoid entering password again and again, use this (more details on [Password-less Login][1])

	appcfg.py --oauth2 update myapp/


##Todo
- Setup Local DB and Google Cloud SQL Workflow
- Script to deploy to App Engine and Github
- DB Migrations with South?

[0]: https://pypi.python.org/pypi/virtualenv
[1]: https://developers.google.com/appengine/docs/python/tools/uploadinganapp#Python_Password-less_login_with_OAuth2