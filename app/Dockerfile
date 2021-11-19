# Official Python 3.8 image
FROM python:3.8-alpine

# Create the app folder
RUN mkdir -p /var/www/remotely

# Copy all contents of app into the new directory
COPY . /var/www/remotely

# Set work directory
WORKDIR /var/www/remotely

# Install system dependencies
RUN apk --no-cache add curl
RUN apt-get update && apt-get install build-essential python3-dev

# Install python dependencies
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# Install NodeJS v14
RUN curl -fsSL https://deb.nodesource.com/setup_14.x | sudo -E bash -
RUN sudo apt-get install -y nodejs

# Install node dependencies
RUN npm install
RUN npm install -g npm
RUN npm run build-prd-wp

# UnZip credentials
RUN unzip -P Remote2021 instance.zip

# Expose port
EXPOSE 8000

# Entrypoint
ENTRYPOINT ["gunicorn", "-k", "eventlet", "-w", "1", "-b", "0.0.0.0:8000", "-m", "007", "swing_main-socketio:app"]
