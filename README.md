# nixos-configs

Personal NixOS configuration, Home Manager setup, and workstation dotfiles for a reproducible Linux environment.

This repository is my source of truth for building, maintaining, and improving my NixOS workstation setup. The goal is to make my environment easier to rebuild, easier to understand, and easier to improve over time.

## Purpose

The purpose of this repo is to document and version-control my NixOS configuration so I can:

* Rebuild my workstation more easily
* Track changes to my system over time
* Share my NixOS setup with others
* Preserve useful configuration patterns
* Improve my Linux, Neovim, and infrastructure workflow
* Create a repeatable technical environment for security, cloud, and engineering work

This repo is intentionally simple at first. It is meant to grow as my NixOS skills improve.

## Current Focus

This configuration is focused on a practical workstation setup for:

* NixOS system configuration
* Home Manager user configuration
* Neovim setup
* Terminal and shell productivity
* Git and development tools
* AWS and infrastructure tooling
* Security and cybersecurity workflows
* Personal learning and experimentation

## Repository Structure

```text
.
├── README.md
├── flake.nix
├── hosts/
│   └── default/
│       ├── configuration.nix
│       └── hardware-configuration.example.nix
├── home/
│   └── rod.nix
└── modules/
    ├── system.nix
    ├── packages.nix
    └── neovim.nix
```

## Directory Overview

### `hosts/`

Machine-specific NixOS configurations.

Each host should eventually have its own folder. For now, this repo starts with a simple `default` host.

### `home/`

Home Manager configuration for user-level settings, packages, shell aliases, Git settings, and personal tools.

### `modules/`

Reusable NixOS modules that can be shared across hosts.

Examples include:

* System settings
* Common packages
* Neovim configuration
* Development tools
* Security tools
* Shell configuration

## Important Security Note

This is intended to be a public or shareable configuration repository.

Do not commit secrets or sensitive files.

Before pushing changes, carefully check for:

* SSH private keys
* AWS credentials
* GitHub tokens
* API keys
* Passwords
* VPN configurations
* Client-specific information
* Internal hostnames or IP addresses
* Private environment variables
* Sensitive machine-specific configuration

The real `hardware-configuration.nix` file may contain machine-specific details. Use an example file in the repo and keep the actual local version private if needed.

## Basic Usage

Clone the repo:

```bash
git clone https://github.com/YOUR-GITHUB-USERNAME/nixos-configs.git
cd nixos-configs
```

Check the flake:

```bash
nix flake check
```

Rebuild the system:

```bash
sudo nixos-rebuild switch --flake .#default
```

Update flake inputs:

```bash
nix flake update
```

Rebuild after updating:

```bash
sudo nixos-rebuild switch --flake .#default
```

## Common Commands

Edit the main system configuration:

```bash
nvim hosts/default/configuration.nix
```

Edit the Home Manager configuration:

```bash
nvim home/rod.nix
```

Edit shared packages:

```bash
nvim modules/packages.nix
```

Edit Neovim module:

```bash
nvim modules/neovim.nix
```

Check Git status:

```bash
git status
```

Commit changes:

```bash
git add .
git commit -m "Update NixOS configuration"
```

Push changes:

```bash
git push
```

## Initial Goals

The first version of this repo is meant to capture:

* A working NixOS flake
* A basic host configuration
* A clean Home Manager setup
* A repeatable package list
* Neovim as the default editor
* Git configuration
* Useful shell aliases
* Infrastructure tools such as AWS CLI and Terraform

## Future Improvements

Planned improvements include:

* Separate host profiles for different machines
* Better Home Manager organization
* More complete Neovim configuration
* Terminal transparency and appearance settings
* Shell customization
* Terraform and cloud tooling
* Security lab tooling
* Documentation for rebuilding a machine from scratch
* Optional private secrets management
* Better module separation

## Personal Notes

This repo is part of my ongoing effort to build a more intentional technical operating system around myself.

The goal is not to create a perfect NixOS setup immediately.

The goal is to create a visible, version-controlled learning map that improves over time.

Small improvements compound.

## License

This project is licensed under the MIT License.

