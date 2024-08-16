FROM ubuntu:latest

RUN apt-get update && apt-get install -y \
	wget \
	build-essential

RUN wget https://ftp.gnu.org/gnu/bash/bash-3.0.16.tar.gz

RUN tar -xzvf bash-3.0.16.tar.gz

WORKDIR bash-3.0.16

RUN ./configure --build=x86_64-linux-gnu && make && make install

RUN echo "/usr/local/bin/bash" >> /etc/shells && \
	chsh -s /usr/local/bin/bash

WORKDIR /usr/src/app

COPY . .

CMD ["bash"]
