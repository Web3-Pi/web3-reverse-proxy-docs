## Requirements

To run the proxy, `python` is required

```
python >= 3.10
```

## Installation

At first create a data directory for Web3 Pi proxy instance and change the working directory to it.

You may wish preferably to use `venv`
```bash
python3 -m venv venv
source venv/bin/activate
```

Get latest version from pypi

```
pip install web3pi-proxy
```

## Run

Before running, provide configuration file `.env`, see Configuration and Monitoring.

Simply execute

```
web3pi-proxy
```

Note that the state data is persisted in the file
```
.w3appdata/web3pi_proxy.sqlite3
```
It is safe to delete this file when the proxy is down in order to clear stats and settings.

## Admin panel

When the proxy is started, the access url to the admin panel is generated.
Check logs and grep the line that looks like this
```
Access admin portal with:
http://0.0.0.0:6561/?token=DJQPiFYBAks9n2vedLIXLtvUu3kuTe60
```
Update the address part `0.0.0.0` in the url according to your network configuration if necessary.
The excerpt above is an example, use a token that is included in your logs.
Note that the access token may change in the next run of the proxy.