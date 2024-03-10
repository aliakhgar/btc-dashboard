### Setup of https://bitcoinexplorer.org on Ubuntu 20.04

    # update and install packages
    apt update
    apt upgrade
    apt install docker.io

    # get source, npm install
    git clone https://github.com/aliakhgar/btc-dashboard.git
    cd btc-dashboard

    # build docker image
    docker build -t btc-dashboard .

    # run docker image: detached mode, share port 3002, sharing config dir, from the "btc-dashboard" image made above
    docker run --name=btc-dashboard -d -v /host-os/env-dir:/container/env-dir --network="host" btc-dashboard
