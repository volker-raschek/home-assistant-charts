# homeassistant-charts

[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/volker-raschek)](https://artifacthub.io/packages/search?repo=volker-raschek)

This is a helm chart for [homeassistant](https://github.com/morpheus65535/homeassistant/).

This helm chart can be found on [artifacthub.io](https://artifacthub.io/) and can be installed via helm.

```bash
helm repo add volker.raschek https://charts.cryptic.systems/volker.raschek
helm install homeassistant volker.raschek/homeassistant
```

## Customization

### Mountpoints

As default all configuration and media files will be stored inside the container filesystem. Inside the `values.yaml`
files the sections `volumes` and `volumeMounts` to mount additional volumes inside the container. For example to mount
the directories containing configuration and media files on separate mountpoints. The `values.yaml` contains also some
examples to mount the directories inside the host filesystem.

#### Troubleshooting

The application use as backend a sqlite database. If the database is stored on a network filesystem like nfs, it is
quite possible that the application lacks or is unusable, because sqlite is not designed to be used as a database
accesses over network.
