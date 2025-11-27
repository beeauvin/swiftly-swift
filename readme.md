# Swiftly Swift - Github Action

A Github Action to install [Swiftly](https://www.swift.org/swiftly/documentation/swiftlydocs/) and a swift 
toolchain. Works with MacOS and Linux runners.

```yaml
  - uses: beeauvin/swiftly-swift@v2
    with:
      swift-version: 6.2
      # Optionally, disable caching swiftly
      # swiftly-cache: 'false'
```

`swift-version` is the Swift Toolchain version that Swiftly will install and defaults to `latest`. Any
version string supported by Swiftly (including snapshots) should work.

### Caching

By default `swiftly-swift` will cache both swiftly itself and the swift toolchain it resolves. Because there
is not a reliable way to track and download spwcific swiftly versions we default to caching whatever is
pulled and using `self-update` on each run to try and keep it at latest. If caching breaks or some other
tragedy occurs you can delete your action cache or disable caching by setting `swiftly-cache` to `false`.

### Windows

Unfortunately [Swiftly doesn't currently support windows](https://github.com/swiftlang/swiftly/issues/151) so
this action doesn't either. Open to contributions to get it working with currently available install methods
until Swiftly has support for it.

## License

Swiftly Swift is available under the [Mozilla Public License 2.0](https://mozilla.org/MPL/2.0/).

A copy of the MPLv2 is included [license.md](/license.md) file for convenience.
