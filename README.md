# Run Leia Action

This is a GitHub action that runs [Leia](https://github.com/lando/leia) tests. It will invoke the `leia` in your `package.json` if it can and if it can't it will fallback to a version configurable globally installed version.

It supports:

* All `pkg` supported node versions
* `x64|amd64` and `aarch64|arm64`
* `macos|linux|windows`.

If you are also looking to code sign/notarize the resulting binaries then check out [@lando/code-sign-action](https://github.com/marketplace/actions/code-sign-action).

## Required Inputs

These keys must be set correctly for the action to work.

| Name | Description | Example Value |
|---|---|---|
| `leia-test` | The Leia test file to parse and run.  | `examples/basics/README.md` |

> **NOTE:** If you want to run multiple tests we recommend you set up a [strategy matrix](https://docs.github.com/en/actions/using-jobs/using-a-matrix-for-your-jobs). We do this in our [dogfooded tests](https://github.com/lando/run-leia-action/blob/main/.github/workflows/pr-file-tests.yml).

## Optional Inputs

These keys are set to sane defaults but can be modified as needed.

| Name | Description | Default | Example |
|---|---|---|---|
| `debug` | Turn on debug mode. | `false` | `true` |
| `cleanup-header` | The cleanup headers to parse. | `Clean,Tear,Burn` | `Destroy` |
| `retry` | The amount of times to retry the test. | `1` | `3` |
| `setup-header` | The setup headers to parse. | `Start,Setup,This is the dawning` | `So it begins!` |
| `stdin` | Attach stdin when the tests are run. | `false` | `true` |
| `test-header` | The test headers to parse. | `Test,Validat,Verif` | `Testing 1 2 3` |
| `version` | The fallback global version of Leia to install if no local version is detected. | `latest` | `0.6.5` |

##  Usage

### Basic Usage

```yaml
- name: Run Leia Tests
  uses: lando/run-leia-action@v2
  with:
    leia-test: tests/leia-test-1.md
```

### Advanced Usage

**Everything, everywhere, all at once:**

```yaml
- name: Run Leia Tests
  uses: lando/run-leia-action@v2
  with:
    leia-test: tests/leia-test-1.md
```

## Changelog

We try to log all changes big and small in both [THE CHANGELOG](https://github.com/lando/run-leia-action/blob/main/CHANGELOG.md) and the [release notes](https://github.com/lando/run-leia-action/releases).

## Releasing

1. Correctly compile, bump versions, tag things and push to GitHub

  ```bash
  yarn release
  ```

2. Publish to [GitHub Actions Marketplace](https://docs.github.com/en/enterprise-cloud@latest/actions/creating-actions/publishing-actions-in-github-marketplace)

## Contributors

<a href="https://github.com/lando/run-leia-action/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=lando/run-leia-action" />
</a>

Made with [contrib.rocks](https://contrib.rocks).

## Other Resources

* [Important advice](https://www.youtube.com/watch?v=WA4iX5D9Z64)
