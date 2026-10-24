# ICE Package Index

This repository is the default package index used by ICE's
**Project -> Manage Packages** dialog.

Each indexed package is a Git submodule. ICE discovers package manifests in the
submodule working trees, so a package directory must contain:

- `package.toml` with the package name, version, and capabilities
- `.github/logo.png`, used as the package logo in the package manager

## Indexed packages

| Package | Repository | Branch |
| --- | --- | --- |
| `gf180mcu` | https://github.com/ldapx/ice-pkg-gf180mcu | `dev` |
| `ihp.sg13g2` | https://github.com/ldapx/ice-pkg-ihp | `dev` |
| `sky130` | https://github.com/ldapx/ice-pkg-sky130 | `dev` |

## Adding a package

From the index repository root:

```sh
git submodule add -b <branch> <package-repository-url> <package-name>
git add .gitmodules <package-name>
git commit -m "Add <package-name> to the package index"
git push
```

The submodule path is normally the package name, but ICE also discovers package
manifests in nested submodule paths.

Users can refresh the index from **Manage Packages** after it has been updated.
