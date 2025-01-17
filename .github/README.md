# Zen Browser

Originally from [MarceColl/zen-browser-flake](https://github.com/MarceColl/zen-browser-flake) deleted and re-made repo for discoverability as "GitHub does not like to show forks in the search".

This is a flake for the Zen browser.

Just add it to your NixOS `flake.nix` or home-manager:

```nix
inputs = {
  zen-browser.url = "github:0xc000022070/zen-browser-flake";
  ...
}
```

## Integration

To integrate `Zen Browser` to your NixOS/Home Manager configuration, add the following to your `environment.systemPackages` or `home.packages` respectively:

```nix
# For now only 'x86_64-linux' is supported
inputs.zen-browser.packages."${system}".default # beta
inputs.zen-browser.packages."${system}".beta
inputs.zen-browser.packages."${system}".twilight
```

_With the end of the year just a few days away, **only the beta version is automatically updated**._

Afterwards you can just build your configuration and start the `Zen Browser`

```shell
$ sudo nixos-rebuild switch # or home-manager switch
$ zen
```

## 1Password

Zen has to be manually added to the list of browsers that 1Password will communicate with. See [this wiki article](https://wiki.nixos.org/wiki/1Password) for more information. To enable 1Password integration, you need to add the line `.zen-wrapped` to the file `/etc/1password/custom_allowed_browsers`.
