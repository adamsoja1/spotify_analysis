FROM ubuntu:20.04

RUN apt-get update && \
    apt-get install -y unzip python3 python3-pip htop

ADD requirements.txt .
RUN pip install -r requirements.txt
RUN chmod -R a+rwx /home

ADD . /home/
WORKDIR /home

EXPOSE 8888

ENTRYPOINT [ "jupyter", "lab", "--ip", "0.0.0.0", "--allow-root" ]
