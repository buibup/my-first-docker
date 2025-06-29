# 1. Choose base image
FROM python:3.9-slim

# 2. Set working directory in image
WORKDIR /app

# 3. Copy requirements file into image
COPY requirements.txt .

# 4. Run pip to install dependencies
RUN pip install -r requirements.txt

# 5. Copy application code into image
COPY . .

# 6. Run the application
CMD ["python", "app.py"]
