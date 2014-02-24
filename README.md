# OpenBSD ports

Intended as a supplement to the regular [OpenBDSD ports][portshb] collection, this repository houses porting instructions for various third-party software. Ultimate goal of these ports is inclusion in the [OpenBSD CVS repository][portscvs] where viable.

## Install instructions

This manual assumes the ports in this repository are placed in `/usr/ports/mystuff`. For inclusion in the regular ports infrastructure, ensure the main ports `Makefile` contains the appropriate `SUBDIR` line. Otherwise, build tools may skip the ports in the `mystuff` directory.

```bash
cd /usr/ports
git clone https://github.com/rkrieger/openbsd-ports.git mystuff
patch < mystuff/ports-Makefile.patch
```

## Caveats

As with anything in life, there are certain things to be mindful of:

These ports are created and maintained using the  [OpenBSD-current][faq.current] branch. As such, I recommend *against* using these ports on regular releases of OpenBSD. This prevents you from shooting yourself in the foot and messing up your system's environment. For more details, review the [OpenBSD FAQ #5][faq/5]. Still, there are no guarantees.


## Links

[faq/current]: http://www.openbsd.org/faq/current.html "Tracking OpenBSD-current"
[faq/5]: http://www.openbsd.org/faq/faq5.html#BldGetSrc "FAQ 5 - Building the System from Source"
[ports7]: http://www.openbsd.org/cgi-bin/man.cgi?query=ports&sektion=7 "ports(7) man page"
[portscvs]: http://www.openbsd.org/cgi-bin/cvsweb/ports "OpenBSD CVS tree: ports"
[portshb]: http://www.openbsd.org/faq/ports/index.html "OpenBSD Porter's Handbook"
[portshb-guide]: http://www.openbsd.org/faq/ports/guide.html "OpenBSD porting guide"
