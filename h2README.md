Creating a Python Django project:

1. first upgrade pipenv: >>pip install --user --upgrade pipenv

2. Make new folder: >>mkdir proj_name

3. Go into the folder >>cd proj_name

4. Install Django >>pipenv install django

5. Run shell>>pipenv shell

6.Create new project  >>django-admin startproject firstProject

7. black command to format generated code >> black 

8. Migrate >>manage.py migrate

9. Run server >>manage.py runserver

(Now complete your project. You can go to the project and add the template folders to include all your html files and static folder to add all you css files. You need to include the directory to template and static folder in your seetting.py file)


Setting Up Heroku
 1. Signup & sign-in Heroku to click the link below: https://heroku.com/

2. Create a Heroku App for Heroku web service by clicking on Create new App and provide the unique name.

3. Download and install Heroku CLI: https://devcenter.heroku.com/articles/heroku-cli

4. Open CMD, and do heroku login to login into the Heroku CLI

5. Navigate to your project folder.



Modifying the Django Project with Heroku dependencies:
1. create Procfile to the folder that has manage.py file and add following command to it:

web: gunicorn showtime.wsgi --log-file -

2. We need a python HTTP server(Python WSGI HTTP Server) on Heroku service. Execute the following command:

pipenv install gunicorn django-heroku psycopg2-binary

3. Activate django-heroku setting by: 

 Open settings.py and add to file and add the following command:

 import django_heroku (preferably below import os)

At the end of the setting file: Activate Django-Heroku settings except logging by the following command:

django_heroku.settings(locals(), logging=False)



Pushing the project to Heroku using git:
>> git init

>> git status

>> git add . or git add --all

>> git commit -m "ready"

>> heroku git:remote -a nepaltime

>>git push heroku master

