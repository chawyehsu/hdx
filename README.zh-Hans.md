# hdx

[English]

> Access Huawei/HarmonyOS Developer [Download Center] from CLI

命令行工具用于访问华为鸿蒙开发者社区下载中心。

## Getting Started

从 [GitHub releases][releases] 页面下载最新版本的二进制文件，解压后将可执行文件放到 PATH 中，运行 `hdx` 查看帮助信息。

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

首先使用 `auth login` 命令进行华为账号的登录，登录成功后认证信息会保存在本地的认证文件 `~/.config/hdx/credentials.json` 中，妥善保管。

```plaintext
hdx auth login
```

目前仅支持使用[华为账号]的**账号名+密码+动态验证码**的组合方式进行登录。暂不支持手机号/邮箱+密码的登录方式。

#### dget

登录成功后，可以使用 `dget` 命令获取指定工具的下载链接。

```plaintext
hdx dget <tool>
```

目前支持获取 [`deveco-studio`] 和 [`command-line-tools-for-hmos`] 两个工具的下载链接。获取链接期间可能会要求签署用户协议。拿到带签名的下载链接后，可以自行使用浏览器或者下载工具进行下载。

如遇认证信息失效，可以使用 `auth refresh` 命令刷新认证信息。

#### config

使用 `config` 命令可以查看和修改本工具的设置。配置文件保存在 `~/.config/hdx/config.json` 中。

```plaintext
hdx config
```

目前仅支持为工具设置代理服务器 `proxy`。

[English]: README.md
[Download Center]: https://developer.huawei.com/consumer/cn/download/
[releases]: https://github.com/chawyehsu/hdx/releases/latest
[`deveco-studio`]: https://developer.huawei.com/consumer/cn/download/deveco-studio
[`command-line-tools-for-hmos`]: https://developer.huawei.com/consumer/cn/download/command-line-tools-for-hmos
[华为账号]: https://id.huawei.com
