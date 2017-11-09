
# Instances

Instances run on any web server and can be made private or public. Multiple instances may
also run on a single web server using different HTTP ports. Because instances require direct
access to the blockchain transaction data, they typically would need to be running as a 
blockchain node or make calls to the target blockchain using an RPC client (for example `geth`).

We don't make any guarantees on how instances are managed, so consumers will need to host
their own instances, subscribe to only trusted providers, or subscribe to multiple instances to
ensure they receive up-to-date blockchain events in the case a provider goes down.
