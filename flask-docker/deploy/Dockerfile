FROM ubuntu:18.04

RUN apt-get update -y

RUN apt-get install python3-pip -y


COPY ./requirements.txt requirements.txt
COPY ./application.py /opt/
COPY ./s3_store.py /opt/
COPY ./templates /opt/templates
COPY ./.ebextensions /opt/.ebextensions
COPY ./uploads /opt/uploads

RUN pip3 install -r requirements.txt
WORKDIR /opt/

EXPOSE 8000

CMD ["python3", "-m", "application"]


