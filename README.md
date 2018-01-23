# bgpcoin
BGPCoin is a proof-of-work/proof-of-stake currency that can be used by Internet Service Providers for real-time settlement of peering expenses such as crossconnects, dark fiber, route advertisement, and bandwidth costs.

BGPCoin can be mined using a CPU miner.  It's recommended to run a BGPCoin node on Ubuntu 17.10, and then use the getwork method of mining and collecting block
miner rewards.

The rewards are 256 BGPCoins per block.

The premined coins in the genesis block will be used to fund development in the
form of code bounties.

# Build Instructions

1. Install the pre-requisites

```
sudo apt-get install build-essential libssl-dev libdb-dev libdb++-dev libboost-all-dev git libssl1.0.0-dbg libdb-dev libdb++-dev libboost-all-dev libminiupnpc-dev libminiupnpc-dev libevent-dev libcrypto++-dev libgmp3-dev
```

2. Build the daemon

```
cd src
make RELEASE=1
```

3. Install it

```
sudo make install
``` 

4.  create a ~/.bgpcoin/bgpcoin.conf file with the following: 
```
rpcuser=user
rpcpassword=x
rpcallowip=*
daemon=1
server=1
txindex=1
gen=0
```

5. Run it
```
nohup /usr/sbin/bgpcoind &
```

Save the ```~/.bgpcoin/wallet.dat``` file and you can load it with your QT wallet

6. Mine your coins (On localhost using all threads)

```
minerd -o http://127.0.0.1:32076 -u user -p x
```

7. Mine your coins (On localhost using one thread)
```
minerd -t 1 -o http://127.0.0.1:32076 -u user -p x
```

Enjoy!

# Current Bounties

1. 8 BGP per blog post evangelizing BGPCoin
2. 1024 BGP (4 block rewards) for a cleaner Makefile that integrates with systemd
3. 10240 BGP (40 block rewards) for a nicely designed site
4. 10240 BGP (40 block rewards) for command line scripts that allow ISPs to pay each other using the API
5. 20480 BGP (80 block rewards) for an ISP who agrees to take BGPCoin
6. 20480 BGP (80 block rewards) for a Mac OS X wallet
7. 20480 BGP (80 block rewards) for an Android wallet
8. 102400 BGP (400 block rewards) for listing on an exchange, per exchange
