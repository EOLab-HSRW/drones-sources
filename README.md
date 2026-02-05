# `eolab-drones-sources`

Helper Debian package to manage eolab-drones’ APT source lists.

## Usage

```
wget -O /tmp/eolab-drones-sources.deb \
  https://github.com/EOLab-HSRW/drones-sources/releases/latest/download/eolab-drones-sources_latest.deb
sudo apt-get install /tmp/eolab-drones-sources.deb
```

If you already have the `eolab-drones-sources` package, you can update the source list by simply:
```
sudo apt-get install --only-upgrade eolab-drones-sources
```

**For maintainers and developers**: We offer a `stable` (default) set of stable sources, but we also have an `experimental` set of sources with less-tested packages or more bleeding edge sources. You can easily change the set of source by running:

```
sudo eolab-drones-set-sources experimental
sudo apt-get update
```

## How you publish new versions (Maintainer)

1. Update [debian/changelog](debian/changelog). For details how, see [4.3. changelog - Debian Manual](https://www.debian.org/doc/manuals/maint-guide/dreq.en.html#changelog)
2. Commit and push
3. Tag and push the tag. This triggers the CI and releases a new version.
