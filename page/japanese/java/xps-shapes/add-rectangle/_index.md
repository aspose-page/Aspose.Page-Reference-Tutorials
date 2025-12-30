---
date: 2025-12-30
description: Aspose.Page を使用して矩形を追加し、Java で XPS ドキュメントを作成する方法を学びましょう。シームレスな XPS ドキュメント操作のためのステップバイステップガイドをご覧ください。
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: JavaでXPSドキュメントを作成 – Aspose.Pageで矩形を追加
url: /ja/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS ドキュメント Java の作成 – 四角形の追加

## はじめに
この包括的なチュートリアルでは **XPS ドキュメント Java** ファイルを作成し、Aspose.Page ライブラリを使用して四角形を追加する方法を学びます。レポート、請求書、カスタムグラフィックの作成において、四角形の作成をマスターすれば XPS レイアウトを正確にコントロールできます。各ステップを順に解説し、コードの各行の意図を説明し、色やストロークのカスタマイズ方法を示して、プロフェッショナルな結果を得られるようにします。

## クイック回答
- **推奨ライブラリは？** Aspose.Page for Java  
- **実装にかかる時間は？** 基本的な四角形で約 10 分  
- **ライセンスは必要？** 開発は無料トライアルで可能。商用利用には商用ライセンスが必要です。  
- **対応 Java バージョンは？** Java 8 以降  
- **複数の図形を追加できる？** はい – 各図形ごとに手順を繰り返します

## 前提条件
作業を始める前に以下を確認してください。

- Java プログラミング言語の基本的な知識。  
- Aspose.Page ライブラリがインストール済みであること。未インストールの場合は、[Aspose.Page Java ドキュメント](https://reference.aspose.com/page/java/) からダウンロードできます。  
- 動作する Java 開発環境（IDE、JDK、必要に応じて Maven/Gradle）。

## パッケージのインポート
まず、Java プロジェクトに必要なパッケージをインポートします。Aspose.Page ライブラリがクラスパスに正しく追加されていることを確認してください。以下は基本的な例です。

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

それでは、例を複数のステップに分解し、Java XPS に四角形を追加する方法を見ていきましょう。

## 手順 1: ドキュメントディレクトリの設定
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

`"Your Document Directory"` を、XPS ファイルを保存したいフォルダーのパスに置き換えてください。

## 手順 2: 新しい XPS ドキュメントの作成
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

この行は **新しい** XPS ドキュメントを作成します。後で図形、テキスト、画像などを追加できます。

## 手順 3: CMYK ソリッドカラーのストローク付き四角形の追加
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

このステップでは、CMYK ソリッドカラーのストローク付き四角形を追加します。ジオメトリ文字列（`"M 20,10 L 220,10 220,100 20,100 Z"`）を変更すればサイズや位置を調整でき、`createColor` のカラー値を変更すればデザインに合わせた色にできます。

## 手順 4: 生成された XPS ドキュメントの保存
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

最後に、先ほど指定したディレクトリに四角形が追加された XPS ドキュメントを保存します。

## 主な使用例
- **レポートヘッダー** – タイトルの背景ブロックとして四角形を使用。  
- **請求書テーブル** – セルやセクションをカラー枠で強調。  
- **カスタムグラフィック** – 複数の四角形を組み合わせて複雑な形状を作成。

## トラブルシューティングのヒント
- **ファイルが見つからないエラー:** `dataDir` が既存のフォルダーを指しているか、ICC プロファイル（`uswebuncoated.icc`）が存在するか確認してください。  
- **色が正しく表示されない:** 使用するカラースペース（CMYK と RGB）に合わせて ICC プロファイルが一致しているか確認してください。  
- **サイズが期待と違う:** ジオメトリ文字列を調整して正しい座標になるよう修正してください。

## 結論
おめでとうございます！Aspose.Page を使用して **XPS ドキュメント Java** ファイルを作成し、四角形を追加する方法を習得しました。この基礎があれば、よりリッチな XPS ドキュメントを構築し、グラフィックをカスタマイズし、図形を大規模なワークフローに統合できます。

## FAQ
### 1つの XPS ドキュメントに複数の四角形を追加できますか？
はい、チュートリアルで示した手順を繰り返すことで、必要なだけ四角形を追加できます。

### 四角形の色を変更するには？
`createColor` メソッドのカラー値を変更すれば、希望の色に設定できます。

### Aspose.Page は複雑な XPS ドキュメント操作に適していますか？
もちろんです。Aspose.Page はさまざまな XPS ドキュメントタスクを処理するための豊富な機能を提供します。

### 追加のサンプルやサポートはどこで見つかりますか？
より多くのサンプルは [Aspose.Page フォーラム](https://forum.aspose.com/c/page/39) で確認でき、コミュニティから支援を受けられます。

### 購入前に Aspose.Page を試すことはできますか？
はい、[無料トライアル](https://releases.aspose.com/) で Aspose.Page の機能を体験できます。

## よくある質問

**Q: この手法は Java 11 以降でも動作しますか？**  
A: はい、Aspose.Page ライブラリは Java 8 以降、Java 11、17 などでも互換性があります。

**Q: 四角形領域内に画像を埋め込めますか？**  
A: `XpsImage` 要素を追加し、同じジオメトリ座標で四角形の上または内部に配置できます。

**Q: ストロークだけでなく塗りつぶし色を設定するには？**  
A: `doc.createSolidColorBrush(...)` で作成したブラシを `path.setFill(...)` に渡します。

**Q: 四角形を回転させることは可能ですか？**  
A: `path.setTransform(...)` で変換行列を適用すれば、回転やスケーリングが可能です。

**Q: 本番環境で必要なライセンスは？**  
A: デプロイ時には商用 Aspose.Page ライセンスが必要です。無料トライアルは評価・開発用途に限定されます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2025-12-30  
**テスト環境:** Aspose.Page for Java 24.12 (latest)  
**作者:** Aspose  

---