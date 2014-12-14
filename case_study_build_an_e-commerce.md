# Case study: build an e-commerce

## Componenents
* Web server
* Replicated web server, for load-sharing and reliability
* System admins
* Development mahinces
* Developer access
* Console servers
* Environmental control systems - air conditioning, power, backup generators..
* Backup servers
* DNS servers
* ... (Many more!)

## How to connect pieces?
* Which pieces should be separated?
* E.g A billing system: 4 different database..
    ![Web server Complex]()

## Why so complex?
* Availability - primarily against ordinary fialtures.
* Everything is replicated: routers, links, Ethernets, servers..

### Inverse proxy
* Inverse proxies are effectively firewalls: only ports 80 (http) and 443 (https).
* Database servers are `not` accessible from outside; when a request comes in, you must go through web server first.

### Danger points
* How are these devices managed?




