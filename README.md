# sbc

Build a Kamailio session border controller for Futel.

## Requirements

We are using some versions of ubuntu, virtualbox, vagrant, ansible.

The Asterisk server should be at the name referred to in the XXX config files we currently write by hand. The Kamailio and Asterisk boxes must not be NATted to each other.

## Deploy to vagrant

vagrant up

## Deploy stage

XXX

## Promote stage to prod

XXX
update config to point to prod asterisk
rename sbc-stage to sbc-prod-foo.phu73l.net, droplet and network
wait for nameservice to propagate
kick users on sbc-prod-back?
shut down and strike sbc-prod-back

## Configure

XXX see README

## Add, remove Asterisk server

XXX

## Test

XXX see README
