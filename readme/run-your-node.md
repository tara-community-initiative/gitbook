---
description: This page describes the basic operation for you to run a node
---

# Run your node

**If you used to be an old node operator or are migrating from an existing and running instance, make sure you use your original** `wallet.json`**.**&#x20;

Instructions remain the same as the [official documentation](https://taraxa.gitbook.io/taraxa-network/node-setup/lite-consensus-node-beta) but we provide:

* an updated Docker compose configuration file so the snapshot-puller service has a valid `SNAPSHOT_URL` environment variable
* an updated `mainnet.json` file with valid boot nodes (without this, your node won't find any peers)

### Requirements

* You need to have docker and docker compose installed.
* You need 30 GB of free storage (to download and extract the archive).

### Fresh install

```shellscript
mkdir -p mainnet/config
cd mainnet

wget https://raw.githubusercontent.com/tara-community-initiative/dev-ops/main/docker/compose.yaml -O compose.yaml
wget https://raw.githubusercontent.com/tara-community-initiative/dev-ops/main/docker/snapshot-init.sh -O snapshot-init.sh
wget https://raw.githubusercontent.com/tara-community-initiative/dev-ops/main/docker/mainnet.json -O config/mainnet.json

docker compose up -d
docker compose logs
```

If you're going on a fresh setup, you'll probably have to wait at least 10 minutes or so, until the snapshot-puller get the latest archive.

Backup the `wallet.json` file which is in `config/wallet.json` (only if it's a fresh setup).

### Migrating from an existing instance

If you have your `wallet.json`, just before running `docker compose up -d`, copy your file to the `config` folder.

If you have an old docker compose file, make sure that it looks like this:

```yaml
services:
...
  node:
    image: taraxa/taraxa-node:v1.14.2
    restart: always
    ports:
      - "10002:10002"
      - "10002:10002/udp"
      - "7777:7777"
      - "8777:8777"
    entrypoint: /usr/bin/sh
    command: >
      -c "mkdir -p /opt/taraxa_data/data &&
          taraxad --chain mainnet --wallet /opt/taraxa_data/conf/wallet.json --config /opt/taraxa_data/conf/mainnet.json --data-dir /opt/taraxa_data/data --overwrite-config --rpc.enable-test-rpc"
    volumes:
      - ./config:/opt/taraxa_data/conf
      - ./data:/opt/taraxa_data/data
```

In the `command` section:

* it must not contain the `--light` flag to avoid pruning the database. This was an improvement made by the official team to avoid wasting time pruning data when running the node from a fresh snapshot.
* it must contain the `--rpc.enable-test-rpc` so we can better map the running node on the network.

### Firewall

Your firewall must accept connections on ports 10002, 7777, 8777.

### Important security notices

* Always keep a copy of your `wallet.json` file in a safe location and never use the only copy you have in production. Any issue on the host preventing access to your server, or bugs in the application can lead to a corrupted file which you could not recover from.
