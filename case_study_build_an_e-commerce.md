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

### What are the security goals:
* C.I.A
* Different sources have different goals. 
    * Database: availability
    * Web server: confidentiality..

#### Protect web servers
* Within web servers, isolate different parts.
* Separate UIDs on the Web Server
    * `Least Priviledge`: login CGI script runs as different user than browsing CGIs.

#### Protect database machines
* If the database is tampered with, VERY BAD THINGS can happen.
* How can database machines attacked?
    * Hacking attack: web server falls $$\rightarrow$$ database machine (issue arbitrary SQL statements to database).
    * SQL injection attack: bypass web server and directly affects database machine.
* Protection: `mandate the customer log in to the database`.
    * All customer-type operation must be accompanied by customer-type authentication.

### Protect inventory database
* Use a separate database and database machine for orders.
* Protecting information: credit card numbers `not` readable by web server.


### Danger points
* How are these devices managed?






