FROM golang:1.22

WORKDIR /app
COPY . .

RUN apt-get update && apt-get install -y curl

EXPOSE 8001

CMD ["go", "run", "main.go"]
