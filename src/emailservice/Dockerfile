# First stage: build environment
FROM python:3.9-slim-buster AS build-env

WORKDIR /app

COPY requirements.txt .

RUN pip install -r requirements.txt

COPY . .

RUN python setup.py install

# Second stage: production environment
FROM python:3.9-slim-buster AS prod-env

WORKDIR /app

COPY --from=build-env /usr/local/lib/python3.9/site-packages /usr/local/lib/python3.9/site-packages
COPY --from=build-env /app /app

CMD ["python", "app.py"]
