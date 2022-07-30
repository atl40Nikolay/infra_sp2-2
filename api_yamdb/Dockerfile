FROM python:3.7-slim

RUN mkdir /app

COPY requirements.txt /app

RUN pip3 install -r /app/requirements.txt --no-cache-dir

COPY . /app

WORKDIR /app

CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000"]
#CMD /app/run.sh # Не получилось реализовать, докер web падает-стартует по настройкам - снова падает

LABEL author='d4mir.sh.d@yandex.ru' version=1 
