pam-google-authenticator
========================

imported from https://code.google.com/p/google-authenticator/

features added in this repository
---------------------------------

### RHOST_WHITELIST option

A list of hosts to your user configuration file, from which the
validation code will never be asked (trusted hosts)

### AUTH_CACHE option

Add this option to the user configuration file to only enter a
validation code only once in a time period from the same host
(temporary trusted host)

quick install guide for debian/ubuntu openssh
---------------------------------------------

    cd libpam
    make
    make test
    make install

edit these files :

* /etc/ssh/sshd_config

        ChallengeResponseAuthentication yes

* /etc/pam.d/sshd (under @common-auth)

        auth required pam_google_authenticator.so nullok noskewadj

