
FROM python:3.11-slim

WORKDIR /app

# Install deps first (better layer caching)
COPY requirements.txt /app/requirements.txt
RUN python -m pip install --upgrade pip && pip install -r requirements.txt

# Copy the rest of your application
COPY . /app

EXPOSE 5000

