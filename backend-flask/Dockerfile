FROM python:3.10-slim-buster

WORKDIR /backend-flask

COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

COPY . .

# Set environment variables
ENV FLASK_ENV=development

# Expose the desired port
EXPOSE 5000


# Spin up our flask server.
ENTRYPOINT ["python3"]
CMD ["main.py"]