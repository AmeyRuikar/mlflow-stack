FROM python:3.7.0

RUN mkdir /mlflow/
RUN pip install mlflow==0.8.2

# set env variables to access the object store
ENV MLFLOW_S3_ENDPOINT_URL=http://minio:9000/
ENV AWS_ACCESS_KEY_ID=minioKey
ENV AWS_SECRET_ACCESS_KEY=minioSecret

# static prefix for html content
ENV MLFLOW_STATIC_PREFIX=/mlflow

EXPOSE 5000

CMD    mlflow server \
       --file-store /mlflow \
       --default-artifact-root s3://sample-bucket \
       --static-prefix /mlflow \
       --host 0.0.0.0
