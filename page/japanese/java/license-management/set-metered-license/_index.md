---
date: 2026-02-05
description: Aspose.Page for Java を使用して EPS を PNG に保存する方法と、メーター制ライセンスの設定方法を学びます。ステップバイステップのガイドと完全なコード例付き。
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Aspose.Page Java（従量課金ライセンス）でEPSをPNGに保存
url: /ja/java/license-management/set-metered-license/
weight: 10
---

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Save EPS as PNG with Aspose.Page Java (Metered License)

## Introduction
Java アプリケーションで **EPS を PNG として保存** したい場合、ライセンス管理が手間なく行える方法をご紹介します。このチュートリアルでは、Aspose.Page のメータード ライセンスの設定方法、PostScript (EPS) ファイルの読み込み、PNG 画像への変換手順を、すぐに実行できるシンプルなステップで解説します。最後まで読むと、**EPS を PNG にレンダリング** する効率的な方法と、**PNG ファイルを書き込む Java** コードの実装方法が理解できます。

## Quick Answers
- **「EPS を PNG として保存」とは何ですか？** ベクタ形式の EPS ファイルをラスタ画像の PNG に変換します。  
- **メータード ライセンスを使う理由は？** 処理したページ数分だけ支払う方式で、変動するワークロードに最適です。  
- **インターネット接続は必要ですか？** いいえ、メータード キーはローカルで検証されます。  
- **必要な Java バージョンは？** Java 8 以上。  
- **セットアップにかかる時間は？** 基本実装で約 10 分程度です。  

## What is “save EPS as PNG”?
EPS を PNG として保存することは、拡張可能な Encapsulated PostScript ドキュメントを、広くサポートされているビットマップ形式に変換することです。PNG は透過性を保持し、ロスレス圧縮を提供するため、ウェブグラフィック、サムネイル、印刷プレビューに最適です。

## Why render EPS to PNG with Aspose.Page?
- **Pure Java API** – ネイティブ依存がなく、JVM が動作する環境ならどこでも実行可能です。  
- **High fidelity rendering** – ベクタ画像を正確にラスタライズし、線の品質を保持します。  
- **Metered licensing** – 変換した分だけ支払うので、コストが予測しやすくなります。  
- **Multiple output options** – PNG の他に JPEG、TIFF なども生成でき、プロジェクトに応じた柔軟な出力が可能です。

## Prerequisites
開始する前に、以下を確認してください。

- Java プログラミングの基本知識。  
- Aspose.Page ライブラリのインストール – [here](https://releases.aspose.com/page/java/) からダウンロード。  
- メータード 公開キーとプライベートキー（Aspose アカウントで取得可能）。

## Import Packages
まず、必要なクラスをインポートします。コードがそのままコンパイルできるよう、インポートブロックは示された通りにしてください。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## How to save EPS as PNG using Aspose.Page Java
以下は、ライセンス設定、読み込み、レンダリング、最終 PNG ファイルの書き出しを組み合わせたステップバイステップ ガイドです。

### Step 1: Initialize Document and Image Format
ここではメータード キーを設定し、出力フォーマット (PNG) を定義します。これが **EPS を PNG として保存** 操作の基礎となります。

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

### Step 2: Initialize PostScript Input Stream
変換したい EPS ファイルを開きます。ストリームはドキュメントを Aspose.Page に渡す役割を果たします。

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Step 3: Check Document License
処理を開始する前に、メータード ライセンスが正しく適用されたか必ず確認してください。

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Step 4: Initialize Options and Image Device
変換設定を制御するオプションオブジェクトと、レンダリング結果を受け取るデバイスを作成します。

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Step 5: Save EPS File as Image
これがコアとなる **EPS を PNG として保存** 呼び出しです。設定したオプションを使用して、ドキュメントを画像デバイスにレンダリングします。

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Step 6: Get and Save Image Bytes
デバイスから PNG バイト列を取得し、ディスク上のファイルに書き出します。この手順で **PNG ファイルを書き込む Java** の安全な実装例を示します。

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

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **License not recognized** | キーが間違っているか、順序が誤っている。 | 公開キー/プライベートキー文字列を再確認し、`setMeteredKey` をドキュメント処理の前に呼び出すことを確認してください。 |
| **Output file is empty** | `device.getImagesBytes()` が `null` を返した。 | EPS ファイルが有効か、`ImageSaveOptions` がゼロサイズのキャンバスに設定されていないかを確認してください。 |
| **OutOfMemoryError on large EPS** | 大きなベクタファイルのレンダリングに大量のメモリが必要。 | ページ単位で処理するか、JVM ヒープを増やす（例: `-Xmx2g`）。 |

## Frequently Asked Questions

**Q: How do I obtain metered public and private keys?**  
A: You can obtain these keys through your Aspose account.

**Q: Is the Aspose.Page library free?**  
A: Aspose.Page offers both free trial and paid versions. Visit [here](https://releases.aspose.com/) for a free trial.

**Q: Can I use Aspose.Page for commercial projects?**  
A: Yes, Aspose.Page offers commercial licenses. You can purchase them [here](https://purchase.aspose.com/buy).

**Q: Where can I find additional documentation?**  
A: Refer to the documentation [here](https://reference.aspose.com/page/java/).

**Q: How can I get temporary licenses?**  
A: Temporary licenses can be obtained [here](https://purchase.aspose.com/temporary-license/).

**Q: What if I need to convert multi‑page EPS files?**  
A: Loop through each page using `device.getImagesBytes()` and write each byte array to a separate PNG file.

**Q: Can I change the PNG quality or color depth?**  
A: Yes, configure `ImageSaveOptions` (e.g., `options.setCompressionLevel(...)`) before calling `document.save(...)`.

---

**最終更新日:** 2025-12-03  
**テスト環境:** Aspose.Page 24.12 for Java  
**作者:** Aspose  

**最終更新日:** 2026-02-05  
**テスト環境:** Aspose.Page 24.12 for Java (latest)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}