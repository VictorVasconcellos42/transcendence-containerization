FROM python:3.11-alpine

WORKDIR /app

COPY requirements.txt .

COPY .env .

RUN pip install --no-cache-dir --upgrade pip

RUN apk add --no-cache python3-dev build-base linux-headers pcre-dev libpq-dev

RUN pip install --no-cache-dir -r requirements.txt

COPY /core/ /app/

EXPOSE 8000

ENV DJANGO_SETTINGS_MODULE=core.settings

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]

