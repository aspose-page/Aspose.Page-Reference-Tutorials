---
date: 2026-09-24
description: Aspose.Page を使用して Java で EPS を PNG に変換し、metered license を設定し、PNG ファイルを書き出す
  Java コードを効率的に作成する方法を学びます。
keywords:
- aspose page convert eps
- write png file java
- metered license java
- eps to png conversion
lastmod: 2026-09-24
linktitle: Java で Metered License を設定
og_description: Aspose.Page を使用して Java で EPS を PNG に変換し、metered license を利用します。本ガイドでは、ライセンスの設定方法、EPS
  のレンダリング、PNG ファイルを書き出す Java コードの手順をステップバイステップで示します。
og_image_alt: Guide showing Aspose.Page Java converting EPS to PNG with metered license
og_title: Aspose.Page を使用した Java での EPS から PNG への変換（metered license）
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  headline: Aspose.Page convert EPS to PNG in Java (metered license)
  type: TechArticle
- description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  name: Aspose.Page convert EPS to PNG in Java (metered license)
  steps:
  - name: initialize document and image format
    text: First, set the metered keys and define the output format (PNG). This establishes
      the foundation for the conversion. The `MeteredLicense` class stores your public
      and private keys, while `ImageSaveOptions` tells Aspose.Page to produce PNG
      output.
  - name: initialize PostScript input stream
    text: Open the EPS file you want to convert. The stream feeds the document into
      Aspose.Page. The `FileInputStream` reads the EPS file from disk, allowing the
      `Document` constructor to parse the PostScript data.
  - name: check document license
    text: Always verify that the metered license was applied correctly before processing.
      The `isLicensed()` method returns `true` only when the supplied keys are valid,
      preventing accidental usage of an unlicensed library.
  - name: initialize options and image device
    text: Create the options object that controls conversion settings and the device
      that will receive the rendered image. `ImageDevice` captures the rasterized
      output in memory, while `ImageSaveOptions` lets you tweak DPI, compression level,
      and color depth.
  - name: save EPS file as image
    text: This is the core **save EPS as PNG** call. The document is rendered into
      the image device using the options we configured. The `document.save(device,
      options)` method performs the rasterization in a single step.
  - name: get and save image bytes
    text: Extract the PNG bytes from the device and write them to a file on disk.
      This step demonstrates how to **write PNG file Java** safely. `Files.write(Paths.get("output.png"),
      device.getImagesBytes()[0])` persists the image without additional libraries.
  type: HowTo
