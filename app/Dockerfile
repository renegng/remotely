# Official Python 3.8 image
FROM ubuntu:20.04

# Create the app folder
RUN mkdir -p /var/www/remotely

# Copy all contents of app into the new directory
COPY . /var/www/remotely

# Set work directory
WORKDIR /var/www/remotely

# Install system dependencies
RUN apt-get update
RUN apt-get install -y software-properties-common
RUN add-apt-repository ppa:deadsnakes/ppa
RUN apt-get install -y python3.8 python3-pip
RUN apt-get install -y build-essential python3-dev libmysqlclient-dev

# Install NodeJS v14
RUN apt-get install -y curl
RUN curl -fsSL https://deb.nodesource.com/setup_14.x | bash -
RUN apt-get install -y nodejs

# Install python dependencies
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# Install node dependencies
RUN npm install
RUN npm install -g npm

# UnZip credentials
RUN apt-get install -y p7zip-full
RUN 7z x instance.zip -pRemote2021

# Compile all npm libraries
RUN npm run build-prd-wp

# Expose port
EXPOSE 8000

# Entrypoint
ENTRYPOINT ["gunicorn", "-k", "eventlet", "-w", "1", "-b", "0.0.0.0:8000", "-m", "007", "swing_main-socketio:app"]
