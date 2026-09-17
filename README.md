# Depot CI Snapshot Action

Snapshot Depot CI filesystem changes and push filesystem snapshots to the Depot registry.

## Usage

```yaml
jobs:
  snapshot:
    runs-on: depot-ubuntu-latest
    steps:
      - uses: depot/snapshot-action@v1
        with:
          image: orgid.registry.depot.dev/repo:tag
```

## Inputs

| Input      | Required | Default                 | Description                                                     |
| ---------- | -------- | ----------------------- | --------------------------------------------------------------- |
| `token`    | No       | `''`                    | Depot API token used as registry password.                      |
| `image`    | **Yes**  | —                       | Full image reference (e.g. `orgid.registry.depot.dev/repo:tag`) |
| `base`     | No       | `/dev/vdb`              | Base block device                                               |
| `upper`    | No       | `/rw/.snap/upper`       | Upper directory for overlay                                     |
| `snapshot` | No       | `/rw/overlay:/rw/.snap` | Overlay:snap mapping                                            |
| `version`  | No       | `latest`                | Snapshot binary version                                         |

## License

MIT License - see [LICENSE](LICENSE) for details.

## Privacy

This Action contacts Chainguard's licensing server to verify authorization. Connection metadata (IP address, GitHub repository identifier, timestamp, and any metadata encoded in the auth token) is transmitted to Chainguard, Inc. even if authorization is denied in accordance with our [Privacy Notice](https://www.chainguard.dev/legal/privacy-notice)
