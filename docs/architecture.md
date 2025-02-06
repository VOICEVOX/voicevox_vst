# 全体構成

VOICEVOX VST は以下のコンポーネントから構成されています：

- C++ 部分（voicevox.vst3）
- Rust 部分（vvvst_impl.dll）
- エディタ

## C++ 部分

[DPF](https://github.com/DISTRHO/DPF) で作成された VST3 プラグインです。
Rust 部分のラッパーとして機能し、主に Rust 部分との通信を行います。
ここで複雑な処理は基本的には行わず、Rust 部分に処理を委譲します。

Rust 部分の呼び出しは `rust_bridge.cpp` で行われています。

## Rust 部分

Rust で書かれた cdylib です。
基本的に処理はこちらで行います。

## エディタ

VST/AU のために改造されたエディタです。
エディタはこちらのリポジトリで開発されています：[voicevox/voicevox:project-vst](https://github.com/voicevox/voicevox/tree/project-vst)
