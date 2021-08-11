# docker-compose-sample

This quick-start guide demonstrates how to use Docker Compose to set up and run a simple Django/PostgreSQL app.

1. Create the Django project by running the docker-compose run command:

 sudo docker-compose run web django-admin startproject composeexample .
 
This instructs Compose to run django-admin startproject composeexample in a container, using the web service’s image and configuration. Because the web image doesn’t exist yet, Compose builds it from the current directory, as specified by the build: . line in docker-compose.yml.

Once the web service image is built, Compose runs it and executes the django-admin startproject command in the container. This command instructs Django to create a set of files and directories representing a Django project.

2. In your project directory, edit the composeexample/settings.py file:

ALLOWED_HOSTS = ['*']
   
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'postgres',
        'USER': 'postgres',
        'PASSWORD': 'postgres',
        'HOST': 'db',
        'PORT': 5432,
    }
}

3. Start services:
docker-compose up -d
