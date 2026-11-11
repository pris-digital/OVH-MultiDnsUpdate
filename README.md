# ovhDynDnsUpdate
Simple bash scripts to update the IP of a dynamic host on OVH.
This script is aimed at small websites where uptime is not the highest priority.

Featuring:
```
- Multiple domains being able to be updated
- Domains can be pointed to an IP with a port
- Multiple IP websites should agree on the IP
- Robustness against a site that checks IP going down
```
## How this works

Update process is described here: https://docs.ovh.com/fr/domains/utilisation-dynhost/

The script actually checks few things then simply call the following command:
```sh
curl -u ${DYNDNS_USER}:${DYNDNS_PASS} "http://www.ovh.com/nic/update?system=dyndns&hostname=${DYNDNS_DOMAIN}&myip=${PUBLIC_IP}"
```

The public IP is resolved using **Cloudflare**, **OpenDNS**, **Ipify** and **ipinfo.io**.
