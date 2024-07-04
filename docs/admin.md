When the proxy is started, the access url to the admin panel is generated.
Check logs and grep the line that looks like this
```
Access admin portal with:
http://0.0.0.0:6561/?token=DJQPiFYBAks9n2vedLIXLtvUu3kuTe60
```
Update the address part `0.0.0.0` in the url according to your network configuration if necessary.
Note that the access token may change in the next run of the proxy.

![Admin Panel](admin.png)

## Users

Users are managed with Admin Panel. Each user is identified by its API key.
It can be set the limit for calls and transferred bytes. 
In order to authorize a user in a RPC call, add API key to the path like this
```
http://localhost:6512/<API-key>
```

## Nodes stats

Admin panel provides simple usage stats on connected Ethereum nodes.

## Billing

The functionality is under construction
