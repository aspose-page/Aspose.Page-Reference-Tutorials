---
date: 2025-12-17
description: Aspose.Page を使用して Java の PostScript に Unicode テキストを追加する方法を学びましょう – Unicode
  文字列を簡単に追加するステップバイステップガイド。
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page を使用した Java PostScript で Unicode テキストを追加する方法
url: /ja/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScriptでUnicodeテキストを追加する方法（Aspose.Page）

## はじめに
JavaベースのPostScript（またはXPS）ワークフローに **how to add Unicode** 文字を追加したい場合、ここが適切な場所です。このチュートリアルでは、Aspose.Page for Java ライブラリを使用してUnicode文字列を埋め込むために必要な正確な手順を順を追って説明します。ガイドの最後までに、アラビア語、中文、絵文字など、任意の言語固有のテキストを直接PostScript出力に挿入できるようになります。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Page for Java  
- **右から左へのスクリプトを追加できますか？** はい、コードに示すように Bidi レベルを設定してください  
- **開発用にライセンスは必要ですか？** テストには無料トライアルで十分です。商用利用には商用ライセンスが必要です  
- **どの IDE が最適ですか？** 任意の Java IDE（IntelliJ IDEA、Eclipse、NetBeans）  
- **コードはクロスプラットフォームですか？** 完全に対応しています—Windows、macOS、Linux で実行可能です

## PostScriptの文脈で「how to add Unicode」とは何ですか？
Unicode を追加するとは、基本的な ASCII 範囲を超えるコードポイントで表される文字を挿入することを意味します。Aspose.Page は低レベルのエンコーディング詳細を抽象化し、テキスト内容とその視覚的配置に集中できるようにします。

## UnicodeテキストにAspose.Pageを使用する理由
- **Full Unicode support** – 複雑なスクリプト、合字、右から左への言語を処理します。  
- **No external dependencies** – フォントファイルを手動で管理する必要はありません。API はシステムフォントと連携します。  
- **Straight‑forward API** – 数回のメソッド呼び出しだけで多言語テキストを描画できます。

## 前提条件
作業を始める前に、以下の項目を準備してください。

1. **Java Development Kit (JDK)** – 任意の最新バージョン（8 以降）。  
2. **Aspose.Page for Java** – ライブラリは [download link](https://releases.aspose.com/page/java/) からダウンロードしてインストールしてください。  
3. **IDE of your choice** – IntelliJ IDEA、Eclipse、またはお好みの Java IDE。

## パッケージのインポート
Java ソースファイルに必要な Aspose.Page クラスを追加します:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## ステップ 1: プロジェクトの設定
新しい Java プロジェクトを作成し、Aspose.Page JAR をビルドパスに追加します。生成された XPS ファイルを保存するフォルダーを作成し、後で `dataDir` として参照します。

## ステップ 2: XPS ドキュメントの初期化
コンテンツを保持する空の XPS ドキュメントをインスタンス化します:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## ステップ 3: Unicode テキストの追加
実際に Unicode 文字列を追加します。以下の例は逆順のフレーズ “AVAJ rof SPX.esopsA” を書き込みますが、任意の Unicode テキスト（例: アラビア語 “مرحبا” や中文 “你好”）に置き換えることができます。

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **Pro tip:** 右から左への言語を正しく描画するには `glyphs.setBidiLevel(1);` を設定してください。左から右へのスクリプトの場合はこの行を省略できます。

## ステップ 4: ドキュメントの保存
XPS ファイルをディスクに永続化します:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

プログラムを実行した後、生成された `AddEncodingText_out.xps` を任意の XPS ビューアで開くと、指定座標に Unicode テキストが描画されていることが確認できます。

## 一般的な問題と解決策
| 問題 | 原因 | 対策 |
|------|------|------|
| テキストが四角で表示される | フォントが見つからない、または文字をサポートしていない | 必要なグリフを含むフォント（例: “Arial Unicode MS”）を使用する |
| 右から左のテキストが左から右に表示される | Bidi レベルが設定されていない | `glyphs.setBidiLevel(1);` を呼び出す |
| ファイルが保存されない | `dataDir` パスが無効、または書き込み権限がない | ディレクトリが存在し、アプリケーションに書き込み権限があることを確認する |

## よくある質問
### Aspose.Page for Java を他のプログラミング言語と併用できますか？
Aspose.Page は主に Java 向けに設計されていますが、Aspose はさまざまなプログラミング言語向けのライブラリも提供しています。

### 無料トライアルは利用可能ですか？
はい、Aspose.Page の無料トライアルは [here](https://releases.aspose.com/) からアクセスできます。

### Aspose.Page に関するサポートやディスカッションはどこで行えますか？
サポートやディスカッションは [Aspose.Page forum](https://forum.aspose.com/c/page/39) で行えます。

### Aspose.Page の一時ライセンスはどのように取得できますか？
一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

### Aspose.Page がサポートするフォントスタイルは何ですか？
Aspose.Page は Regular、Bold、Italic、BoldItalic といったフォントスタイルをサポートしています。

## 結論
これで **how to add Unicode** テキストを Aspose.Page を使用して Java の PostScript（XPS）ドキュメントに追加する方法を習得しました。この機能により、多言語レポート、国際化請求書、ASCII 以外の文字が必要なあらゆるシナリオが実現可能になります。テキストの回転、クリッピングパス、カスタムフォントの埋め込みなど、追加機能もぜひ試してみてください。詳細は公式 [documentation](https://reference.aspose.com/page/java/) をご参照ください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2025-12-17  
**テスト環境:** Aspose.Page for Java 23.12 (執筆時点での最新)  
**作者:** Aspose