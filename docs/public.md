This section describes how to bring your Ethereum nodes to the public with Web3 Reverse Proxy.
There are multiple configurations to achieve this.
Here are a few.

## Own Public IP

The easiest way is to have your own public IP.

The configuration assumes to have Web3 Reverse Proxy and Ethereum nodes connected in a local network
and expose the proxy service to the internet with the public IP.
The caveat is that you have to have the public IP.

## UPnP

If UPnP is enabled in the router, configure it in Web3 Reverse Proxy.
See Configuration page for further steps.

## Rent Public IP

It is possible to rent the public IP from external providers, for instance from cloud providers.
The configuration assumes to have the public IP at an external provider, 
Web3 Reverse Proxy and Ethereum nodes connected in a local network.
You need a kind of tunnel established to forward clients communication to the local network.
Providing a convenient solution is on our roadmap and it will be supported in the future.