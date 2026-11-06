# Vector snap

Please check the [github](https://github.com/vectordotdev/vector) repo for the project and [vector.dev](https://vector.dev) for more details.


## Build

Install Snapcraft and configure LXD, then run:

```sh
snapcraft pack --use-lxd
sudo snap install --dangerous ./kodoroki-vector_0.61.0_amd64.snap
kodoroki-vector.vector --version
```

This takes around 45 min to complete building the snap on a GitHub Actions 4 core machine.

To use `vector` as the CLI command after installation:

```sh
sudo snap alias kodoroki-vector.vector vector
vector --version
```

## Verify

```sh
sudo kodoroki-vector.vector validate /var/snap/kodoroki-vector/current/vector.yaml
sudo snap start --enable kodoroki-vector.service # You can also enable the service if you like
sudo snap logs kodoroki-vector.service
```

Connect host observation interfaces if your pipeline needs them:

```sh
sudo snap connect kodoroki-vector:log-observe
sudo snap connect kodoroki-vector:system-observe
```

## Tracks

Tracks follow upstream minor releases. For example, Vector 0.61.x is available in the `0.61/stable` channel.
