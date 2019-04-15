# L1 Bay2-specific setup

Connect Ethernet cable to a network port underneath the printer. Lower right port in the right panel should be used \(it is labeled **"Slicer"**\).

### Network configuration details

| Configuration parameter | Value | Comment |
| --- | --- | --- |
| IP | x | Dedicated to the workstation; can be used in Bay 2 area; The IP address is registered in the Bay 2 scanner host for DICOM transfer |
| Subnet Mask | x |  |
| Gateway | x |  |

### Test connection from MRI host computer

To check the connection, press Ctrl+Esc on the MRI host to pop up windows menu, choose "Run...," type

```
cmd
```

and hit Enter. Once the command terminal opens, type:

```
ping x
```

If the network is configured properly, you will see responses like:

```
Reply from x bytes=32 time<1ms TTL=64
```

If there is an issue, the terminal shows network unreachable error.

