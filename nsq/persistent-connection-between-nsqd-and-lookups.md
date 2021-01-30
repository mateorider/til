# How NSQD Connects with nsqlookupd's
## June 17, 2019

NSQD and nsqlookupd's have a persistent TCP connection between them.

- Producers push messages to nsqd
- Nsqlookupd's read messages from nsqd
- Consumers read messages fromo nsqlookupd's via http requests
- Consumers cnonecet to ALL nsqlookupd's

from: https://speakerdeck.com/snakes/nsq-nyc-golang-meetup?slide=64
