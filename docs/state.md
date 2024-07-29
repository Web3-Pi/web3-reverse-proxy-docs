
Web3Pi Proxy persists state data like usage stats and settings between runs.
In the place that the proxy is run a data file is created.
```
.w3appdata/web3pi_proxy.sqlite3
```
It is safe to delete this file when the proxy is down in order to clear stats and settings.

Note that if you run the proxy in a new location, the state is carried over automatically.
And you cannot run two instances of the proxy simultaneously in the same location.
