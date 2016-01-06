# Fail Close Square lab
This directory contains the necessary Cisco (IOS 12.4) configuration files to setup
the square topology presented in the Central Control over Distributed Routing
presented at SIGCOMM2015.

It also contains the necessary binding file in order to setup locally visible fake
nodes (through the use of the distribute list in the OSPF configuration).

Running the controller software is a two-step process:
    1. Connect your machine to one of the routers, and launch the southbound controller
     specifying on which interface you are physically connected:
     sudo python -m fibbingnode eth0
     You might also want to provide another default.cfg file (e.g. to sync OSPF
     timers between the controller and the real routers)
    2. Launch the Northbound controller,
     python demo.py

You should now observe that both destination prefixes are routed independently
from each other.
