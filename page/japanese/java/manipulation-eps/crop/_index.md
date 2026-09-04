---
date: 2026-09-04
description: Aspose.Page を使用して Java で EPS ファイルをトリミングし、EPS ファイルサイズを削減する方法を学びます – ステップバイステップのガイドで、crop
  eps、crop eps image、trim eps file の方法を示します。
keywords:
- reduce eps file size
- how to crop eps
- Aspose.Page Java
- EPS cropping Java
lastmod: 2026-09-04
linktitle: JavaでEPSファイルをトリミング
og_description: Aspose.Page を使用して Java で EPS ファイルをトリミングし、EPS ファイルサイズを削減する方法を学びます –
  コードとヒントを含む簡潔なガイドです。
og_image_alt: 'Guide: cropping EPS files in Java to reduce file size with Aspose.Page'
og_title: JavaでEPSファイルをトリミングしてEPSファイルサイズを削減する方法
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  headline: How to crop EPS files in Java to reduce EPS file size
  type: TechArticle
- description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  name: How to crop EPS files in Java to reduce EPS file size
  steps:
  - name: set document directory and input stream
    text: Here we point the code to the folder that holds our source EPS file and
      open a stream for reading it.
  - name: initialize PsDocument object
    text: The `PsDocument` class represents an EPS file in memory, allowing you to
      read and modify its properties. The object gives you access to the original
      bounding box and other metadata.
  - name: extract initial bounding box
    text: Extracting the original bounding box gives you the coordinates of the current
      visible area – handy for deciding how much you need to trim.
  - name: create output stream
    text: We open a stream where the cropped EPS will be written.
  - name: define new bounding box and crop
    text: The `cropEps` method trims the document to a new bounding box and writes
      the result to an output stream. Provide the four coordinates (lower‑left x,
      lower‑left y, upper‑right x, upper‑right y) that define the area you want to
      keep. The method performs the cropping and writes the result to `output_cr
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works with Java 8 and any later version.
    question: Is Aspose.Page compatible with Java 8?
  - answer: Absolutely. A commercial license is required for production deployments.
      You can obtain one [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: Visit the official [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for discussions, code samples, and troubleshooting tips.
    question: Where can I find additional resources and community support?
  - answer: Yes, you can download a free trial of Aspose.Page from the releases page
      [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is there a free trial available for testing?
  - answer: A temporary license can be requested from the licensing portal [temporary
      license request page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for short‑term evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- reduce eps file size
- Aspose.Page
- Java EPS processing
- crop EPS
title: JavaでEPSファイルをトリミングしてEPSファイルサイズを削減する方法
url: /ja/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# JavaでEPSファイルをトリミングしてサイズを削減する方法

## はじめに
Javaアプリケーションで **crop EPS** ファイルをプログラム的に処理し、 **reduce EPS file size** を実現したい場合は、ここが最適です。このチュートリアルでは、強力な Aspose.Page for Java ライブラリを使用して EPS 画像をトリミングする手順をすべて解説します。ガイドの最後まで読むと、なぜ EPS のトリミングが重要なのかが分かり、必要なコードを確認でき、独自プロジェクトへの統合準備が整います。

## クイック回答
- **JavaでEPSトリミングを処理するライブラリは何ですか？** Aspose.Page for Java。  
- **基本的なトリミングの実装にどれくらい時間がかかりますか？** 約5〜10分。  
- **開発にライセンスは必要ですか？** 評価用の無料トライアルで動作しますが、商用利用には商用ライセンスが必要です。  
- **サポートされている Java バージョンは？** Java 8 以降。  
- **カスタムのバウンディングボックスを定義できますか？** はい、必要な座標を指定します。

## EPSトリミングとは何か、そしてなぜ使用するのか
**EPSトリミングは、EPS ファイルの表示領域を定義する新しいバウンディングボックスを作成します。**  
EPS ファイルをトリミングすると、不要な余白が除去され、実際に必要な領域だけにグラフィックが切り詰められるため、**EPS ファイルサイズを直接削減** でき、PDF やレポートなどの下流ドキュメントでレイアウトの一貫性が向上します。

## なぜEPSファイルをトリミングするのか？
EPS ファイルをトリミングすると、ファイルサイズを最大30 % まで縮小でき、余分な余白を排除し、バッチ処理パイプライン向けにグラフィックを標準化できます。多数の EPS アセットを単一の PDF に埋め込む場合や、低消費電力デバイスでのレンダリング速度を向上させたい場合に特に有用です。

## 前提条件
以下を事前に用意してください。

- **Aspose.Page for Java** ライブラリがインストールされていること – 公式ページからダウンロードしてください [Aspose.Page for Java release page](https://releases.aspose.com/page/java/)。  
- **Java Development Kit (JDK)** 8 以上がマシンにインストールされていること。  
- **フォルダー** を用意し、入力 EPS (`input.eps`) とトリミング後のファイル (`output_crop.eps`) を格納できるようにします。

## パッケージのインポート
まず、必要な Java クラスをインポートします。このスニペットはオリジナルのチュートリアルと全く同じです。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

## JavaでEPS画像をトリミングする方法
ソース EPS を読み込み、新しいバウンディングボックスを定義し、トリミング API を呼び出すだけで、5 つの簡潔な手順で完了します。

### ステップ1: ドキュメントディレクトリと入力ストリームの設定
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
ここでは、ソース EPS ファイルが格納されているフォルダーを指し示し、読み取り用ストリームを開きます。

### ステップ2: PsDocument オブジェクトの初期化
`PsDocument` クラスはメモリ内の EPS ファイルを表し、プロパティの読み取りや変更が可能です。  
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
このオブジェクトを通じて、元のバウンディングボックスやその他のメタデータにアクセスできます。

### ステップ3: 初期バウンディングボックスの抽出
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
元のバウンディングボックスを抽出すると、現在の表示領域の座標が得られ、どれだけトリミングすべきか判断しやすくなります。

### ステップ4: 出力ストリームの作成
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
トリミング後の EPS が書き込まれるストリームを開きます。

### ステップ5: 新しいバウンディングボックスの定義とトリミング
`cropEps` メソッドはドキュメントを新しいバウンディングボックスに合わせてトリミングし、結果を出力ストリームに書き込みます。  
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
保持したい領域を定義する 4 つの座標（左下 x、左下 y、右上 x、右上 y）を指定してください。メソッドはトリミングを実行し、結果を `output_crop.eps` に書き出します。

## 一般的な問題と解決策
- **座標が正しくない:** EPS はポイント（1/72 インチ）単位です。トリミングがずれて見える場合は単位変換を再確認してください。  
- **ファイルが見つからないエラー:** `dataDir` が適切なパス区切り文字（`/` または `\`）で終わっていることを確認してください。  
- **ライセンス例外:** 有効なライセンスなしでコードを実行すると、出力に透かしが付くことがあります。本番環境で使用する前に一時または永続ライセンスを適用してください。

## よくある質問

**Q: Aspose.PageはJava 8と互換性がありますか？**  
A: はい、Aspose.PageはJava 8およびそれ以降のバージョンで動作します。

**Q: Aspose.Pageを商用プロジェクトで使用できますか？**  
A: もちろんです。商用展開には商用ライセンスが必要です。購入は [Aspose purchase page](https://purchase.aspose.com/buy) から行えます。

**Q: 追加のリソースやコミュニティサポートはどこで得られますか？**  
A: 公式 [Aspose.Page forum](https://forum.aspose.com/c/page/39) でディスカッション、コードサンプル、トラブルシューティング情報が提供されています。

**Q: 無料トライアルは利用できますか？**  
A: はい、[Aspose.Page releases page](https://releases.aspose.com/) から無料トライアルをダウンロードできます。

**Q: 短期評価用の一時ライセンスはどう取得しますか？**  
A: 一時ライセンスはライセンスポータルの [temporary license request page](https://purchase.aspose.com/temporary-license/) からリクエストできます。

## 結論
これで **how to crop EPS** ファイルを Java と Aspose.Page を使って **reduce EPS file size** できる方法が分かりました。カスタムバウンディングボックスを定義し `cropEps` を呼び出すだけで、不要な余白を削除したり、EPS グラフィックの特定部分だけを抽出したりできます。このスニペットをドキュメント処理パイプラインに組み込めば、EPS の操作を自動化し、**crop EPS image** アセットや **trim EPS file** コンテンツを効率的に処理できます。

---

**最終更新日:** 2026-09-04  
**テスト環境:** Aspose.Page for Java 24.11  
**作者:** Aspose

## 関連チュートリアル

- [JavaでAspose.Pageを使用してEPSファイルのサイズ変更方法](/page/java/manipulation-eps/resize/)
- [Aspose.Page JavaでEPSをPNGに変換する方法（メータードライセンス）](/page/java/license-management/set-metered-license/)
- [Aspose Page Javaチュートリアル – EPSファイルにXMPメタデータを追加する](/page/java/xmp-metadata-manipulation/add-metadata/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}