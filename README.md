This is just a quick set of sample configuration files to get started
with Receptor.  This runs a three-node network, all running on localhost,
with nodes named foo, bar and baz.

To use this:

- Install Receptor.  (Clone the repo, `make receptor`, put it in your path.)
- Run `makecerts.sh`, which will create certificates under `certs/`.
- Run `receptor -c testconfig_foo.yml` to start the `foo` node.
- Start the `bar` and `baz` nodes similarly.  They should talk to each other.
- Interact with Receptor by connecting to the control sockets, optionally using receptorctl
