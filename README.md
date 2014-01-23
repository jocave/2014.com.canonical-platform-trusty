2014.com.canonical-platform-trusty
==================================

These tests are meant to be run from a host with the target device hooked
up over a USB cable and with a working adb connection.

Setup
-----

*This is temporary, none of this should be necessary*

To run these tests you will need a non released version of plainbox that
provides manage.py, such version can be obtained by branching

    bzr branch lp:~zkrynicki/checkbox/provider-tools plainbox

From this branch you just need to install what's in the plainbox subdir,
ideally in a virtualenv

*To build/install successfully you will need libxslt1-dev among others*

    venv="$HOME/venv/plainbox"
    virtualenv --python python3 "$venv"
    . "$venv/bin/activate"
    cd provider-tools/plainbox
    python setup.py install

Then return to this directory 

    ./manage.py develop


Runnning
--------

To run all the tests provided just

    plainbox run --whitelist whitelists/platform.whitelist -f html \
        -o results.html


Tests
-----

The tests are provided compiled here as a convenience, to retrieve the 
source branch

*subject to change*

    lp:~sergiusens/+junk/gotests $GOPATH/src/launchpad.net/goget-ubuntu-touch-platform-tests

To build you will require to have a golang environment setup.
