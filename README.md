This is just a quick set of sample configuration files to get started
with Receptor.  This runs a three-node network, all running on localhost,
with nodes named foo, bar and baz.

To use this:

- Clone the main Receptor repo.
- Install Receptor.  (`make receptor`, put the `receptor` binary in your path.)
- Install receptorctl.  (`make version`, `cd receptorctl`, `python3 setup.py`)

- Clone this repo.
- Run `makecerts.sh`, which will create certificates under `certs/`.
- Run `receptor -c testconfig_foo.yml` to start the `foo` node.
- Start the `bar` and `baz` nodes similarly.  They should talk to each other.
- Set your socket environment variable with `export RECEPTORCTL_SOCKET=/path/to/receptor.sock`
- Interact with Receptor using receptorctl

Once it's up and running, here are some interesting commands to try out:

- `receptorctl status`
- `receptorctl traceroute baz`
- `receptorctl connect baz bash --tls-client foo_client --raw`
- `seq 10 | receptorctl work submit sleepcat --payload=- --follow --rm --node=baz --tls-client foo_client`

