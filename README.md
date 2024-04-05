# Run Leia Action

This is a GitHub action that runs [Leia](https://github.com/lando/leia) tests. It will use the `leia` in your `package.json` if it can and if it can't it will fallback to a globally installed version that is configurable with `version`.

## Required Inputs

These keys must be set correctly for the action to work.

| Name | Description | Example Value |
|---|---|---|
| `leia-test` | The Leia test file to parse and run.  | `examples/basics/README.md` |

> **NOTE:** If you want to run multiple tests we recommend you set up a [strategy matrix](https://docs.github.com/en/actions/using-jobs/using-a-matrix-for-your-jobs). See our [dogfooded tests](https://github.com/lando/run-leia-action/blob/main/.github/workflows/pr-files-tests.yml) for an example.

## Optional Inputs

These keys are set to sane defaults but can be modified as needed.

| Name | Description | Default | Example |
|---|---|---|---|
| `cleanup-header` | The cleanup headers to parse. | `Clean,Tear,Burn` | `Destroy` |
| `retry` | The amount of times to retry the test. | `1` | `3` |
| `setup-header` | The setup headers to parse. | `Start,Setup,This is the dawning` | `So it begins!` |
| `shell` | The shell to use. | `auto` | `bash` |
| `stdin` | Attach stdin when the tests are run. | `false` | `true` |
| `test-header` | The test headers to parse. | `Test,Validat,Verif` | `Testing 1 2 3` |
| `version` | The fallback global version of Leia to install if no local version is detected. | `latest` | `0.6.5` |

> **NOTE:** Please read Leia's [shell considerations](https://github.com/lando/leia#shell-considerations) for details on how `shell: auto` works.

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
    debug: true
    cleanup-header: Clean
    retry: 0
    setup-header: Setup
    shell: bash
    stdin: true
    test-header: Test
    version: "^0.6.5"
```

## Changelog

We try to log all changes big and small in both [THE CHANGELOG](https://github.com/lando/run-leia-action/blob/main/CHANGELOG.md) and the [release notes](https://github.com/lando/run-leia-action/releases).

## Releasing

Create a release and publish to [GitHub Actions Marketplace](https://docs.github.com/en/enterprise-cloud@latest/actions/creating-actions/publishing-actions-in-github-marketplace). Note that the release tag must be a [semantic version](https://semver.org/).

## Maintainers

* [@pirog](https://github.com/pirog)
* [@reynoldsalec](https://github.com/reynoldsalec)

## Contributors

<a href="https://github.com/lando/run-leia-action/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=lando/run-leia-action" />
</a>

Made with [contrib.rocks](https://contrib.rocks).

## Other Resources

* [Important advice](https://www.youtube.com/watch?v=WA4iX5D9Z64)
