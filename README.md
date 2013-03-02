Octave-forge helper scripts for Archlinux
=========================================

newpkg
------

There is a large number of octave packages, and this script helps you create a
PKGBUILD automatically. It detect the latest package version released on
octave.sf.net and reads necessary configurations from the package's DESCRIPTION
file.

- To create a new package <pkg>:

    ./newpkg <pkg>

The new package will be created in `octave-<pkg>/`.

- To update a package <pkg>, I like to do this:

Create new PKGBUILD from scratch.

    rm -rf octave-<pkg>
    ./newpkg <pkg>

Compare results to committed version and restore custom changes.

    git diff
    git checkout -p

Test and commit.

    cd octave-<pkg>
    makepkg -s -i -f
    git add -u
    git commit -m '<pkg> <version>'

buildall
--------

This will rebuild and install the packages which are expected to work.

list-licenses
-------------

Outputs an overview of licenses used by the octave-forge packages.
