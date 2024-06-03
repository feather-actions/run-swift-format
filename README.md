# Run Swift Format

This GitHub Action ensures that the Swift code adheres to a consistent coding style by running a script to check the Swift files using [swift-format](https://github.com/apple/swift-format).

## Usage

Include the action in the workflow (make sure that a Swift 5.6+ toolchain is on the PATH, on macOS, this should be given, but on Linux, it needs to be installed first, e.g., [setup-swift](https://github.com/fwal/setup-swift)).

Add a .swift-format file to the repository to configure the lint action. If no file is added, the default configuration will be used.

```yaml
- uses: feather-actions/run-swift-format@0.0.1
```
Full example:

```yaml
on: [push]

jobs:
  job-name:
    runs-on: macos-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v4
        with:
          fetch-depth: 1
  
      - name: Run Swift Format
        uses: feather-actions/run-swift-format@0.0.1
```

## Inputs

These are the optional inputs of the action:

```yaml
swift-format-version: string input to Swift Format tag version number, default is 510.1.0
```