# Stage 1 - Build
FROM python:3.11-slim as builder
WORKDIR /app
COPY app/ .
RUN pip install --no-cache-dir -r requirements.txt

# Stage 2 - Distroless (lightweight)
FROM gcr.io/distroless/python3
WORKDIR /app
COPY --from=builder /app /app

CMD ["app.py"]
