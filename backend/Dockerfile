# ---------- Build stage ----------
FROM golang:1.25.1-alpine AS builder

WORKDIR /app

COPY go.mod go.sum ./
RUN go mod download

COPY . .

RUN CGO_ENABLED=0 GOOS=linux GOFLAGS="-p=1" go build -o /app/bin/api ./cmd/api

# ---------- Runtime stage ----------
FROM alpine:3.20

RUN apk add --no-cache ca-certificates

WORKDIR /app

COPY --from=builder /app/bin/api .

EXPOSE 8080

ENTRYPOINT ["./api"]
