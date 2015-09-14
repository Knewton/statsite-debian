Statsite
========

This directory can be used for building a package for statsite.

Unpacking the Source
--------------------

Packages can be built easily within the Vagrant virtual machine. Use
Vagrant to create a virtual machine and login to the box.

Download an upstream tarball from GitHub. This can usually be found at
https://github.com/armon/statsite/archive/v${version}.tar.gz. Unpack the
tarball and remove the `deps/check-0.9.8` directory. The packaged
sources in this directory cause the debian package build to fail. Repack
the tarball as a debian original tarball.

Example:

    $ wget https://github.com/armon/statsite/archive/v0.7.1.tar.gz
    $ tar -xzf v0.7.1.tar.gz
    $ rm -r statsite-0.7.1/deps/check-0.9.8
    $ tar -czf statsite_0.7.1.orig.tar.gz statsite-0.7.1/

If rebuilding the package, just unarchive the original tarball.

Building the Debian Package
---------------------------

In the virtual machine, copy the folder at `/home/vagrant/debian` to the
debian folder inside of the source tree. Then run `debuild -uc -us`.
