FROM opensuse
MAINTAINER Lakshmipathi.G

# Install build tools
RUN zypper -n install git autoconf automake gcc make

# Install needed dependencies.
RUN zypper -n install e2fsprogs-devel libblkid-devel zlib-devel  lzo-devel asciidoc xmlto

# Clone the repo
RUN git clone https://github.com/kdave/btrfs-progs.git

# Start the build
WORKDIR /btrfs-progs
RUN ./autogen.sh
RUN ./configure
RUN make
RUN make install
RUN btrfs --version

# Setup greetings 
RUN zypper -n install cowsay
RUN echo "#!/bin/bash" > /run.sh
RUN echo "cowsay 'Welcome to BTRFS Docker image for `grep PRETTY_NAME /etc/os-release | cut -f2 -d'='`'" >> /run.sh
RUN echo "btrfs --version; /bin/bash" >> /run.sh
RUN chmod +x /run.sh
ENTRYPOINT ["/run.sh"]
