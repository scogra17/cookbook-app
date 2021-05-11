## Starting the app 
$ pipenv shell 
$ python app.py

## Adding to the db 

1. Create the new model in app.py 
2. In a python shell, run:
	$ from app import db
	$ db.create_all()
	$ from app import <Object name> 
	$ obj.<Object name>(<pk>='<pk_value>')
	$ db.session.add(obj)
	$ db.session.commit()

3. In a python shell, access by: 
	$ <Object name>.query.all()

## Troubleshooting 

### Css changes won't load in broswer
The browser is likely caching the old main.css. Click 'reload' while holding down the 'shift' key to do a full reload of the browser. 

## Heroku deployment
https://reverse-cook-app.herokuapp.com/

## DB changes
From pipenv:
$ python
>>> from app import db
>>> db.create_all()

Add to table represented by model [ClassName]:
>>> from app import [ClassName]
>>> obj = [ClassName]([fields])
>>> db.session.add(obj)
>>> db.session.commit()

Retrieving data:
https://docs.sqlalchemy.org/en/13/orm/query.html
>>> [ClassName].query.all()

## DB migrations 
https://flask-migrate.readthedocs.io/en/latest/

HOWTO: 
make change to db in app.py then: 
	$ pipenv shell 
	$ flask db migrate -m "<message>"
	$ flask db upgrade 

See tables:
$ db.metadata.tables

## DB browsing
SQLite: https://docs.sqlalchemy.org/en/13/orm/tutorial.html
Use DB broswer for SQLite: https://sqlitebrowser.org/dl/
