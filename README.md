# packer-qemu
Docker image for building qemu images with packer

## Build qemu based image

    docker run --rm -e PACKER_LOG=1 -e PACKER_LOG_PATH="packer-docker.log" \
      -it \
      --privileged \
      --cap-add=ALL -v /lib/modules:/lib/modules \
      -v `pwd`:/opt/ \
      -w /opt/ leonkyneur/packer-qemu build -var-file=hardened.json CentOS-6-qemu.json
