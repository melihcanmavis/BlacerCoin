BlacerCoin Core (fork of PIVX) integration/staging repository
======================================


It is recommended [use the shell script](https://github.com/blcrproject/lgs-install) to install a BlacerCoin Masternode on a Linux server running Ubuntu 14.04, 16.04, 18.04

***

Quick installation of the BlacerCoin daemon under linux. See detailed instructions there [build-unix.md](build-unix.md)

Installation of libraries (using root user):
    

    sudo apt-get update -y && sudo apt-get upgrade -y && sudo apt-get install vim -y && sudo apt-get install python-dev -y &&                     sudo apt-get install libevent-dev -y &&  sudo apt-get install python-virtualenv -y && apt-get install git -y
    sudo apt update
    sudo apt-get install libgmp3-dev
    sudo apt install python rename git software-properties-common libzmq3-dev libqrencode-dev libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils python3 libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-test-dev libboost-thread-dev libminiupnpc-dev -y
    sudo add-apt-repository ppa:bitcoin/bitcoin
    sudo apt update
    sudo apt install libdb4.8-dev libdb4.8++-dev -y
    sudo apt-get install libdb4.8-dev libdb4.8++-dev
    apt-get install libzmq3-dev -y
    apt-get install libssl1.0-dev -y
    sudo apt-get install libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev
    sudo apt-get install libdb++-dev
    add-apt-repository ppa:bitcoin/bitcoin -y
    apt-get update
    apt-get install -y build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils
    apt-get install -y libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev
    apt-get install -y libdb4.8-dev libdb4.8++-dev



2a. OpenSLL- Install OpenSSL dependencies on Windows.
Download the latest version of OpenSSL https://www.openssl.org/source/openssl-1.0.1j.tar.gz to your deps folder.

    cd /c/deps/
    tar xvfz openssl-1.0.1j.tar.gz
    cd openssl-1.0.1j
    ./Configure no-zlib no-shared no-dso no-krb5 no-camellia no-capieng no-cast no-cms no-dtls1 no-gost no-gmp no-heartbeats no-idea no-jpake no-md2 no-mdc2 no-rc5 no-rdrand no-rfc3779 no-rsax no-sctp no-seed no-sha0 no-static_engine no-whirlpool no-rc2 no-rc4 no-ssl2 no-ssl3 mingw
    make

2b. Berkeley DB
Download http://download.oracle.com/berkeley-db/db-4.8.30.NC.tar.gz and place in your deps folder.
In the MinGW shell use the following code.

    cd /c/deps/
    tar xvfz db-4.8.30.NC.tar.gz
    cd db-4.8.30.NC/build_unix
    ../dist/configure --enable-mingw --enable-cxx --disable-shared --disable-replication
    make
    

Cloning the repository and compiling (use any user with the sudo group):

    cd
    git clone https://github.com/blcrproject/BlacerCoin.git
    cd BlacerCoin
    ./autogen.sh
    ./configure
    sudo make install
    cd src
    sudo strip blacercoind
    sudo strip blacercoin-cli
    sudo strip blacercoin-tx
    cd ..

Running the daemon:

    blacercoind

Stopping the daemon:

    blacercoin-cli stop

Demon status:

    blacercoin-cli getinfo
    blacercoin-cli mnsync status

All binaries for different operating systems, you can download in the releases repository:

https://github.com/blcrproject/BlacerCoin/releases

P2P port: 24433, RPC port: 24432
-
Distributed under the MIT software license, see the accompanying file COPYING or http://www.opensource.org/licenses/mit-license.php.
