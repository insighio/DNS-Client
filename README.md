# DNS-Client

MicroPython library for querying DNS records.

Tested on Pycom GPy module.

example IPv4:

```python
import usocket
from query import dns_resolve

socket = usocket.socket(usocket.AF_INET, usocket.SOCK_DGRAM)

url='google.com'
dns_server="8.8.8.8"
ipv6 = False

resolvedIPs = dns_resolve(socket, url, dns_server, ipv6)
print("Resolved IP list: " + str(resolvedIPs))

socket.close()
```

example IPv6

```python
import usocket
from query import dns_resolve

socket = usocket.socket(usocket.AF_INET, usocket.SOCK_DGRAM)

url='google.com'
dns_server="2001:4860:4860::8888"
ipv6 = True

resolvedIPs = dns_resolve(socket, url, dns_server, ipv6)
print("Resolved IP list: " + str(resolvedIPs))

socket.close()
```
