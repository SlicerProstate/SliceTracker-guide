# L1 Bay2-specific setup

Connect Ethernet cable to a network port underneath the printer. Lower right port in the right panel should be used (it is labeled **"Slicer"**).

### Network configuration details

| Configuration parameter | Value | Comment
| -- | -- | -- |
| IP | 192.168.1.3 | Dedicated to the workstation; can be used in Bay 2 area; The IP address is registered in the Bay 2 scanner host for DICOM transfer
 |
| Subnet Mask | 255.255.255.0 | |
| Gateway| 172.23.204.1 | |
| DNS | 170.223.101.17 | |


### Test connection
To check the connection, press Ctrl+Esc on the MRI Host to pop up windows menu, choose "Run...," type 

```
cmd
```

and hit Enter. Once the command terminal opens, type:

```
ping 172.23.204.62
```

If the network is configured properly, you will see responses like:

```
Reply from 172.23.204.62 bytes=32 time<1ms TTL=64
```
If there is any issue, the terminal shows network unreachable error.







