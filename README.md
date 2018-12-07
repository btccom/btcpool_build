BTCPool Build Environment
=========================

This repository manages the build environments for [BTCPool](https://github.com/btccom/btcpool).

BTCPool is now using [CircleCI](https://circleci.com/gh/btccom/btcpool) as the CI/CD system. Building in docker images with prebuilt dependencies including blockchain sources reduces the build time significantly. This is achieved by utilizing Docker Hub automatic builds.

* The `master` branch is the base of all other branches. Dependencies other than blockchain sources are supposed to be managed there.
* Other branches in this repository ressembles different blockchain supports. They are rebased on the `master` branch.
* Other branches add blockchain building and put the sources and libraries under `/work/bitcoin` of docker images. It is then be used by BTCPool CMake process as `CHAIN_SRC_ROOT` variable.
* Other branches sets the environment variable `CHAIN_TYPE` in the docker images, which will be used by BTCPool CMake process as `CHAIN_TYPE` variable.
