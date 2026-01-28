FROM golang:1.25 AS build
RUN mkdir /app
WORKDIR /app
COPY main.go /app/

RUN go build -o hello main.go


FROM alpine:latest
COPY --from=build /app/hello /app/hello
CMD ["/app/hello"]
