# nix-freeze-files
Convert a tree of files into an tree of fixed-output paths.

# Output Example
`nix-freeze-files .`
```
{
  "B" = {
    "A" = {
      "A.hs" = builtins.path {
        path = /root/sandbox/nix_sandbox/B/A/A.hs;
        sha256 = "0ip26j2h11n1kgkz36rl4akv694yz65hr72q4kv4b3lxcbi65b3p";
        };
      };
    "B.hs" = builtins.path {
      path = /root/sandbox/nix_sandbox/B/B.hs;
      sha256 = "0ip26j2h11n1kgkz36rl4akv694yz65hr72q4kv4b3lxcbi65b3p";
      };
    };
  }
```
# Motive
[snack](https://github.com/nmattia/snack), the Nix-based incremental build tool for Haskell projects, needs a way to prevent redundantly analyzing import dependencies of module files in every builds. An attribute set of fixed-output file paths can help.

# Credits
This package is modified from Jack Kelly's [nix-freeze-tree](https://sr.ht/~jack/nix-freeze-tree/).


