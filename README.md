# steampipe-plugin-build-push-action

GitHub action to build your [Steampipe][] plugin and push it to GitHub packages.

Your repository should be named `steampipe-plugin-thename`. Once the package has been pushed, you can install with steampipe with: `steampipe plugin install ghcr.io/youruser/thename`.
The config file should reference `plugin = "ghcr.io/youruser/thename"` to work:

```hcl
connection "thename" {
    plugin = "ghcr.io/youruser/thename"

    ....
}
```

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

## License

MIT

[Steampipe]: https://github.com/turbot/steampipe
