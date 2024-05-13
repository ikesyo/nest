# 🪺 nest

nest is a package manager to install executable binary which is made with Swift.

```
$ nest install realm/SwiftLint 
📦 Found an artifact bundle, SwiftLintBinary-macos.artifactbundle.zip, for SwiftLint.
🌐 Downloading the artifact bundle of SwiftLint...
✅ Success to download the artifact bundle of SwiftLint.
🪺 Success to install swiftlint.

$ nest install XcodesOrg/xcodes
🪹 No artifact bundles in the repository.
🔄 Cloning xcodes...
🔨 Building xcodes for 1.4.1...
🪺 Success to install xcodes.
```

## Concept
nest is highly inspired by [mint](https://github.com/yonaskolb/Mint) and [scipio](https://github.com/giginet/Scipio).

mint is a tool to install and run executable Swift packages. 
The tool is so amazing, but the tool requires to build packages at first.
The build time cannot be ignored on Cl environment where cache are not available like Xcode Cloud.

scipio is a tool to generate and reuse xcframeworks,
The tool drastically reduced the pre-build frameworks.

nest, it takes over the concept of these tools, reuses an artifact bundle to reduce the build time.
If there is an artifact bundle in GitHub release, nest downloads the artifact bundles and installs the executable binaries in the bundles.
If not, nest clones and build the package and installs the executable binaries.

## Why nest
A nest is place where Swift birds store their crafts.

## How to Use

### Install packages
```
$ nest install realm/SwiftLint 
$ nest install realm/SwiftLint 0.55.0 # A version can be specified.
$ nest install https://github.com/realm/SwiftLint 0.55.0
```

### Uninstall package
```
$ nest uninstall swiftlint # All versions of swiftlint are uninstalled.
$ nest uninstall swiftlint 0.55.0 # A verision can be specified.
```

### Show all binaries
```
$ nest list
```