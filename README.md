# Django Docker

Dockerizing a Django application

## Create Dockerfile

```
FROM python:3.10-slim-buster

WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

COPY . .

CMD ["python3", "manage.py", "runserver", "0.0.0.0:8000"]
```

## Create a docker ignore file

This is file ignores all file you don't want in your docker container

.dockerignore

```
<!-- All files you want to ignore goes here -->
*/venv
```

## Run the docker container

```
docker run --publish 8000:8000 python-django
```
