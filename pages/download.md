# Download

Koji {{version}} is a preview release. Download the package of your platform from the [release on GitHub]({{release}}), unpack it and put its directory on your `PATH`.

| Platform | Package |
| --- | --- |
| Linux, x86-64 | [koji-{{version}}-linux-x64.tar.gz](https://github.com/koji-language/koji/releases/download/v{{version}}/koji-{{version}}-linux-x64.tar.gz) |
| Linux, arm64 | [koji-{{version}}-linux-arm64.tar.gz](https://github.com/koji-language/koji/releases/download/v{{version}}/koji-{{version}}-linux-arm64.tar.gz) |
| macOS, Apple silicon | [koji-{{version}}-macos-arm64.tar.gz](https://github.com/koji-language/koji/releases/download/v{{version}}/koji-{{version}}-macos-arm64.tar.gz) |
| macOS, Intel | [koji-{{version}}-macos-x64.tar.gz](https://github.com/koji-language/koji/releases/download/v{{version}}/koji-{{version}}-macos-x64.tar.gz) |
| Windows, x86-64 | [koji-{{version}}-windows-x64.zip](https://github.com/koji-language/koji/releases/download/v{{version}}/koji-{{version}}-windows-x64.zip) |

[SHA256SUMS](https://github.com/koji-language/koji/releases/download/v{{version}}/SHA256SUMS) has the checksums of the packages.

## Linux and macOS

```sh
tar -xzf koji-{{version}}-linux-x64.tar.gz
export PATH=$PWD/koji-{{version}}-linux-x64:$PATH
kojic version
```

On macOS, a downloaded `kojic` is quarantined: `xattr -d com.apple.quarantine koji-{{version}}-macos-arm64/kojic` lets it run.

## Windows

Unpack `koji-{{version}}-windows-x64.zip`, add its directory to your `PATH`, and run `kojic version` in a new terminal.

## Your editor

For Visual Studio Code, install the extension **Koji** from the
[Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=koji-language.koji),
or, for VSCodium, Cursor and other editors, from
[Open VSX](https://open-vsx.org/extension/koji-language/koji): it colors the code and shows the
errors, types and declarations of the language server of Koji (`kojic lsp`), which any editor that
speaks the Language Server Protocol can use too.

## From the source

Koji builds from its repository with nothing but `gzip` (PowerShell on Windows): the compiler builds itself from a seed of its own executables.

```sh
git clone https://github.com/koji-language/koji
cd koji
bootstrap/build.sh           # bootstrap\build.cmd on Windows
build/kojic run examples/hello.kj
```

Then [Getting Started](docs/getting-started.html) walks through your first program and every command.
