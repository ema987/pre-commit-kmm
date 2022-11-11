# pre-commit hooks for KMM projects
Provides hooks to format Kotlin code using [`ktlint`](https://github.com/pinterest/ktlint) and Swift code using [`SwiftFormat`](https://github.com/nicklockwood/SwiftFormat)

## Installation
`ktlint` and `SwiftFormat` should be added via Gradle and SPM so you can control their version in your codebase, avoiding someone having a different version on their machine.

1. Install [pre-commit](https://pre-commit.com) on your machine
2. Add [ktlint-gradle](https://github.com/JLLeitschuh/ktlint-gradle) to your project
3. Add [SwiftFormat](https://github.com/nicklockwood/SwiftFormat#1-create-a-buildtools-folder-and-packageswift) to your project
4. Add the following in your `.pre-commit-config.yaml`:
```yaml
repos:
  -   repo: https://github.com/ema987/pre-commit-kmm
      rev: master
      hooks:
        -  id: ktlint-format
           fail_fast: true
        -  id: swift-format
           fail_fast: true
```

Notes:
- change `rev` to another tag or specific commit if needed
- if you want all the hooks to run even if there is an error in a previos one, remove the `fail_fast` param, it defaults to `false`