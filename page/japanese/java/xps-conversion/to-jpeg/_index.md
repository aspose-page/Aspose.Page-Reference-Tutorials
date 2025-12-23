---
date: 2025-12-23
description: JavaでXPSをJPEGに変換する方法と、Aspose.Pageを使用してXPSファイルを効率的に変換する方法を学びましょう。シームレスな統合のためのステップバイステップの手順を含む包括的なガイドです。
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: JavaでXPSをJPEGに変換する方法
url: /ja/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# JavaでXPSをJPEGに変換する方法

## はじめに
このチュートリアルでは、強力な Aspose.Page ライブラリ for Java を使用して **XPS を JPEG に変換する方法** を学びます。XPS ファイルを画像形式に変換することは、Web やデスクトップ アプリケーションで文書ページを表示、プレビュー、またはさらに処理する必要がある場合に一般的な要件です。各ステップを順に説明し、各行の重要性を解説し、実践的なヒントを提供するので、変換ロジックを自分のプロジェクトに自信を持って組み込むことができます。

## クイック回答
- **変換を処理するライブラリは何ですか？** Aspose.Page for Java  
- **特定のページを選択できますか？** はい – `JpegSaveOptions` の `setPageNumbers` を使用します  
- **どの画像品質を制御できますか？** スムージングモード、解像度、JPEG 品質設定  
- **本番環境でライセンスが必要ですか？** はい、商用ライセンスが必要です（無料トライアルが利用可能です）  
- **コードは Java 8 と互換性がありますか？** もちろんです – API は Java 8 以降で動作します  

## XPS とは何か、なぜ JPEG に変換するのか
XPS（XML Paper Specification）は、PDF に似た固定レイアウトの文書形式です。XPS を JPEG に変換すると、サムネイルやメール添付、画像ファイルのみを受け付けるシステムとの統合など、ラスタ画像が必要な場合に便利です。JPEG は視覚品質とファイルサイズのバランスが良く、Web プレビューに最適です。

## 前提条件
コードに入る前に、以下が揃っていることを確認してください：

- **Java Development Environment** – JDK 8 以降がインストールされ、設定されていること。  
- **Aspose.Page for Java** – 公式サイトの [here](https://releases.aspose.com/page/java/) から最新のライブラリをダウンロードしてください。  
- **Sample XPS Document** – JPEG 画像に変換したい XPS ファイル。  

## パッケージのインポート
必要なクラスを Java ソースファイルにインポートします：

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## ステップ 1: パスの初期化と XPS ドキュメントのロード
ソース XPS ファイルがあるディレクトリを設定し、`XpsDocument` インスタンスを作成します：

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **プロのヒント:** プラットフォームに依存しないパス処理のために `java.nio.file` の `Paths.get()` を使用してください。

## ステップ 2: JPEG 保存オプションの設定
JPEG 画像のレンダリング方法（解像度、スムージング、エクスポートするページ）を定義します：

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` は印刷に適した高解像度出力を生成します。  
- `setPageNumbers` を使用すると、必要なページだけを選択でき、時間とメモリを節約できます。  

## ステップ 3: レンダリング デバイスの作成
`ImageDevice` はレンダリングされたページをバイト配列として取得します：

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## ステップ 4: XPS ドキュメントを JPEG にレンダリング
設定したデバイスとオプションを渡して `save` メソッドを呼び出します：

```java
document.save(device, options);
```

この時点で `device` は二次元配列を保持しており、各要素は JPEG エンコードされたページを表します。

## ステップ 5: 結果を反復処理してファイルを書き出す
レンダリングされたページをループし、各バイト配列を個別の JPEG ファイルに書き出します：

```java
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //close the stream
        imageStream.close();
    }
}
```

各ファイルは `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg` という名前になり、元のドキュメントとページ番号を簡単に識別できます。

## よくある問題とトラブルシューティング
| 症状 | 考えられる原因 | 対策 |
|---------|--------------|-----|
| **空白の JPEG ファイル** | 出力ストリームが適切にフラッシュまたはクローズされていない | `imageStream.close()` が内部ループ内で呼び出されていることを確認してください（例参照）。 |
| **大きな XPS ファイルでのメモリ不足エラー** | すべてのページを一度にレンダリングすると RAM を過剰に消費します | ページを小さなバッチで処理するか、JVM ヒープ（`-Xmx`）を増やしてください。 |
| **ページが欠落** | `setPageNumbers` に目的のページが含まれていない | ページ番号配列が実際の XPS ページインデックス（1 ベース）と一致しているか確認してください。 |

## よくある質問

### Q: Aspose.Page は商用プロジェクトに適していますか？
A: はい、Aspose.Page は商用製品で、ライセンスオプションが利用可能です。詳細は [here](https://purchase.aspose.com/buy) をご確認ください。

### Q: 購入前に Aspose.Page を試すことはできますか？
A: はい、無料トライアルを [here](https://releases.aspose.com/) から取得できます。

### Q: Aspose.Page のドキュメントはどこで見つけられますか？
A: ドキュメントは [here](https://reference.aspose.com/page/java/) で入手可能です。

### Q: Aspose.Page のサポートはどのように受けられますか？
A: コミュニティベースのサポートは [Aspose.Page Forum](https://forum.aspose.com/c/page/39) をご覧ください。

### Q: テスト用に一時ライセンスは必要ですか？
A: はい、一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

## 結論
これで、Aspose.Page for Java を使用した **XPS を JPEG に変換する方法** をマスターしました。ステップバイステップのガイドに従うことで、この変換パイプラインを任意の Java アプリケーション（デスクトップツール、Web サービス、バッチ処理ユーティリティなど）に組み込むことができます。プロジェクトの要件に合わせて、さまざまな解像度、ページ選択、画像形式を自由に試してみてください。

---

**最終更新日:** 2025-12-23  
**テスト環境:** Aspose.Page 24.11 for Java（執筆時点での最新）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}