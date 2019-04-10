FROM python:3.7.0

RUN mkdir /mlflow/
RUN pip install mlflow==0.8.2

EXPOSE 5000

CMD    mlflow server \
       --file-store /mlflow \
       --default-artifact-root s3://sample-bucket \
       --static-prefix /mlflow \
       --host 0.0.0.0
