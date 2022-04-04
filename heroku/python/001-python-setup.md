# Setup to Integrate a Python project with Heroku

## Install ```gunicorn``` to your Python Application
``` 
pip install gunicorn
```
### Add gunicorn to your ```requirements.txt```
```
pip freeze > requirements.txt
```

## Define a ```Procfile```
- Create a file called as ```Procfile``` in the root directory of your project. <br>
*Note* : The name of the file should start with a **capital P**.
- Add the following command into the ```Procfile```
```
web: gunicorn app:app
```

## FAQs
### What is Gunicorn?
It's a Web Server Gateway Interface (WSGI) which allows us to run a webserver for Python. It is compatible with various frameworks like Flask and Django to help developers streamline web application development.

### What is a ```Procfile```?
It's the entry point to the heroku application. It tells heroku how to run the app. In the example above it's running a command called gunicorn which will run our app server. This command can be any command which is entry point.

## References
1. https://devcenter.heroku.com/articles/python-gunicorn
