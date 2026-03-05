---
date: 2025-12-28
description: Aspose.Page を使用して Java で XPS ドキュメントを作成し、タイル状画像を簡単に追加する方法をステップバイステップで学びましょう。
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: Javaでタイル画像を使用したXPSドキュメントの作成方法
url: /ja/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# JavaでXPSドキュメントを作成し、タイル画像を追加する

## はじめに
モダンな Java 開発において、**XPS ドキュメント** をプログラムで作成できることは貴重なスキルです。特に、タイル画像のようなグラフィックでドキュメントを豊かにしたいときに役立ちます。Aspose.Page for Java を使用すれば、このプロセスはシンプルになり、低レベルのファイル操作に煩わされることなくビジュアルデザインに集中できます。本チュートリアルでは、XPS ドキュメントの作成方法、**タイル画像の追加**、そして結果の保存方法を、明確なステップバイステップのコード例とともに学びます。

## Quick Answers
- **Aspose.Page は何をしますか？** JavaでXPSドキュメントを生成・操作するための高レベルAPIを提供します。  
- **画像をタイル状に配置できますか？** はい – `XpsImageBrush` と `XpsTileMode.Tile` を使用します。  
- **ライセンスは必要ですか？** 本番環境で使用するには一時ライセンスまたは商用ライセンスが必要です。  
- **サポートされているJavaバージョンは？** JDK 8以降であればすべて対応しています。  
- **実装にどれくらい時間がかかりますか？** 基本的なタイル画像シナリオでおおよそ10〜15分です。

## 「XPSドキュメントの作成」とは？
XPS（XML Paper Specification）ファイルは、PDF に似た固定レイアウトのドキュメント形式です。プログラムで XPS ドキュメントを作成すると、Java コードから直接印刷可能でデバイスに依存しないファイルを生成できます。

## なぜタイル画像を追加するのか？
画像をタイル状に配置すると、指定した領域全体にグラフィックが繰り返し描画されます。背景、透かし、パターン塗りなどに最適です。Aspose.Page の `XpsTileMode.Tile` を使用すれば、数行のコードで実現できます。

## 前提条件
開始する前に以下を用意してください。

1. **Java Development Kit (JDK)** – JDK 8以降がインストールされていること。  
2. **Aspose.Page for Java** – [ウェブサイト](https://releases.aspose.com/page/java/)からダウンロードしてください。  
3. **書き込み可能なディレクトリ** – 生成された XPS ファイルを保存する場所。

## パッケージのインポート
Java プロジェクトで必要なクラスをインポートします。

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## 手順ガイド

### 手順 1: プロジェクトのセットアップ
Aspose.Page の JAR ファイルをプロジェクトのクラスパスに追加し、インポート文がエラーなくコンパイルできることを確認します。

### 手順 2: XPSドキュメントの作成
新しい `XpsDocument` オブジェクトをインスタンス化します。これがページ、パス、リソースを保持するコアコンテナになります。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### 手順 3: タイル画像のパスを定義する
タイルに使用したい画像（例: `R08LN_NN.jpg`）を `dataDir` が指すディレクトリに配置します。画像はブラシパターンとして使用されます。

### 手順 4: タイル画像を追加する
矩形パスを作成し、`XpsImageBrush` で塗りつぶします。タイルモードを `Tile` に設定することで、画像が矩形全体に繰り返し描画されます。

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### 手順 5: ドキュメントを保存する
XPS ファイルをディスクに永続化します。出力ファイルには先ほど定義したタイル画像が含まれます。

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

同様の手順で、同一 XPS ドキュメント内の他のページやシェイプにも **タイル画像を追加** できます。

## よくある問題と解決策
| 問題 | 解決策 |
|------|--------|
| 画像が表示されない | ファイルパス (`dataDir + "R08LN_NN.jpg"`) が正しく、画像にアクセスできることを確認してください。 |
| タイルパターンが伸びて表示される | タイルサイズを制御するために、ソースおよびデスティネーションの `Rectangle2D` 値を調整してください。 |
| 不透明度が効果を示さない | タイルモード設定 **後** にブラシの不透明度が設定されていることを確認してください。 |

## よくある質問

### Aspose.PageはすべてのJavaバージョンと互換性がありますか？
Aspose.PageはさまざまなJavaバージョンで動作するよう設計されています。互換性は、ドキュメント[こちら](https://reference.aspose.com/page/java/)で確認してください。

### 商用プロジェクトでAspose.Pageを使用できますか？
はい、Aspose.Pageは商用ライセンスを提供しています。購入は[こちら](https://purchase.aspose.com/buy)から行えます。

### 無料トライアルは利用できますか？
はい、無料トライアルでAspose.Pageの機能を体験できます。[こちら](https://releases.aspose.com/)からお試しください。

### コミュニティサポートやディスカッションはどこで見つけられますか？
Aspose.Pageコミュニティは[フォーラム](https://forum.aspose.com/c/page/39)で交流できます。

### Aspose.Pageの一時ライセンスはどう取得できますか？
一時ライセンスは[こちら](https://purchase.aspose.com/temporary-license/)から取得できます。

---

**最終更新日:** 2025-12-28  
**テスト環境:** Aspose.Page for Java 24.12 (latest)  
**作者:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
