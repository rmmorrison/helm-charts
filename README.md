# helm-charts

This repository contains publicly accessible Helm charts for projects that I'm working on.

Note that unless otherwise specified, these charts use chart API version 2 and thus require Helm 3 to be deployed on a Kubernetes cluster.

## Using the Charts

Charts (under the `charts/` directory in this repository) are automatically built and published to this repository's GitHub Pages, which can be used as a Helm repository:

    $ helm repo add rmmorrison https://rmmorrison.github.io/helm-charts
    "rmmorrison" has been added to your repositories
    
    $ helm repo update
    Hang tight while we grab the latest from your chart repositories...
    ...Successfully got an update from the "rmmorrison" chart repository
    ...Successfully got an update from the "bitnami" chart repository
    Update Complete. ⎈Happy Helming!⎈

    $ helm search repo chatterbox
    NAME                    CHART VERSION   APP VERSION     DESCRIPTION
    rmmorrison/chatterbox   0.1.1           1.0.0-pre2      chatterbox is a Discord bot intending to provid...

You can now install any chart provided by this repository, for example:

    helm install chatterbox . \
      --set discord.token="<token>" \
      --set discord.ownerId=":<owner ID>" \
      --set database.url="<JDBC database URL>" \
      --set database.username="<username>" \
      --set database.password="<password>"