# steampipe-plugin-build-push-action

GitHub action to build your [Steampipe][] plugin and push it to GitHub packages.

## Usage

```yaml
name: Build and Deploy OCI Image

on:
  push:
    tags:
      - 'v*'

jobs:
  build:
    name: Build and publish
    runs-on: ubuntu-latest
    steps:
      - uses: francois2metz/steampipe-plugin-build-push-action@v0
        env:
          GITHUB_TOKEN: "${{ secrets.GITHUB_TOKEN }}"
```

[Steampipe]: https://github.com/turbot/steampipe
