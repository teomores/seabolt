# Seabolt for M1
Seabolt is the C Connector Library for Neo4j.
The library supports multiple versions of the Bolt protocol through the new _Connector API_ and will provide a base layer for a number of language drivers.

This repo is forked from the original one, that you can find [here](https://github.com/neo4j-drivers/seabolt).
The reason behind this is adding support for the **M1 chip MacBooks with Big Sur**.

## Prerequisites

1. Install XCode,
2. Install XCode Command Line Tools via `xcode-select --install`
3. Install CMake `brew install cmake`
4. Install OpenSSL `brew install openssl`
5. Create an environment variable named `OPENSSL_ROOT_DIR` that points to the openssl library installation path (default is `/usr/local/opt/openssl`)

## Building

To build the project, first of all download the source code. Then from the root directory run the make script: 
```console
./make_debug.sh
```
or
```console
./make_release.sh
```
This will compile and deposit project artifacts in the `build/dist` directory.

To create distributable packages, invoke `cpack` in `build` directory (after `make_debug.sh` or `make_release.sh` is completed) and all binary package artifacts will be placed in `build/dist-package` directory.


## Move to the right dir
Finally move the libseabolt to the standard directory where other tools will search for it:
```console
cd build/dist
cp libseabolt17.1.dylib /usr/local/lib/libseabolt17.dylib
```
