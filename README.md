# Download plugin for Buildkite

A Buildkite plugin which will download some files before running a build step.

The plugin creates a new directory for the downloads, and sets an environment
variable called `BUILDKITE_DOWNLOADS_PATH` with the name of that directory. The
directory is deleted after the build.

## Example

The following pipeline downloads this file and then prints it out.

```yaml
steps:
  - command: cat $${BUILDKITE_DOWNLOADS_PATH}/README.md
    plugins:
      - matrix-org/download#v1.1.0:
          urls:
            - https://raw.githubusercontent.com/matrix-org/download-buildkite-plugin/master/README.md
```

(The example above uses `$$` to access the environment variable with the
downloads directory, because that variable is not set when the pipeline file is
interpolated.)

## Configuration

### `urls` (required, array)

The list of URLs to download.
