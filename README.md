# Smart Contract Programming on Cardano
Notes and Snippets from Plutus Pioneer Program, Cohort 3.

# MacOS Setup for Plutus Pioneer Program
Since there is a plethora of (at times outdated) installation guides out there, here is what worked for me running:
- macOS Monterey, v12.0.1
- processor: 2.3 GHz Quad-Core Intel Core i7
- memory: 16 GB 3733 MHz LPDDR4X

I mostly followed the MacOS resource from [https://docs.plutus-community.com](https://docs.plutus-community.com/docs/setup/MacOS.html) with a few little tweaks.

## Setup
1 - Install Nix
```console
sh <(curl -L https://nixos.org/nix/install) --darwin-use-unencrypted-nix-store-volume
```

2 - Restart terminal (or reload bash profile)

3 - Edit the /etc/nix/nix.conf file
```console
vim /etc/nix/nix.confvolume
```

4 - Add the following lines to *nix.confvolume*:
```console
substituters        = https://hydra.iohk.io https://iohk.cachix.org https://cache.nixos.org/
trusted-public-keys = hydra.iohk.io:f/Ea+s+dFdN+3Y/G+FDgSq+a5NEWhJGzdjvKNGv0/EQ= iohk.cachix.org-1:DpRUyj7h7V830dp/i6Nti+NEO2/nhblbov/8MW7Rqoo= cache.nixos.org-1:6NCHdD59X431o0gWypbMrAURkbJ16ZPMQFGspcDShjY=volume
```

5 - Restart computer

6 - Clone the plutus git repo 
```console
git clone https://github.com/input-output-hk/plutus.git
```

6 - Navigate to plutus directory
```console
cd plutus/
```

7 - Build the Plutus Core
```console
nix build -f default.nix plutus.haskell.packages.plutus-core.components.library
```

8 - Fire up nix-shell
```console
nix-shell
```

# Author
- [Tilman Dingler](https://github.com/Til-D/)


Release under The MIT License (MIT), copyright: Tilman Dingler, 2021
