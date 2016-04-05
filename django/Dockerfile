FROM python:2.7
ENV PYTHONUNBUFFERED 1
RUN apt-get update && apt-get install -y \
supervisor
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
RUN mkdir /code
WORKDIR /code
ADD requirements.txt /code/
RUN pip install -r requirements.txt
ADD . /code/
CMD ["/usr/bin/supervisord"]
