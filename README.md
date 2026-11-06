# Vector snap

Please check the [github](https://github.com/vectordotdev/vector) repo for the project and [vector.dev](https://vector.dev) for more details.


## Build

Install Snapcraft and configure LXD, then run:

```sh
snapcraft pack --use-lxd
sudo snap install --dangerous ./vector_0.61.0_amd64.snap
vector --version
```

This takes around 45 min to complete building the snap on a GitHub Actions 4 core machine.

## Verify

```sh
sudo vector validate /var/snap/vector/current/vector.yaml
sudo snap start --enable vector.service # You can also enable the service
sudo snap logs vector.service
```

Connect host observation interfaces if your pipeline needs them:

```sh
sudo snap connect vector:log-observe
sudo snap connect vector:system-observe
```

## Tracks

Tracks follow upstream minor releases. For example, Vector 0.61.x is available in the `0.61/stable` channel.
