FROM alpine:latest AS build
RUN mkdir /app
WORKDIR /app
RUN apk add --no-cache go
ENV PATH=$PATH:/app/go/bin

COPY main.go /app/

RUN go build -o hello main.go

FROM alpine:latest
COPY --from=build /app/hello /app/hello
CMD ["/app/hello"]
