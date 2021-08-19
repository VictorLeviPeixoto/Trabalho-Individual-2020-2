FROM python:3.7-alpine

WORKDIR /app/api

ENV PYTHONUNBUFFERED=1

COPY . .

RUN apk update && apk add postgresql-dev gcc python3-dev musl-dev

RUN pip install --no-cache-dir django psycopg2 djangorestframework django-cors-headers

EXPOSE 8000

CMD ["python3", "manage.py", "migrate"]

CMD ["python3", "manage.py", "runserver", "0.0.0.0:8000"]

