FROM golang:1.16-alpine as build
WORKDIR usr/src/app
COPY .  .
RUN go mod download
COPY *.go ./
RUN go build -o /go-docker-demo

FROM golang:1.21-rc-bullseye
COPY --from=build . .
EXPOSE 8080

CMD [ "/go-docker-demo" ]
