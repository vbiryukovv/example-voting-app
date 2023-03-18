#Download base image ubuntu 20.04
FROM ubuntu:20.04

#Configure tz-data
ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Update Ubuntu Software repository
RUN apt-get -qy update
RUN apt install -qy python3 python3-pip software-properties-common git ansible
RUN pip install ansible-lint==4.0.0

CMD ["/bin/bash"]

