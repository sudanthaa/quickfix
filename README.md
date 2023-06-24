# Quickfix

[![Build Status](https://travis-ci.org/quickfix/quickfix.svg?branch=master)](https://travis-ci.org/quickfix/quickfix)

## BUILDING AND INSTALLING

    Full instructions:
        See doc/html/building.html

    Quick instructions:
        ./bootstrap
        ./configure
        make
        make check
        sudo make install

For SunOS and AIX have a look at README.SunOS and README.AIX.

--------------------------------------------------------------------

It is possible to build many components with a relatively newer version of cmake.


For example on Windows,

mkdir build
cd build
cmake  -DHAVE_SSL=ON -G "Visual Studio 15 2017 Win64" -DCMAKE_INSTALL_PREFIX:PATH="install-path" -DOPENSSL_ROOT_DIR="path to openssl" ..
Then build in Visual Studio or on command prompt.

On Linux (with system openssl),

cmake -DCMAKE_BUILD_TYPE=RelWithDebInfo -DHAVE_SSL=ON -DCMAKE_INSTALL_PREFIX:PATH="install-path" ..
make -j 4 install

If one has Ninja then (with system openssl),

cmake -G Ninja -DCMAKE_BUILD_TYPE=RelWithDebInfo -DHAVE_SSL=ON -DCMAKE_INSTALL_PREFIX:PATH="install-path" ..
ninja install

Alternatively, you can build and install quickfix using [vcpkg](https://github.com/Microsoft/vcpkg/) dependency manager:

    git clone https://github.com/Microsoft/vcpkg.git
    cd vcpkg
    ./bootstrap-vcpkg.sh
    ./vcpkg integrate install
    ./vcpkg install quickfix

The quickfix port in vcpkg is kept up to date by Microsoft team members and community contributors. If the version is out of date, please [create an issue or pull request](https://github.com/Microsoft/vcpkg) on the vcpkg repository.

