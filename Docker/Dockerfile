FROM golang:alpine3.16 AS builder

WORKDIR /usr/src/app

COPY mensagem.go .

RUN CGO_ENABLED=0 go build -o /app mensagem.go

FROM scratch

COPY --from=builder /app /app

ENTRYPOINT ["/app"]