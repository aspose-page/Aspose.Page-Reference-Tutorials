---
date: 2025-12-28
description: Aspose.Page を使用して Java で XPS ドキュメントに画像を追加する方法を学びましょう。このステップバイステップガイドでは、画像を簡単に追加し、ドキュメント処理を強化する方法を示します。
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: Java XPSドキュメントに画像を追加する方法 – Aspose.Pageによるシンプルガイド
url: /ja/java/xps-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page を使用した Java XPS ドキュメントへの画像追加方法

XPS ファイルに画像を追加することは、レポートや請求書、その他のビジュアルドキュメントを充実させる必要がある Java 開発者にとって一般的な要件です。このチュートリアルでは、強力な Aspose.Page for Java ライブラリを使用して **画像を追加する方法** を学びます。各手順を順に解説し、各行の意味を説明し、典型的な落とし穴を回避するためのヒントを提供します。

## クイックアンサー
- **必要なライブラリは？** Aspose.Page for Java
- **複数の画像を追加できますか？** はい – 画像ごとに画像追加の手順を繰り返してください
- **サポートされている画像形式は？** TIFF、JPEG、PNG、GIF（および.NETでサポートされているその他の形式）
- **ライセンスは必要ですか？** 評価には無料トライアルをご利用いただけますが、本番環境では商用ライセンスが必要です
- **標準的な実装時間は？** 基本的な画像挿入は約10～15分です

## はじめに
画像を XPS ドキュメントに追加することは、多くの Java アプリケーションで一般的な要件です。レポート生成からドキュメント処理まで、さまざまなシナリオで利用されます。Aspose.Page for Java はこの作業を簡素化し、画像を XPS ファイルにシームレスに統合するための効率的なメソッドを提供します。本チュートリアルでは、Aspose.Page for Java を使用して XPS ドキュメントに画像を追加する手順を示します。

## 前提条件
チュートリアルに入る前に、以下の前提条件が整っていることを確認してください。
1. **Aspose.Page for Java ライブラリ** – [Web サイト](https://releases.aspose.com/page/java/) から Aspose.Page for Java ライブラリをダウンロードしてインストールします。
2. **Java 開発環境** – お使いのマシンに Java 開発環境がセットアップされていることを確認します。

それでは、次の手順に進みましょう。

## パッケージのインポート
Java プロジェクトで、必要なクラスとメソッドにアクセスするために必要な Aspose.Page for Java パッケージをインポートします。

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```

## ステップ 1: ドキュメントディレクトリの設定
XPS ドキュメントと画像ファイルを保存するドキュメントディレクトリへのパスを定義します。

```java
String dataDir = "Your Document Directory";
```

## ステップ 2: 新しい XPS ドキュメントの作成
次のコードスニペットを使用して、新しい XPS ドキュメントを初期化します。

```java
XpsDocument doc = new XpsDocument();
```

## ステップ 3: XPS ドキュメントへの画像の追加
画像を追加するには、XPS ドキュメント内にパスを作成し、提供された画像ファイルと座標を使用して画像ブラシを設定します。

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```

## ステップ 4: 結果の XPS ドキュメントの保存
変更した XPS ドキュメントを指定したディレクトリに保存します。

```java
doc.save(dataDir + "AddImage_out.xps");
```

これらの手順を繰り返して、画像を追加したり、プロジェクトの要件に合わせて既存の画像をカスタマイズしたりできます。

## まとめ
おめでとうございます！Aspose.Page for Java を使用して XPS ドキュメントに **画像を追加する方法** を習得しました。このスキルは、Java アプリケーションやドキュメントの見た目を向上させるために非常に役立ちます。

### よくある質問
### Aspose.Page for Java を使用して、同じ XPS ドキュメントに複数の画像を追加できますか？
はい。このチュートリアルで説明されている手順を各画像に対して繰り返すことで、複数の画像を追加できます。

### Aspose.Page for Java でサポートされている画像形式は何ですか？
Aspose.Page for Java は、TIFF、JPEG、PNG、GIF など、さまざまな画像形式をサポートしています。

### Aspose.Page for Java の試用版はありますか？
はい。[このリンク](https://releases.aspose.com/) から Aspose.Page for Java の無料試用版を入手できます。

### Aspose.Page for Java の一時ライセンスはどこで入手できますか？
一時ライセンスは [このリンク](https://purchase.aspose.com/temporary-license/) から入手できます。

### Aspose.Page for Java に関する追加サポートや問題について議論するには、どこで確認できますか？
[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39) にアクセスして、ヘルプを求めたり、経験を共有したり、Aspose.Page コミュニティに参加したりしてください。

## その他のヒントとよくある落とし穴
- **パスジオメトリの精度** – SVG スタイルのパス文字列が画像のサイズと一致していることを確認してください。一致していないと、画像が引き伸ばされたり、切り取られたりする可能性があります。
- **イメージブラシのスケーリング** – `createImageBrush` メソッドは、ソースとターゲットの四角形を受け取ります。これらの値を調整することで、位置とスケーリングを正確に制御できます。
- **ライセンスアクティベーション** – 有効なライセンスなしでコードを実行すると、Aspose は生成された XPS ファイルに透かしを追加します。

---

**最終更新日:** 2025年12月28日
**テスト環境:** Aspose.Page for Java 23.12 (執筆時点の最新版)
**作成者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}