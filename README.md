# node-policies

Apply a self-imposed sandbox on your CLI or dockerized Node.js apps. You can use this library to
augment the experimental [Node 17 Policies](https://nodejs.org/api/policy.html) feature.

This library will restrict 

## Policies

- Inbound/Outbound Requests from Domains / DNS
- Inbound/Outbound Websockets
- File/Directory Access
- Exec usage
- Cluster (unreffed)
- Workers
- Process.ENV access
- Integrity Checks
- Import/Require

## Policies File

Create a `.policiesrc.json` or a `.policiesrc.js`

```
{
    "extends": "...", 
    "onError": "log", // throw or exit
    "policies": {
        "inbound/http": [
            {
                access: 'deny',
                resources: '*',
            },
            {
                access: 'allow',
            }
        ]
    }
}
```