# bsp-raspberrypi0-2w

Board support for the Raspberry Pi Zero 2 W

## Using this extension

`bsp-raspberrypi0-2w` is an [Avocado](https://avocadolinux.org) extension — a reusable fragment of
build- and runtime-configuration that you compose into your own Avocado project. To use it,
declare it as a package-sourced extension in your `avocado.yaml` and add it to a runtime:

```yaml
extensions:
  avocado-bsp-raspberrypi0-2w:
    source:
      type: package
      version: "*"        # or pin an exact version

runtimes:
  my-runtime:
    extensions:
      - avocado-bsp-raspberrypi0-2w
```

Then install and build:

```sh
avocado install   # fetches + installs the SDK, extensions and runtime deps from your config
avocado build     # builds the SDK compile steps, extensions and runtime images
```

`avocado install` pulls the extension from your target's package feed and merges its
config into your project; `avocado build` then produces the runtime.
