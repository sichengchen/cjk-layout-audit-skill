# CJK テキストレイアウト監査 Agent Skill

[English](README.md) | [繁體中文](README.zh-Hant.md) | [简体中文](README.zh-Hans.md) | [한국어](README.ko.md)

`cjk-layout-audit` は、中国語・日本語・韓国語のテキストレイアウトを監査する agent skill です。対象は、Web ページ、frontend app、電子書籍、PDF、スクリーンショット、ソースからレンダリングされるコンテンツです。

可視 CJK テキストの可読性、折り返し、スペーシング、W3C 文字組版要件との整合性を確認します。

## 対応標準

- [JLReq：日本語組版処理の要件](https://www.w3.org/TR/jlreq/)
- [CLReq：中文排版需求](https://www.w3.org/TR/clreq/)
- [KLReq：한국어 텍스트 레이아웃 및 타이포그래피를 위한 요구사항](https://www.w3.org/TR/klreq/)

## 監査項目

- 言語指定と locale metadata
- 横組み、縦組み、書字方向の混在
- 改行、行頭禁則、行末禁則処理
- 約物の間隔、ぶら下げ、連続する約物の処理
- ルビ、ふりがな／注釈、強調表記、行内注
- CJK とラテン文字の混在、数字、日付、記号
- 段落間隔、行揃え、孤立行、孤立字、見出し、改ページ
- 電子書籍および PDF のページ構成、柱、図版、表、注

## 使用方法

この skill に対応した agent runtime で、次の prompt を入力します。

```text
$cjk-layout-audit を使って、この CJK Web ページまたは電子書籍を W3C の文字組版要件に照らして監査してください。
```

監査範囲が大きい場合は、対象 URL、ローカルファイル、スクリーンショット、電子書籍または PDF、想定言語、確認対象のデバイスまたはページサイズを指定します。

監査結果として、具体的な指摘、対象箇所、証拠、W3C 要件との対応、影響、修正方法を返します。

## Codex Plugin

作者の Codex Marketplace を追加します。

```bash
codex plugin marketplace add sichengchen/codex-plugins
```

続いて、`cjk-text-layout` プラグインをインストールします。

---

この README は英語で作成され、LLM によって日本語に翻訳されたものです。
