# hdx

[简体中文]

> Access Huawei/HarmonyOS Developer [Download Center] from CLI

CLI tool for accessing Huawei HarmonyOS Developer Community Download Center.

## Getting Started

Download the latest version of the binary from the [GitHub releases][releases] page, extract and place the executable in your PATH. Run `hdx` to see the help information.

```plaintext
$ hdx
CLI tool for accessing Huawei/HarmonyOS Developer Download Center.

If you find any bug or have a feature request, please open an issue on
GitHub: https://github.com/chawyehsu/hdx/issues

Usage: hdx [OPTIONS] <COMMAND>

Commands:
  auth         Authenticate with Huawei ID
  completions  Generate shell completions
  config       Manage configurations of this tool
  dget         Get the download URL of specified tool
  help         Print this message or the help of the given subcommand(s)

Options:
  -v, --verbose...  Increase logging verbosity
  -q, --quiet...    Decrease logging verbosity
  -h, --help        Print help
  -V, --version     Print version
```

### Usage

#### auth

First, use the `auth login` command to log in with your Huawei ID. After a successful login, the authentication information will be saved in the local authentication file `~/.config/hdx/credentials.json`. Please keep it safe.

```plaintext
hdx auth login
```

Currently, only the combination of **username + password + dynamic verification code** using a [Huawei ID] is supported for login. Logging in with a phone number/email + password is not currently supported.

#### dget

After a successful login, you can use the `dget` command to get the download link for the specified tool.

```plaintext
hdx dget <tool>
```

Currently, it supports obtaining download links for [`deveco-studio`] and [`command-line-tools-for-hmos`]. You may be required to sign a user agreement during the process. Once you have signed the agreement and obtained the download link, you can use a browser or download tool to download it.

If the authentication information expires, you can use the `auth refresh` command to refresh the authentication information.

#### config

Use the `config` command to view and modify the settings of this tool. The configuration file is saved in `~/.config/hdx/config.json`.

```plaintext
hdx config
```

Currently, only setting a proxy server for the tool using `proxy` is supported.

[简体中文]: README.zh-Hans.md
[Download Center]: https://developer.huawei.com/consumer/cn/download/
[releases]: https://github.com/chawyehsu/hdx/releases/latest
[`deveco-studio`]: https://developer.huawei.com/consumer/cn/download/deveco-studio
[`command-line-tools-for-hmos`]: https://developer.huawei.com/consumer/cn/download/command-line-tools-for-hmos
[Huawei ID]: https://id.huawei.com
