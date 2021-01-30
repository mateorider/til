# Talking with NSQ
## January 15, 2020

You can communicate with NSQ over HTTP or TCP

### NSQD
4150 - tcp
4151 - http

### NSQLOOKUPD
4160 - tcp
4161 - http

If I want to hit NSQ from a golang program, I have to use the tcp ports. If I’m using curl, I should use the http ports.
