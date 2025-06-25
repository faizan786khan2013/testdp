FROM python:3.9

WORKDIR /app
COPY . .

RUN pip install flask gunicorn

EXPOSE 8002

CMD ["gunicorn", "--bind", "0.0.0.0:8002", "app:app"]
