# AMIGO-specific setup

To set up SliceTracker in [AMIGO](http://www.brighamandwomens.org/research/amigo/default.aspx), you will need to:

* Connect the Macbook directly to the ethernet cable labeled "AMIGO Client 3 or 4" coming from the ethernet outlet next to the MR-workstation \(under the table\)
* Apply the network configuration \(see Network configuration details\)
* On the MR console, use AMIGO-CLIENT-4 destination to send the data

NOTE: there is an internal port forwarding configured in the Macbook which forwards incoming data on port 104 to port 11112.

### Network configuration details

| Configuration parameter | Value |
| --- | --- |
| IP | 172.22.99.143 |
| Subnet Mask | 255.255.255.192 |
| Default Gateway \(router on OS X\) | 172.22.99.129 |



