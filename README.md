# OpenBSD ports

Intended as a supplement to the regular [OpenBSD ports][portshb] collection, this repository houses porting instructions for various third-party software. Ultimate goal of these ports is inclusion in the [OpenBSD CVS repository][portscvs] where viable.

## Install instructions

These instructions assume the files in this repository reside in `/usr/ports/mystuff`. Inclusion in the regular ports infrastructure is done through patching the root ports `Makefile`. The patch merely adds the `mystuff` to the list of `SUBDIR` entries. If you skip this step, build tools may skip the ports in the `mystuff` directory.

```bash
cd /usr/ports
git clone https://github.com/rkrieger/openbsd-ports.git mystuff
patch < mystuff/ports-Makefile.patch
```

If you wish to place items in another directory, adjust these instructions accordingly. Adding the files from the repository to the root of your ports tree is *not* recommended (due to existing `Makefile`s being overwritten by `git clone`).

## Caveats

As with anything in life, there are certain things to be mindful of:

1. These ports are created and maintained using the [OpenBSD-current][faqcurrent] branch. As such, I recommend *against* using these ports on regular releases of OpenBSD. This prevents you from shooting yourself in the foot and messing up your system's environment. For more details, review the [OpenBSD FAQ #5][faq5]. Still, there are no guarantees.
2. *Do not* extract the repository in your ports root directory, use a subdirectory (`mystuff`) instead. The repository contains `Makefile`s that would otherwise overwrite and break your ports checkout.


[faqcurrent]: http://www.openbsd.org/faq/current.html "Tracking OpenBSD-current"
[faq5]: http://www.openbsd.org/faq/faq5.html#BldGetSrc "FAQ 5 - Building the System from Source"
[ports7]: http://www.openbsd.org/cgi-bin/man.cgi?query=ports&sektion=7 "ports(7) man page"
[portscvs]: http://www.openbsd.org/cgi-bin/cvsweb/ports "OpenBSD CVS tree: ports"
[portshb]: http://www.openbsd.org/faq/ports/index.html "OpenBSD Porter's Handbook"
[portshb-guide]: http://www.openbsd.org/faq/ports/guide.html "OpenBSD porting guide"