FROM python:3.7-buster

RUN apt update

RUN apt install -y python3-opencv

RUN mkdir /app

WORKDIR /app

ADD requirements.txt /app

RUN pip install --upgrade pip

RUN pip install -r requirements.txt

ADD . /app

ENTRYPOINT ["gunicorn", "main:app", "--bind", ":8080", "--worker-class", "aiohttp.GunicornWebWorker"]
