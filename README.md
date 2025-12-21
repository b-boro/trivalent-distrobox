# trivalent-distrobox

[Trivalent](https://github.com/secureblue/Trivalent) only officially supports
SecureBlue, although it can be installed manually on Fedora. This is my setup to
put it in a Distrobox container. This is less secure than using SecureBlue, but
it provides an easy way to use a nice browser elsewhere.

- Based on https://github.com/ublue-os/toolboxes
- Fedora 43
- No Nvidia support until https://github.com/ublue-os/toolboxes/issues/521 is resolved

No GH action or automatic builds. This image needs to be manually updated or
rebuilt regularly.

## Usage
``` sh
podman build -f Containerfile.trivalent -t trivalent-box
distrobox create --image localhost/trivalent-box:latest --name trivalent-43
distrobox enter trivalent-43
distrobox-export --app trivalent
```

## Notes
TODO hardened_malloc, ld preload, filter list copr

Maybe the base image could be ghcr.io/secureblue/securecore-main-hardened.
Didn't work immediately when I tried it.

## KeepassXC support
See https://github.com/keepassxreboot/keepassxc/issues/12390#issuecomment-3192985383
