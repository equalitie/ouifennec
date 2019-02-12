# OuiFennec

A clone of Firefox For Android (Fennec) with Ouinet/Client in it.

# Set up injector's parameters

These are currently hardcoded in [ouinet.xml](https://github.com/equalitie/gecko-dev/blob/ouinet/mobile/android/app/src/main/res/values/ouinet.xml)
and can't be changed during the runtime (See TODO).

To change the icon name, change the `MOZ_APP_DISPLAYNAME` variable in
`gecko-dev/mobile/android/branding/unofficial/configure.sh`

# Build

```sh
sudo docker build - < Dockerfile
mkdir -p root.build/.mozbuild # build cache will be stored in $PWD/ouinet.build, $PWD/ouifennec.build, and $PWD/root.build
sudo docker run --rm -it --mount type=bind,source="$(pwd)",target=/usr/local/src/ouifennec --mount type=bind,source="$(pwd)/root.build",target=/root $CONTAINER_ID_FROM_↑_BUILD
cd ouifennec
bash build.sh
```

# TODO

## Technical

* Set up ouinet with injector's IPFS ID, IP and I2P addresses and
  injector's creadentials.
* Allow setting up Injector's values using QR codes
* Get rid of our [`OUINET_QUICK_HACK`](https://github.com/equalitie/gecko-dev/commit/2de7aad32981201d5a75cfbc9c49acf38f21dc0c)
