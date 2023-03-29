FROM python:3.7-slim as base
COPY requirements.txt .
RUN pip install -r requirements.txt
WORKDIR /email_server
COPY . .

EXPOSE 8080
ENTRYPOINT [ "python", "email_server.py" ]