# Download plugin for Buildkite

A Buildkite plugin which will download some files before running a build step.

## Example

The following pipeline downloads this file and then prints it out.

```yaml
steps:
  - command: cat downloads/README.md
    plugins:
      - matrix-org/download#v1.0.0:
          target-directory: downloads
          urls:
            - https://raw.githubusercontent.com/matrix-org/download-buildkite-plugin/master/README.md
```

## Configuration

### `urls` (required, array)

The list of URLs to download.

### `target-directory` (optional, string)

Where to put the downloaded files. Defaults to the working directory.
