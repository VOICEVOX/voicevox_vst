# VOICEVOX VST

VOICEVOX エディタの VST/AU プラグイン。

## 開発

- エディタはこちらです： <https://github.com/voicevox/voicevox/tree/project-vst>
- エディタをクローンして`npm run vst:serve`すると VST 用のエディタが立ち上がります。
- Release ビルドするときはエディタを`npm run vst:build`し、`dist`内を`resources/editor`にコピーしてください。
- `cargo xtask` にビルドスクリプトがあります。

## ビルド

### VST プラグイン本体

```bash
❯ cargo xtask build --help
Usage: xtask.exe build [OPTIONS]

Options:
  -r, --release                          Releaseビルドを行うかどうか。
  -l, --log                              logs内にVST内のログを出力するかどうか。
  -d, --dev-server-url <DEV_SERVER_URL>  開発用サーバーのURL。デフォルトはhttp://localhost:5173。
  -h, --help                             Print help
  -V, --version                          Print version
```

### Windows用インストーラー

[NSIS](https://nsis.sourceforge.io/Main_Page) が必要です。

```bash
❯ cargo xtask generate-installer --help
Usage: xtask.exe generate-installer

Options:
  -h, --help     Print help
  -V, --version  Print version
```

### `rust_bridge.generated.{cpp,hpp}`

```bash
❯ cargo xtask generate-bridge --help
Usage: xtask.exe generate-bridge

Options:
  -h, --help     Print help
  -V, --version  Print version
```

### ライセンス情報

```bash
❯ cargo xtask generate-licenses --help
Usage: xtask.exe generate-licenses

Options:
  -h, --help     Print help
  -V, --version  Print version
```

## ツール

### テスト

```bash
❯ cargo test
```

### ログの確認

```bash
❯ cargo xtask watch-log
```

## 仕組み

- 全体の構成については [./docs/architecture.md](./docs/architecture.md) を参照してください。
- 起動シーケンスなどについては [./docs/sequences.md](./docs/sequences.md) を参照してください。

## ライセンス

このリポジトリは LGPL-3.0 ライセンスの下で公開されています。
