FROM golang:1.16-alpine AS base

WORKDIR /usr/src/app
COPY . .

FROM base as build

WORKDIR /usr/src/app
RUN go build

FROM golang:1.16-alpine

WORKDIR /usr/src/app
EXPOSE 8080
ENV REQUEST_ORIGIN="http://localhost"
COPY --from=build /usr/src/app/server ./server
ENTRYPOINT ["./server"]
