# btrfs-docker-images


### Building Images

  Pull the repo contents:

	  cd btrfs-docker-images/

  Build the specific container image:

          docker build -t opensuse `pwd`/openSUSE

### Launch the container

	  docker run opensuse

### Todo

- Add other distros.

- loop-back device setup. (using either -v /dev:/dev --privileged or create via mknod)

- Invoke 'make test' && save logs.

- Push pre-built images to Docker hub. 

