---
slug: /releasing/
sidebar_position: 11
---

# Релизы

The release process of Task is done with the help of [GoReleaser][goreleaser]. You can test the release process locally by calling the `test-release` task of the Taskfile.

[GitHub Actions](https://github.com/go-task/task/actions) should release artifacts automatically when a new Git tag is pushed to `main` branch (raw executables and DEB and RPM packages).

Since v3.15.0, raw executables can also be reproduced and verified locally by checking out a specific tag and calling `goreleaser build`, using the Go version defined in the above GitHub Actions.

# Homebrew

Goreleaser will automatically push a new commit to the [Formula/go-task.rb][gotaskrb] file in the [Homebrew tap][homebrewtap] repository to release the new version.

# npm

To release to npm update the version in the [`package.json`][packagejson] file and then run `task npm:publish` to push it.

# Snapcraft

The [snap package][snappackage] requires to manual steps to release a new version:

- Updating the current version on [snapcraft.yaml][snapcraftyaml].
- Moving both `amd64`, `armhf` and `arm64` new artifacts to the stable channel on the [Snapcraft dashboard][snapcraftdashboard].

# Scoop

Scoop is a command-line package manager for the Windows operating system. Scoop package manifests are maintained by the community. Scoop owners usually take care of updating versions there by editing [this file](https://github.com/ScoopInstaller/Main/blob/master/bucket/task.json). If you think its Task version is outdated, open an issue to let us know.

# Nix

Nix - это метод установки, принадлежащий сообществу. Мейнтейнеры Nix пакетов позаботились об обновлении версий, редактируя [этот файл](https://github.com/NixOS/nixpkgs/blob/nixos-unstable/pkgs/development/tools/go-task/default.nix). Если вы считаете, что его версия Task устарела, откройте issue, чтобы уведомить нас.

<!-- prettier-ignore-start -->

<!-- prettier-ignore-end -->
[goreleaser]: https://goreleaser.com/
[homebrewtap]: https://github.com/go-task/homebrew-tap
[gotaskrb]: https://github.com/go-task/homebrew-tap/blob/master/Formula/go-task.rb
[packagejson]: https://github.com/go-task/task/blob/main/package.json#L3
[snappackage]: https://github.com/go-task/snap
[snapcraftyaml]: https://github.com/go-task/snap/blob/master/snap/snapcraft.yaml#L2
[snapcraftdashboard]: https://snapcraft.io/task/releases