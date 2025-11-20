FROM python:latest
WORKDIR /app
COPY src /app/
RUN apt-get update && apt-get install -y python3 python3-pip
RUN pip install --no-cache-dir -r requirements.txt
EXPOSE 6100
CMD ["python3", "server.py"]