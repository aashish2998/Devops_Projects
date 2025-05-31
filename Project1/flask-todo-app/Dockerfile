# First Stage: Builder
FROM python:3.9 AS builder
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .

# Second Stage: Slim Final Image
FROM python:3.9-slim
WORKDIR /app
RUN apt-get update && apt-get install -y curl && rm -rf /var/lib/apt/lists/*
# Create a non-root user
RUN useradd -m appuser
COPY --from=builder /app /app
COPY --from=builder /usr/local/lib/python3.9/site-packages /usr/local/lib/python3.9/site-packages
USER appuser
EXPOSE 5000
HEALTHCHECK --interval=10s --timeout=3s --retries=3 CMD curl -f http://localhost:5000/health || exit 1
CMD ["python", "app.py"]
