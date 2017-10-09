FROM  osrf/ubuntu_arm64:yakkety 
MAINTAINER Lakshmipathi.G

# Install build tools
RUN apt-get update
RUN apt-get install -y git autoconf automake gcc make pkg-config

# Install needed dependencies.
RUN apt-get install -y e2fslibs-dev libblkid-dev zlib1g-dev liblzo2-dev asciidoc xmlto

# reduce image size
RUN sudo apt-get -y remove --auto-remove texlive

# Clone the repo and build  (uncomment if needed)
#RUN git clone https://github.com/kdave/btrfs-progs.git

#WORKDIR /btrfs-progs
#RUN ./autogen.sh
#RUN ./configure
#RUN make
#RUN make install
#RUN make tests
#RUN btrfs --version

# Setup greetings  - uncomment below lines to enable entry point and greetings
#RUN apt-get install -y cowsay
#RUN ln -s /usr/games/cowsay /usr/bin/cowsay
#RUN echo "#!/bin/bash" > /run.sh
#RUN echo "cowsay 'Welcome to BTRFS Docker image for `grep PRETTY_NAME /etc/os-release | cut -f2 -d'='`'" >> /run.sh
#RUN echo "btrfs --version; /bin/bash" >> /run.sh
#RUN chmod +x /run.sh
#ENTRYPOINT ["/run.sh"]
