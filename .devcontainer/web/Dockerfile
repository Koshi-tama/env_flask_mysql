FROM python:3.9-slim

RUN apt-get update && apt-get install -y tzdata \
  && rm -rf /var/lib/apt/lists/*

WORKDIR /tmp/work
COPY requirements.txt .
RUN pip install -r requirements.txt
EXPOSE 5000

ENV TZ=Asia/Tokyo
ENV USER=user1

RUN useradd -m ${USER} --uid 1000
RUN gpasswd -a ${USER} sudo
RUN echo "${USER}:password" | chpasswd

USER ${USER}


