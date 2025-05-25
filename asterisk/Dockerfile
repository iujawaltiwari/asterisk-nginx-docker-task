FROM debian:bullseye

RUN apt-get update && apt-get install -y \
    build-essential git wget subversion \
    libjansson-dev libxml2-dev libncurses5-dev uuid-dev libsqlite3-dev \
    curl net-tools iputils-ping && \
    cd /usr/src && \
    git clone -b 18 https://github.com/asterisk/asterisk.git && \
    cd asterisk && \
    contrib/scripts/install_prereq install -y && \
    ./configure && \
    make -j$(nproc) && \
    make install && \
    make samples && \
    make config && \
    ldconfig

EXPOSE 5060/udp 5061/tcp 8000 8088

CMD ["/usr/sbin/asterisk", "-f"]

