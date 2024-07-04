This page describes primary configuration of the proxy.

The default configuration can be overriden with `.env` file or environment variables.

## Ethereum nodes

The list of connected Ethereum nodes are to be passed in the `.env`, an example
```
ETH_ENDPOINTS='[{"name": "rpi5", "url": "http://192.168.1.90:8545/"}, {"name": "rpi4", "url": "http://192.168.1.224:8545/"} ]'
```
or via the environment variable, an example
```
ETH_ENDPOINTS='[{"name": "rpi5", "url": "http://192.168.1.90:8545/"}, {"name": "rpi4", "url": "http://192.168.1.224:8545/"} ]' web3pi-proxy
```

Note that the value of `ETH_ENDPOINTS` is a valid json. Names of endpoints are arbitrary.
Endpoints are to be any valid Ethereum RPC services, not necessary Web3-Pi installation.

## Ports and Addresses

Modify the proxy addresses with the following records
```
PROXY_LISTEN_ADDRESS='0.0.0.0'
PROXY_LISTEN_PORT=6512
ADMIN_LISTEN_PORT=6561
```

To initialize UPnP set
```
USE_UPNP='True'
```

To use SSL set
```
SSL_ENABLED=True
SSL_CERT_FILE='cert.pem'
SSL_KEY_FILE='key.pem'
```

## Other

You can find other configurtion records in the source file [conf.py](https://github.com/Web3-Pi/web3-reverse-proxy/blob/main/web3pi_proxy/config/conf.py)
