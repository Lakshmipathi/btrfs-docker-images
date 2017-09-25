FROM centos:centos7
MAINTAINER Lakshmipathi.G

# Install build tools
RUN yum -y install git autoconf automake gcc make

# Install needed dependencies
RUN yum -y install e2fsprogs-devel libblkid-devel zlib-devel  lzo-devel asciidoc xmlto which

# Clone the repo
RUN git clone https://github.com/kdave/btrfs-progs.git

# Start the build
WORKDIR /btrfs-progs
RUN ./autogen.sh
RUN ./configure
RUN make
RUN make install
RUN make tests
RUN btrfs --version

# Setup greetings 
RUN yum -y install epel-release
RUN yum -y install cowsay
RUN echo "#!/bin/bash" > /run.sh
RUN echo "cowsay 'Welcome to BTRFS Docker image for `grep PRETTY_NAME /etc/os-release | cut -f2 -d'='`'" >> /run.sh
RUN echo "btrfs --version; /bin/bash" >> /run.sh
RUN chmod +x /run.sh
ENTRYPOINT ["/run.sh"]
