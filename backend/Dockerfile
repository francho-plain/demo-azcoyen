# Use Python 3.12 slim image as base
FROM python:3.12-slim

# Set working directory
WORKDIR /app

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1

# Install system dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    gcc \
    postgresql-client \
    && rm -rf /var/lib/apt/lists/*

# Copy requirements file
COPY requirements.txt .

# Install Python dependencies
# Note: --trusted-host flags are used as a workaround for SSL certificate issues in CI environments
# For production, ensure proper SSL certificates are configured
RUN pip install --no-cache-dir --trusted-host pypi.org --trusted-host files.pythonhosted.org -r requirements.txt

# Copy project files
COPY . .

# Expose port 8000 for Django development server
EXPOSE 8000

# Run Django development server
# Note: This is for development only. For production, use a WSGI server like gunicorn
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
