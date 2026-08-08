---
date: 2026-05-30
description: Aspose.Page を使用して Java で XPS ドキュメントを作成し、ステップバイステップのガイドでタイル画像を簡単に追加する方法を学びます。XPS
  ファイルを迅速に作成する方法。
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: Java XPSでタイル画像を追加
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: Javaでタイル画像を使用したXPSドキュメントの作成方法
url: /ja/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# タイル画像を使用したXPSドキュメントの作成方法（Java）

## はじめに
プログラムでXPSドキュメントを作成することは、印刷可能でデバイスに依存しない出力が必要なJava開発者にとって重要なスキルです。**XPSファイルの作成方法**を効率的に提供するのがAspose.Page for Javaで、低レベルのXML Paper Specificationの詳細を抽象化し、ビジュアルデザインに集中できるようにします。このガイドでは、XPSドキュメントの作成方法、背景やパターンとしてタイル画像を追加する方法、そして結果を保存する方法を、簡潔で本番環境向けのコードを使って具体的に示します。

## クイック回答
- **Aspose.Pageは何をするものですか？** JavaでXPSドキュメントを生成・操作するための高レベルAPIを提供します。  
- **画像をタイル状に配置できますか？** はい – `XpsImageBrush` と `XpsTileMode.Tile` を使用します。  
- **ライセンスは必要ですか？** 本番環境で使用するには、一時的または商用ライセンスが必要です。  
- **サポートされているJavaバージョンは？** JDK 8以降であればすべて対応しています。  
- **実装にどれくらい時間がかかりますか？** 基本的なタイル画像シナリオでおおよそ10〜15分です。

## 「XPSドキュメントを作成する」とは何か
`XpsDocument` は、Aspose.Page の最上位オブジェクトで、メモリ内の単一のXPSファイルを表します。ページ、リソース、メタデータをカプセル化し、プログラムでドキュメントを構築できるようにします。XPSドキュメントを作成するとは、このクラスのインスタンスを生成し、ビジュアル要素を追加し、最後に `save` を呼び出して固定レイアウトのファイルをディスクに書き込むことを意味します。このアプローチにより手動でのXML処理が不要になり、XML Paper Specification への準拠が保証されます。

## なぜタイル画像を追加するのか
タイル処理は、グラフィックを定義された領域全体に繰り返し配置することで、背景や透かし、パターン塗りに最適です。`XpsTileMode.Tile` を使用すると、画像が自動的に繰り返され、手動での複製が不要になるため開発時間を短縮し、どのデバイスでも一貫した描画が保証されます。また、同じビットマップリソースを再利用するため、タイル画像はファイルサイズを低く抑えることができます。

## 前提条件
Before diving in, make sure you have:

1. **Java Development Kit (JDK)** – JDK 8 以上がインストールされていること。  
2. **Aspose.Page for Java** – [website](https://releases.aspose.com/page/java/) からダウンロードしてください。  
3. **書き込み可能なディレクトリ** – 生成されたXPSファイルを保存する場所。

## パッケージのインポート
In your Java project, import the necessary classes:

`XpsDocument` はXPSファイルを表す主要オブジェクトです。  
`XpsImageBrush` は画像ソースを使用してシェイプを塗りつぶします。  
`XpsTileMode` は画像のタイル方法を指定します。  
`Rectangle2D` は配置用の矩形領域を表します。

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## ステップバイステップガイド

### 手順 1: プロジェクトの設定
Aspose.Page の JAR ファイルをプロジェクトのクラスパスに追加し、インポート文がエラーなくコンパイルできることを確認してください。

### 手順 2: XPSドキュメントの作成
`XpsDocument` はページ、パス、リソースを保持するコアコンテナです。希望するページサイズでインスタンス化し、そこからグラフィカル要素の追加を開始できます。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### 手順 3: タイル画像のパスを定義
`dataDir` が指すディレクトリ内に、タイルに使用したい画像（例: `R08LN_NN.jpg`）を配置してください。その画像がブラシパターンとして使用されます。

### 手順 4: タイル画像の追加
矩形パスを作成し、`XpsImageBrush` で塗りつぶします。タイルモードを `Tile` に設定することで、画像が矩形全体に繰り返されます。タイルのサイズや位置を制御するために、ソース矩形とデスティネーション矩形を調整してください。

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### 手順 5: ドキュメントの保存
XPSファイルをディスクに保存します。出力ファイルには先ほど定義したタイル画像が含まれ、任意のXPSビューアで開くことができます。

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

同じXPSドキュメント内の他のページやシェイプに **タイル画像を追加** する必要がある場合は、これらの手順を繰り返してください。

## よくある問題と解決策
| 問題 | 解決策 |
|-------|----------|
| 画像が表示されない | ファイルパス（`dataDir + "R08LN_NN.jpg"`）が正しいか、画像にアクセス可能か確認してください。 |
| タイルパターンが伸びて見える | タイルサイズを制御するために、ソースとデスティネーションの `Rectangle2D` の値を調整してください。 |
| 不透明度が効果を示さない | タイルモードの設定 **後** にブラシの不透明度が設定されていることを確認してください。 |

## よくある質問

**Q:** Aspose.Page はすべての Java バージョンと互換性がありますか？  
**A:** Aspose.Page は Java 8 から Java 21 までサポートしています。完全な互換性マトリックスは [here](https://reference.aspose.com/page/java/) で確認できます。

**Q:** 商用プロジェクトで Aspose.Page を使用できますか？  
**A:** はい。本番環境で使用するには商用ライセンスが必要です。購入オプションは [here](https://purchase.aspose.com/buy) に掲載されています。

**Q:** 無料トライアルは利用できますか？  
**A:** 完全に機能する無料トライアルは Aspose のリリースページからダウンロードできます。 [here](https://releases.aspose.com/)

**Q:** コミュニティサポートはどこで得られますか？  
**A:** 質問やサンプル共有のために、Aspose.Page のコミュニティフォーラム [forum](https://forum.aspose.com/c/page/39) に参加してください。

**Q:** 評価用の一時ライセンスはどのように取得できますか？  
**A:** 一時ライセンスは Aspose ポータルからリクエストに応じて提供されます。 [here](https://purchase.aspose.com/temporary-license/)

## 結論
これで、Aspose.Page for Java を使用してタイル画像付きの **XPSドキュメントを作成する** 完全な本番向けワークフローが手に入りました。`XpsImageBrush` と `XpsTileMode.Tile` を活用すれば、ファイルサイズを増やすことなく豊富で繰り返し可能なグラフィックを生成できます。さまざまなタイルサイズ、透明度、形状を試して、洗練されたドキュメントレイアウトを構築してください。次のステップとして、ベクターシェイプやテキストオーバーレイを追加し、XPSファイルをさらに強化することを検討してください。

---

**最終更新日:** 2026-05-30  
**テスト環境:** Aspose.Page for Java 24.12（最新）  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Java XPS ドキュメントに画像を追加する方法 – Aspose.Page を使ったシンプルガイド](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java - XPS にページを追加するチュートリアル](/page/java/xps-page-manipulation/add-page/)
- [Aspose.Page Java を使用して Java で XPS を PDF に変換する方法](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}