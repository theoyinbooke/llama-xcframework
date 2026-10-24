# llama.cpp xcframework

Unmodified builds of [llama.cpp](https://github.com/ggml-org/llama.cpp) packaged as an
xcframework with **iOS, iOS Simulator and macOS** slices, for Swift packages that use it as a
binary target.

The official llama.cpp releases ship an xcframework with iOS (device) and macOS slices only, so
an app linking it can't build for the iOS Simulator. Each release here is the same llama.cpp tag
built with llama.cpp's own `build-xcframework.sh`, adding the Simulator slice. Nothing in
llama.cpp is changed.

## Use

```swift
.binaryTarget(
    name: "llama",
    url: "https://github.com/theoyinbooke/llama-xcframework/releases/download/b11552/llama-b11552-xcframework.zip",
    checksum: "9e969e402a5f11d8174861e40dcaf3b7760abb1aaed4c2d654bfc55de4d81522"
)
```

## Releases

| Release | llama.cpp commit | Slices | SwiftPM checksum |
|---|---|---|---|
| b11552 | `23b0202a189c44a54625aadcb37a946dd1d6278d` | ios-arm64, ios-arm64_x86_64-simulator, macos-arm64_x86_64 | `9e969e402a5f11d8174861e40dcaf3b7760abb1aaed4c2d654bfc55de4d81522` |

Each release's notes give the exact build command and toolchain. To rebuild one yourself:

```sh
git clone --depth 1 --branch b11552 https://github.com/ggml-org/llama.cpp.git
cd llama.cpp
./build-xcframework.sh ios-sim ios-device macos
```

## Licence

llama.cpp is MIT-licensed; its licence is in [LICENSE](LICENSE) and inside each xcframework.
