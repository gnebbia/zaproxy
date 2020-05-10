# ZAP

Fast passive scan of 1 minute (around 600 pages):
```sh
docker run -t owasp/zap2docker-weekly zap-baselyine.py -t <target_url> 
```
this is very configurable if needed.

## Basic Functionalities

OWASP ZAP is a full-fledged application to perform manual and automatic
web application vulnerability assessment.

It allows testers to perform plenty of operations and tests. In addition,
it is also extensible and modifiable because it contains a scripting engine
and it's open source.

The main functionalities are:
- intercepting proxy that can break on each request;
- request modifier
- fuzzer
- spider
- active scanner
- ajax spider
- web vulnerability scanner 
- HUD
- report generation
- other functionalities...


## Modes

ZAP can work through four modes.
Before understanding what modes are it would be useful
to define the concept of "dangerous action".

In ZAP we consider "dangerous actions" the following actions:
- spidering, used to find new nodes by visiting the site and making HTTP requests to
             newly found links;
- active scanning, used to find vulnerabilities on nodes, it tries basic attack vectors on the nodes
                   for different attacks, both attack intensity and alert threshold can be configured;
- forced browsing, used to find new nodes by using lists, such as dirbuster, dirb, and so on...
- fuzzing, used to fuzz any part of request content;
- open requests with request editor, to modify requests manually;


- **Safe Mode**, this mode doesn't allow to perform any "dangerous action"
    on any URL;
- **Protected Mode**, this mode allows to perform "dangerous actions" only
    on URLs which are inside our scope;
- **Standard Mode**, in this mode the user can do anything;
- **ATTACK Mode**, in this mode the user can do anything, additionally,
    as soon as new nodes inside the current scope are discovered, they
    are actively scanned;

So in any mode we are anyway somewhat safe in the sense that out of scope
nodes are not actively scanned/attacked.


In Standard and ATTACK modes we can also run a fully automatized web application
scan which works as a web vulnerability scanner for the whole application.
This is basically what ZAP calls "Automated Scan" and is accessible from the 
*Quick Start* menu.

This will basically perform different actions automatically on the web application
in scope, such a spidering the
application, ajax spidering the application, active scanning each node and so on.

We can always check what is the current status of the scan by checking the
"Progress" string from the *Quick Start* menu after having launched
the automated attack.


