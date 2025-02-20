# Zen Browser

This is a flake for the Zen browser.

Just add it to your NixOS `flake.nix`:

```nix
inputs = {
  zen-browser.url = "github:cutekylie/zen-browser-flake";
  ...
}
```

## Packages

In the `configuration.nix` in the `environment.systemPackages`, or in `home.nix` add in the `home.packages`:

(Also remember to add up into everything { inputs, ... })

```nix
inputs.zen-browser.packages."${system}".default
```

```shell
$ sudo nixos-rebuild switch
$ zen
```

Or, if you have flakes:

```shell
$ sudo nixos-rebuild switch --flake /path/to/flake
```

## 1Password

Zen has to be manually added to the list of browsers that 1Password will communicate with. See [this wiki article](https://nixos.wiki/wiki/1Password) for more information. To enable 1Password integration, you need to add the line `.zen-wrapped` to the file `/etc/1password/custom_allowed_browsers`.
