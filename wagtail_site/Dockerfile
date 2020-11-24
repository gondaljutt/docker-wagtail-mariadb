FROM python:3.7
LABEL maintainer="GondalJutt"
ENV PYTHONUNBUFFERED 1
COPY docker_assignment/requirements.txt /code/requirements.txt
RUN pip install --upgrade pip
RUN pip install -r /code/requirements.txt
RUN pip install gunicorn
COPY docker_assignment /code/
WORKDIR /code/
RUN python manage.py migrate
RUN useradd wagtail
RUN chown -R wagtail /code
USER wagtail