- questions:
  - answer: Log into your Aspose account, navigate to the **Metered License** section,
      and copy the generated public and private keys.
    question: How do I obtain metered public and private keys?
  - answer: Aspose.Page offers a free trial with full functionality; production use
      requires a paid license. Download the trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is the Aspose.Page library free?
  - answer: Yes, a commercial license permits deployment in production environments.
      Purchase a license [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: The full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: Temporary licenses are provided through the Aspose portal [Aspose temporary
      license page](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image conversion
- metered licensing
title: Aspose.Page を使用した Java での EPS から PNG への変換（metered license）
url: /ja/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page を使用した Java での EPS から PNG への変換（メーターライセンス）

## はじめに
Java アプリケーションでライセンスをシンプルに保ちながら **EPS を PNG として保存** したい場合、ここが適切な場所です。このチュートリアルでは Aspose.Page の **メーターライセンス** の設定方法、EPS（Encapsulated PostScript）ファイルの読み込み、PNG 画像への変換手順を説明します。最後まで読むと、**EPS を PNG に効率的にレンダリング** する方法と、**Java で PNG ファイルを書き込む** コードを本番環境で信頼して使用できるようになります。

## クイック回答
- **「EPS を PNG として保存」とは何ですか？** ベクターベースの EPS ファイルをラスタ画像の PNG に変換し、透過性とロスレス圧縮を保持します。  
- **なぜメーターライセンスを使用するのですか？** 処理したページ数分だけ支払う方式で、変動するワークロードに最適です。  
- **インターネット接続は必要ですか？** いいえ、メーターキーは JVM 上でローカルに検証されます。  
- **必要な Java のバージョンは？** Java 8 以降が完全にサポートされています。  
- **セットアップにどれくらい時間がかかりますか？** 基本的な実装でおおよそ 10 分です。

## 「EPS を PNG に保存」とは何か
EPS を PNG として保存することは、ベクターベースの Encapsulated PostScript ドキュメントをラスタ PNG 画像に変換し、透過性を保持しつつロスレス圧縮を提供します。この変換は、Web 用のグラフィック、サムネイル、または PostScript インタプリタを必要とせずに任意のブラウザで表示できる印刷プレビューが必要な場合に便利です。

## なぜ Aspose.Page で EPS を PNG にレンダリングするのか
Aspose.Page は純粋な Java API を提供し、EPS ファイルを高忠実度でラスタライズし、50 以上の出力フォーマットをサポートし、変換した分だけ支払うメーターライセンスを提供します。このライブラリは、ファイル全体をメモリにロードせずに数百ページにわたるドキュメントを処理でき、JVM をサポートするあらゆるプラットフォームで高速かつ正確なレンダリングを実現します。

## 前提条件
- 基本的な Java 開発経験。  
- Aspose.Page ライブラリを [Aspose.Page Java ダウンロードページ](https://releases.aspose.com/page/java/) からダウンロード。  
- Aspose アカウントから取得したメーター用の公開キーとプライベートキーのペア。  

## パッケージのインポート
`import` 文は必要なクラスをスコープに持ち込みます。このブロックは変更せずそのまま保持してください。コードが変更なしでコンパイルできます。

`java.io` クラスはファイルストリームを処理し、Aspose.Page クラスはライセンス管理、ドキュメントの読み込み、画像のレンダリングを行います。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Aspose.Page Java を使用して EPS を PNG として保存する方法
以下は、ライセンス設定、読み込み、レンダリング、最終的な PNG ファイルの書き出しを組み合わせたステップバイステップのガイドです。

### 直接的な回答
EPS ファイルを読み込み、メーターライセンスを適用し、PNG 用に `ImageSaveOptions` を構成し、ドキュメントを `ImageDevice` にレンダリングし、最後に生成されたバイト配列をディスクに書き出します。この手順で **EPS を PNG として保存** のワークフローが数行の Java コードで完了します。

### 手順 1: ドキュメントと画像フォーマットの初期化
まず、メーターキーを設定し、出力フォーマット（PNG）を定義します。これが変換の基盤となります。

`MeteredLicense` クラスは公開キーとプライベートキーを保持し、`ImageSaveOptions` は Aspose.Page に PNG 出力を指示します。

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

### 手順 2: PostScript 入力ストリームの初期化
変換したい EPS ファイルを開きます。このストリームがドキュメントを Aspose.Page に供給します。

`FileInputStream` はディスク上の EPS ファイルを読み取り、`Document` コンストラクタが PostScript データを解析できるようにします。

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### 手順 3: ドキュメントライセンスの確認
処理を開始する前に、メーターライセンスが正しく適用されていることを必ず確認してください。

`isLicensed()` メソッドは、提供されたキーが有効な場合にのみ `true` を返し、未ライセンスのライブラリの誤使用を防止します。

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### 手順 4: オプションと画像デバイスの初期化
変換設定を制御するオプションオブジェクトと、レンダリングされた画像を受け取るデバイスを作成します。

`ImageDevice` はメモリ内にラスタライズされた出力を保持し、`ImageSaveOptions` では DPI、圧縮レベル、色深度を調整できます。

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### 手順 5: EPS ファイルを画像として保存
これがコアとなる **EPS を PNG として保存** の呼び出しです。ドキュメントは設定したオプションを使用して画像デバイスにレンダリングされます。

`document.save(device, options)` メソッドは、ラスタライズを一括で実行します。

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### 手順 6: 画像バイトを取得して保存
デバイスから PNG バイト列を抽出し、ディスク上のファイルに書き出します。この手順は **Java で PNG ファイルを書き込む** 方法を安全に示しています。

`Files.write(Paths.get("output.png"), device.getImagesBytes()[0])` は追加のライブラリなしで画像を永続化します。

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## よくある問題と解決策
| 問題 | 発生理由 | 対策 |
|-------|----------------|-----|
| **ライセンスが認識されない** | キーが正しくないか、`setMeteredKey` がドキュメント処理後に呼び出されています。 | 公開キーとプライベートキーの文字列を再確認し、`setMeteredKey` が Aspose.Page の呼び出しより前に実行されていることを確認してください。 |
| **出力ファイルが空** | `device.getImagesBytes()` が `null` を返しました。これは EPS ファイルが解析できなかったためです。 | EPS ファイルが有効であること、`ImageSaveOptions` がゼロでないキャンバスサイズを指定していることを確認してください。 |
| **大きな EPS で OutOfMemoryError** | 大きなベクターファイルのレンダリングはヒープメモリを大量に消費します。 | ページを1つずつ処理するか、JVM ヒープを増やしてください（例: `-Xmx2g`）。 |

## よくある質問

**Q: メーター用の公開キーとプライベートキーはどう取得しますか？**  
A: Aspose アカウントにログインし、**Metered License** セクションへ移動して、生成された公開キーとプライベートキーをコピーしてください。

**Q: Aspose.Page ライブラリは無料ですか？**  
A: Aspose.Page はフル機能の無料トライアルを提供していますが、本番利用には有料ライセンスが必要です。トライアルは [Aspose トライアルダウンロードページ](https://releases.aspose.com/) からダウンロードしてください。

**Q: Aspose.Page を商用プロジェクトで使用できますか？**  
A: はい、商用ライセンスにより本番環境での展開が可能です。ライセンスは [Aspose 購入ページ](https://purchase.aspose.com/buy) から購入してください。

**Q: 追加のドキュメントはどこで見つけられますか？**  
A: 完全な API リファレンスは [Aspose.Page Java API リファレンス](https://reference.aspose.com/page/java/) で利用できます。

**Q: 評価用の一時ライセンスはどう取得できますか？**  
A: 一時ライセンスは Aspose ポータルの [Aspose 一時ライセンスページ](https://purchase.aspose.com/temporary-license/) から提供されています。

**Q: 複数ページの EPS ファイルを変換する必要がある場合は？**  
A: `device.getImagesBytes()` を使用して各ページをループし、各バイト配列を別々の PNG ファイルに書き出してください。

**Q: PNG の品質や色深度を変更できますか？**  
A: はい、`document.save(...)` を呼び出す前に `ImageSaveOptions` を設定してください（例: `options.setCompressionLevel(9)`）。

---

**Last Updated:** 2026-09-24  
**Tested with:** Aspose.Page 24.12 for Java (latest)  
**Author:** Aspose

## 関連チュートリアル

- [Aspose.Page Java API のライセンス設定方法 – ライセンス管理](/page/java/license-management/)
- [Aspose.Page Java API で PS を PNG に変換](/page/java/postscript-conversion/to-image/)
- [Aspose.Page を使用した EPS のリサイズ – Java EPS 操作](/page/java/manipulation-eps/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}