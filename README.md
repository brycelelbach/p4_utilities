<!--
Copyright (c) 2017-8 NVIDIA Corporation
Reply-To: Bryce Adelstein Lelbach aka wash <brycelelbach@gmail.com>

Distributed under the Boost Software License v1.0 (boost.org/LICENSE_1_0.txt)
-->

# CUDA Thrust Perforce Utilities

*Reply-To:* [Bryce Adelstein Lelbach aka wash](brycelelbach@gmail.com)

This repository contains utilities to simplify basic Perforce tasks for 
  [NVIDIA's CUDA Thrust library] team:

- `p4-describe <args...>`: Invoke the Perforce command `p4 describe` with the diff style set to unified.
- `p4-description <changelist>`: Print the tab-indented description of the specified changelist without a terminating newline.
- `p4-integrate-change <changelist> <from-path> <to-path>`: Integrate (aka copy) the specified changelist from one Perforce path to another.
- `p4-listfiles <changelist>`: Print a scriptable list of the local paths of the files in the specified Perforce changelist.
- `p4-submit-shelved <changelist>`: Submit the specified **shelved** Perforce changelist.

This software is distributed under the [Boost Software License v1.0].

### Prerequisites

This software is designed to work on Linux-based operating systems.

**Required Software**

| Software                            | Version  |
| ----------------------------------- | -------- |
| [GNU Bash]                          | 4.2      |
| [GNU Make]                          | 4.1      |
| [Perforce Command-Line Client (p4)] | 2017.1   |

To install the Perforce Command-Line Client (p4) on Debian or Ubuntu
  systems, you'll need to add their Debian package repository to your list of
  Debian package sources:

```bash
deb http://package.perforce.com/apt/ubuntu trusty release
```

The following commands will add Perforce repoistory and update the list of
  available packages:

```bash
sudo bash -c 'echo "deb http://package.perforce.com/apt/ubuntu trusty release" > /etc/apt/sources.list.d/perforce.list'
sudo apt-get update
```

After you've done that, the following will install all of the requried
  prerequisites on Debian or Ubuntu systems:

```bash
sudo apt-get install python bash make git perforce-cli asciidoc docbook xmlto
```

### Installing

Then, you can just run `make` to build and install this software:

```bash
sudo make install
```

By default, this will install into `/usr/local`.
You can control the install root with the `INSTALL_ROOT` variable:

```bash
make install INSTALL_ROOT=/my/install/root
```

Alternatively, you can add the path to your checkout of this software to your `PATH` instead of installing.
If your default shell is `bash`, you can put something like this in your `.bashrc`:

```bash
export PATH="/path/to/this/checkout/:${PATH}"
```

[NVIDIA's CUDA Thrust library]:             https://thrust.github.com
[Boost Software License v1.0]:              https://boost.org/LICENSE_1_0.txt 
[GNU Bash]:                                 https://www.gnu.org/software/bash
[GNU Make]:                                 https://www.gnu.org/software/make
[Perforce Helix Command-Line Client (p4)]:  https://www.perforce.com/downloads/helix-command-line-client-p4

