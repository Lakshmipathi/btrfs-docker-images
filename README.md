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


### Launch armv8 container

	docker run -it --privileged=true --device=/dev/loop0:/dev/loop0 --device=/dev/loop1:/dev/loop1  --device=/dev/loop2:/dev/loop2  --device=/dev/loop3:/dev/loop3 --device=/dev/loop4:/dev/loop4  laks/btrfs_armv8

### Todo

- Add arm32,mips,ppc64.

- Integrate with travis

- Run all tests (make test) and ensure they work.

