# macOS Virtual Machines

It is possible to run macOS Virtual Machines the same way one can run [Linux containers](/guide/linux.md) on macOS Community Cluster. 
Simply use `osx_instance` in `.cirrus.yml` files:

```yaml
osx_instance:
  image: mojave-xcode-10.1

task:
  script: ...
```

### List of available images

* `mojave-base` - vanilla macOS with Brew and Command Line Tools pre-installed.
* `mojave-xcode-10.1` - based of `mojave-base` with Xcode and couple other packages pre-installed:
`cocoapods`, `fastlane`, `rake` and `xctool`.
* `high-sierra-base` - vanilla macOS with Brew and Command Line Tools pre-installed.
* `high-sierra-xcode-[9.4.1, 10.0]` - based of `high-sierra-base` with Xcode and couple other packages pre-installed:
`cocoapods`, `fastlane`, `rake` and `xctool`.

Please refer to [`osx-images`](https://github.com/cirruslabs/osx-images) repository on how the images were built and
don't hesitate to [create issues](https://github.com/cirruslabs/osx-images/issues) if current images are missing something.

!!! info "Underlying Technology"
    Under the hood Cirrus CI is using [Anka Cloud hosted on MacStadium](/guide/supported-computing-services.md#anka) for 
    orchestrating macOS VMs. Please refer to [documentation](/guide/supported-computing-services.md#anka) for more details.
