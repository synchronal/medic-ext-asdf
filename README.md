# Medic ASDF

An extension pack for using [medic](https://github.com/synchronal/medic-rs)
with asdf.

## Installation

```shell
brew tap synchronal/tap
brew install medic-ext-asdf
```

Example `Brewfile`:

```shell
tap 'synchronal/tap'

brew  'synchronal/tap/medic'
brew  'synchronal/tap/medic-ext-asdf'
```

## Usage

```toml
[doctor]

checks = [
  { check = "asdf", command = "plugin-installed", args = { plugin = "rust" } },
  { check = "asdf", command = "package-installed", args = { plugin = "rust" } },
]
```


# medic-check-asdf

Checks for whether plugins and specific plugin packages are installed
via the `asdf` runtime version manager.

## plugin installed?

Checks whether an ASDF plugin is installed.

```shell
medic-check-asdf plugin-installed --plugin rust
```

## package installed?

Checks whether a package is installed for a specific plugin. If
`--version` is not passed, the version configured with `.tool-versions`
or `asdf global` is used.

```shell
medic-check-asdf package-installed --plugin rust
medic-check-asdf package-installed --plugin rust --version nightly
```
