The Web3Pi Proxy is independent sofware to Web3Pi nodes and othere Ethereum nodes.
It can be installed on any machine that can directly or via tunnels 
connect to your Ethereum nodes. 
There is no restriction if hardware parameters are sufficent - 
and this is satisfied in most cases since the proxy is lightweight.
For instance it can be installed on PC, a dedicated 
RaspberryPi, or collocated with one of Ethereum nodes.

The instruction is provided for Linux. 
Windows instalation needs further examination.

## Requirements

To run the proxy, `python` is required

```
python >= 3.10
```

## Installation

Before proceeding further, verify the python's version. Should be at least `3.10`.

```bash
user@host:~$ python3 --version
```

At first create a data directory for Web3 Pi proxy instance and change the working directory to it.
For the purposes of demonstration assume that the data directory is `web3pi` in the user's home folder.
Then the example commands are

```bash
user@host:~$ mkdir web3pi
user@host:~$ cd web3pi
user@host:~/web3pi$
```

You may wish preferably to use a python's virtual environment `venv`. 
Note that this is optional.
For example, create a virtual environment `venv`.
```bash
user@host:~/web3pi$ python3 -m venv venv
```

The folder `venv` is created in the place. Now activate the virtual environment.

```bash
user@host:~/web3pi$ source venv/bin/activate
(venv) user@host:~/web3pi$
```

Get latest version from pypi

```bash
(venv) user@host:~/web3pi$ pip install web3pi-proxy
```

## Configuration

Before running for the first time, a basic configuration with Ethereum nodes addresses needs to be provided.
For more options and further details see [Configuration and Monitoring](configuration.md#ethereum-nodes).
Here is simple configuration that allows the proxy to run.

Create the file `.env`. Note the the file name must be exactly `.env`.

```bash
(venv) user@host:~/web3pi$ touch .env
```

Edit the file with an editor of your preference, and provide variable/value records.
In simple configuration only the variable `ETH_ENDPOINTS` needs to be set.
It lists Ethereum nodes to be connected.
A basic example of `.env` file content is as follows.

```bash
(venv) user@host:~/web3pi$ cat .env
ETH_ENDPOINTS='[{"name": "my_node", "url": "http://192.168.1.90:8545/"}]'
```

Remember that the value of `ETH_ENDPOINTS` must be a valid json. 
Furthermore, this is an array of objects, each describing one Ethereum node with 
arbitrary but distinct `name` (pick one you like) and `url` which is an RPC endpoint of Ethereum node.

## Run

Simply execute

```bash
(venv) user@host:~/web3pi$ web3pi-proxy
```

Ctrl+C (`SIGTERM`) shuts down the proxy.

## Admin panel

When the proxy is up, the access url to the admin panel is generated.
Check logs and grep the line that looks like this
```
Access admin portal with:
http://0.0.0.0:6561/?token=DJQPiFYBAks9n2vedLIXLtvUu3kuTe60
```
Update the address part `0.0.0.0` in the url according to your network configuration.
The excerpt above is an example, use a token that is actually included in your logs.
Note that the access token may change in the next run of the proxy.

See [Admin Panel](admin.md) for further details.