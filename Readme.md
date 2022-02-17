
# Readme

This repository contains a completed test task for the position "Python developer (Django, DRF)"

## issue of task

**Task**: To design and develop an API for a user survey system.

Functionality for the system administrator:

- authorization in the system (registration is not required)
- adding/changing/ deleting polls. Survey attributes: name, start date, end date, description. After creation, the "start date" field of the survey cannot be changed
- adding/changing/deleting questions in the survey. Question Attributes: question text, question type (answer in text, answer with a choice of one option, answer with a choice of several options)

Functionality for system users:

- getting a list of active polls
- passing the survey: surveys can be conducted anonymously, a numeric ID is transmitted to the API as a user ID, which stores the user's answers to questions; one user can participate in any number of surveys
- receiving surveys completed by the user with details on the answers (what is selected) by the unique user ID

Use the following technologies: Django 2.2.10, Django REST framework.

The result of the task:

- application source code in github (only on github, public repository)
- instructions for deploying the application (in docker or locally)
- API documentation

## set up

1. Clone git rep.

    ```bash
    git clone git@github.com/nurlan5t/survey_test_task.git
    ```

2. install docker и docker-compose

3. Running docker containers in the background

    ```bash
    docker-compose up --build -d
    ```

4. Exec migrations

    ```bash
    docker-compose run django_web /usr/local/bin/python manage.py migrate
    ```

5. Create superuser

    ```bash
    docker-compose run django_web /usr/local/bin/python manage.py createsuperuser
    ```

6. Runserver
   cd survey_test_task
    ```bash
    docker-compose -f docker-compose.yml up
    ```


## Use

App running and available at 8001

### Functionality for the system administrator:

The functionality for the system administrator is fully implemented on the django admin panel.

1. go to url http://127.0.0.1:8001/admin
2. we log in under the administrator we created
3. in `polls/quizzes` we can add / change / delete polls.


### Functionality for system users:

The functionality for the users of the system is implemented in the form of an API.

API documentation is located at http://127.0.0.1:8001/swagger