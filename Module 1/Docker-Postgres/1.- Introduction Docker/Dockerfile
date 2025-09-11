FROM python:3.9.1
RUN apt-get install wget
RUN pip install pandas
WORKDIR /app

COPY pipeline.py pipeline.py

ENTRYPOINT ["python", "pipeline.py"]