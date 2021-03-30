FROM phpdockerio/php74-fpm:latest
WORKDIR "/application"

# Fix debconf warnings upon build
ARG DEBIAN_FRONTEND=noninteractive

# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get -y --no-install-recommends install  php7.4-mysql php7.4-bcmath

RUN chown -R 33:33 /application

# Prepare python environment
RUN apt-get -y install software-properties-common
RUN add-apt-repository ppa:deadsnakes/ppa
RUN apt-get update
RUN apt -y install python3.8
RUN apt -y install python3-pip

RUN pip3 install youtube-dl
RUN pip3 install pafy
RUN pip3 install matplotlib
RUN pip3 install opencv-python-headless
RUN pip3 install imutils
RUN pip3 install scikit-image
RUN pip3 install python-dotenv
RUN pip3 install pymysql

# clean apt install
RUN apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*