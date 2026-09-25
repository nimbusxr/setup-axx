# setup-axx

Installs [axx](https://github.com/nimbusxr/axx), the human-readable acceptance testing framework
for the agentic era, in GitHub Actions on Linux, macOS and Windows, and adds it to `PATH`.

```yaml
- uses: nimbusxr/setup-axx@v1
  with:
    version: latest   # or a version such as 0.1.0, or nightly
- run: axx run --format junit:build/axx/junit.xml
```

| Input | Default | |
| --- | --- | --- |
| `version` | `latest` | A version such as `0.1.0`, `latest` (the newest release, pre-releases included) or `nightly`. |
| `token` | `${{ github.token }}` | The token used to list releases, which avoids API rate limits. |

The installed version is the `version` output.

The action downloads the release archive for the runner's OS and architecture and checks it
against the release's `checksums.txt`. Every `0.x` release of axx is a GitHub pre-release, so
`latest` is resolved from the list of releases rather than GitHub's "latest release".

`install.sh` and `install.ps1` are copies of axx's
[install scripts](https://github.com/nimbusxr/axx/tree/main/scripts), which also serve
`curl -fsSL https://axx.nimbusxr.us/install.sh | sh`.

## License

Apache-2.0. See [LICENSE](LICENSE) and [NOTICE](NOTICE).
