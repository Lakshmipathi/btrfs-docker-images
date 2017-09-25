# btrfs-docker-images


### Building Images

  Pull the repo contents:

	  cd btrfs-docker-images/

  Build the specific container image:

          docker build -t opensuse `pwd`/openSUSE

### Launch the container

	  docker run -it opensuse

  or

	 docker run -it --privileged=true --device=/dev/loop0:/dev/loop0 --device=/dev/loop1:/dev/loop1  --device=/dev/loop2:/dev/loop2  --device=/dev/loop3:/dev/loop3 --device=/dev/loop4:/dev/loop4   opensuse


### Todo

- Add other distros.

- loop-back device setup. (using either -v /dev:/dev --privileged or create via mknod)

- Invoke 'make test' && save logs.

- Push pre-built images to Docker hub. 

