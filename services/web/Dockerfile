# official base image
FROM python:3.10.6-slim-buster

# set working dir
WORKDIR /usr/src/app

# don't generate __pycache__
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# system depencencies
RUN apt-get update && apt-get install -y netcat

# update pip, so no warning
RUN pip install --upgrade pip
# put pip requirements
COPY ./requirements.txt /usr/src/app/requirements.txt
# install them
RUN pip install -r requirements.txt

# copy project
COPY . /usr/src/app/

# run entrypoint
ENTRYPOINT [ "/usr/src/app/entrypoint.sh" ]