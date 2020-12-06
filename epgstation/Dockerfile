FROM l3tnun/epgstation:master-debian
EXPOSE 8888

ENV DEV="software-properties-common wget gnupg"
RUN apt-get update && apt-get -y install $DEV
RUN wget http://archive.raspberrypi.org/debian/raspberrypi.gpg.key -O - | apt-key add -
RUN apt-add-repository 'deb http://archive.raspberrypi.org/debian buster main'
RUN apt-get update
RUN apt-get -y install -t buster ffmpeg

# 不要なパッケージを削除
RUN apt-get remove -y $DEV
RUN apt-get autoremove -y
RUN apt-get clean
