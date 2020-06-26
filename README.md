# pipeline-buildah-nodejs-demo

Beispiel einer Pipeline, die folgendes kann:
- Erstellung eines Docker Images

Die Dependencies werden mit Renovate aktualisiert. Mehr Infos: https://github.com/renovatebot/renovate

```
name: Standard Pipeline

on:
  pull_request:
    branches: '**'
  push:
    branches:
      - develop
  schedule:
    - cron: '0 20 * * 5'

jobs:
  buildah:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: build
      run: buildah bud -t buildah-demo .
```

## Referenzen
- Buildah: https://github.com/containers/buildah
