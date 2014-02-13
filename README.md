# Overview

DataStax OpsCenter makes it easy to manage Cassandra and DataStax Enterprise clusters. It allows administrators, architects and developers to manage, monitor and control even the most complex database workloads with point-and-click ease from a centralized web browser.

This charm deploys DataStax from their upstream repository, and configures the dashboard to auto-load from any cassandra DB you relate to OpsCenter.

## Quick Start

```
juju deploy cassandra -n 4
juju deploy opscenter
juju add-relation cassandra:database opscenter:db
```
This will deploy a 4 node cluster of CassandraDB units, and OpsCenter management interface.

With the relationship defined, OpsCenter connects to the first node that responds to the relationship. From there, OpsCenter auto configures the remainder of the dashboard according to the cluster units it detects from the seed host.

You can then browse to http://ip-address:8881 (by default) to configure the service.

## Known Limitations and Issues

This Charm does not support scale-out usage. If you add units to opscenter, they will be running independently of one another.


# Configuration Options

  - port: The binding port to run OpsCenter's Web UI
    - `juju set opscenter port=9001`

  -interface: Used for binding to interfaces, eg: bind to an internal IP only
    - `juju set interface 10.0.5.5`

  - ssl: Enable/Disable SSL
    - `juju set ssl=true`

  - ssl-key: Contents of your SSL Key (.key)
    - `juju set ssl-key=`cat ssl.key``

  - ssl-cert: Contents of your SSL Cert (.pem)
    - `juju set ssl-cert=`cat ssl.pem``

  - ssl-port: The port to bind secure traffic to
    - `juju set ssl-port=9002`

# Contact Information

Maintainer: Charles Butler <charles.butler@canonical.com>


## DataStax OpsCenter

- Upstream website: [DataStax](http://www.datastax.com/)
- Upstream Forums: [DataStax Forums](http://www.datastax.com/support-forums/forum/opscenter)
