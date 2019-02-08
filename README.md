# Smoke Test Buildkite Plugin

A [Buildkite plugin](https://buildkite.com/docs/agent/v3/plugins) for smoke testing OPX Debian packages with [`opx-test`](https://github.com/open-switch/opx-test).

## Example

```yaml
steps:
  - command: build.sh
    artifacts: "pool/stretch-amd64/*"
  - wait
  - plugins:
      - opx-infra/smoke-test#v0.1.0:
          download: pool/stretch-amd64
          distribution: stretch
```

## Configuration

### `download` (required)

The path to use for downloading artifacts to publish.

### `slug` (optional)

Append `${BUILDKITE_PIPELINE_SLUG}` to the `download` path.

### `distribution` (optional)

The Debian distribution to publish to. The default is `stretch`.

## License

MIT (see [LICENSE](LICENSE))
