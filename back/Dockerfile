FROM golang:1.23.3

ENV ROOT=/go/src
WORKDIR ${ROOT}

ENV GO111MODULE=on

RUN go install github.com/air-verse/air@latest
RUN apt-get update && apt-get install -y postgresql-client
# RUN go get github.com/lib/pq
#ホットリロードはair-verseの方推薦しているため
# RUN go install github.com/cosmtrek/air@latest

# RUN go get -u github.com/labstack/echo/v4
# RUN go get -u github.com/labstack/echo/v4/middleware