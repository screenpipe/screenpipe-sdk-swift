> ⚠️ **Generated mirror — do not edit `Sources/`, `Tests/`, or `Package.swift` here.**
> They are rsynced from [`screenpipe/screenpipe` → `ee/sdk/`](https://github.com/screenpipe/screenpipe/tree/main/ee/sdk) on every SDK release (`swift-mirror` job in `sdk-release.yml`) and any local change is overwritten. Develop the Swift SDK in the monorepo; this repo only exists so Swift Package Manager can consume the package from a repo root.

// screenpipe — AI that knows everything you've seen, said, or heard
// https://screenpi.pe

# Screenpipe Swift SDK

Swift Package Manager distribution of the Screenpipe SDK — a screen-recording
client for macOS apps, powered by Screenpipe's native capture stack.

This repository mirrors `ee/sdk` from
[screenpipe/screenpipe](https://github.com/screenpipe/screenpipe) so that
SwiftPM can consume `Package.swift` from a repo root. Source of truth for the
SDK lives in the monorepo.

## Install

```swift
// Package.swift
dependencies: [
  .package(url: "https://github.com/screenpipe/screenpipe-sdk-swift.git", from: "0.1.0"),
],
targets: [
  .executableTarget(
    name: "YourApp",
    dependencies: [
      .product(name: "Screenpipe", package: "Screenpipe"),
    ]
  ),
]
```

## Runtime requirements

The Swift SDK speaks JSON-lines to a bundled Node bridge. At runtime the host
process must be able to spawn `node` and the bridge resolves
[`@screenpipe/sdk`](https://www.npmjs.com/package/@screenpipe/sdk) from the
configured `sdkRoot`. See [the Swift example app](examples/swift-app) for a
working setup.

## License

Source-available under the Screenpipe Enterprise License — see
[LICENSE.md](LICENSE.md). Production use requires a valid Screenpipe Enterprise
subscription. Contact [louis@screenpi.pe](mailto:louis@screenpi.pe).

## Issues

File issues against the upstream monorepo:
[screenpipe/screenpipe/issues](https://github.com/screenpipe/screenpipe/issues).