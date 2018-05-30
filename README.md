# SUPPLY CHAIN SECURITY

[![Build status](https://travis-ci.org/kbabioch/supplychain?branch=master)](https://travis-ci.org/kbabioch/supplychain)
[![Code coverage](https://codecov.io/gh/kbabioch/supplychain/branch/master/graph/badge.svg)](https://codecov.io/gh/kbabioch/supplychain)

This repository contains a set of tools and scripts to analyze and improve the
supply chain security around RPM files and the Open Build Service (OBS). This
can be helpful in identifying potentials to improve on security, e.g.:

- Scan for unused signature files, that are available upstream, but not used
  during the build process to verify the authenticity of the sources
- Use of unencrypted transfer channels, e.g. using `http://`,
  although `https://` is available

It also contains tools to quickly create keyrings, required for verification of
signed source files.

## TOOLS

### scs-keyring

This script will extract the OpenPGP key IDs that were used to sign the
provided files and will try to retrieve them using public keyservers.
It minimizes these keys and exports the whole keyring to a file. The
resulting keyring file can be used to verify all available sources, e.g.
within a RPM spec file.

### scs-https-replace

This script scans the input for any `http://` URLs, and checks whether the
appropriate `https://` URL is also available. It replaces these URLs, if
applicable. Optionally, it can also check whether the returned resource is
actually the same.

## LICENSE

[![GNU GPLv3](http://www.gnu.org/graphics/gplv3-127x51.png "GNU GPLv3")](http://www.gnu.org/licenses/gpl.html)

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.

