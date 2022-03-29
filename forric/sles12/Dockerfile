FROM darksheer/sles12:latest
RUN zypper -n in which \
                 curl \
                 net-tools \
                 procps \
                 perl
RUN zypper -n up
RUN pip3 install distro
