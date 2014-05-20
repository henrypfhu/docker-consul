# kelseyhightower/consul

## Build

```
docker build -t kelseyhightower/consul .
```

## Usage

### Run consul as the first node in the cluster

```
docker run -d -P kelseyhightower/consul -bootstrap -client 0.0.0.0 -server
```

Check the logs

```
docker logs <CONTAINER_ID>
```

```
==> WARNING: Bootstrap mode enabled! Do not enable unless necessary
==> WARNING: It is highly recommended to set GOMAXPROCS higher than 1
==> Starting Consul agent...
==> Starting Consul agent RPC...
==> Consul agent running!
       Node name: 'b0fefc4e18e0'
      Datacenter: 'dc1'
          Server: true (bootstrap: true)
     Client Addr: 0.0.0.0 (HTTP: 8500, DNS: 8600, RPC: 8400)
    Cluster Addr: 172.17.0.2 (LAN: 8301, WAN: 8302)
```

### Run consul with the web UI

The `/opt/consul/web_ui` directory is bundled in the container.

```
docker run -d -P kelseyhightower/consul -bootstrap -client 0.0.0.0 -server -ui-dir /opt/consul/web_ui
```
