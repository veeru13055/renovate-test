# Build stage
FROM golang:1.25 AS builder
WORKDIR /app
COPY . .
RUN go build -o main .

# Runtime stage
FROM alpine:latest
WORKDIR /root/
COPY --from=builder /app/main .
CMD ["./main"]
