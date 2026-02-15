---
date: 2026-02-15
description: Aspose.Page for Java を使用して、PostScript Java ドキュメントの作成方法と、画像の平行移動および回転を伴う
  PostScript ドキュメントファイルの生成方法を学びます。
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: PostScript Java の作成 – Java PostScript に画像を追加
url: /ja/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript Java の作成 – Java PostScript に画像を追加

## はじめに
このチュートリアルでは、Aspose.Page for Java ライブラリを使用して **create postscript java** ドキュメントを作成し、画像を埋め込む方法を学びます。新しい PostScript ファイルの初期化から **translate and rotate image** 変換の適用まで、各ステップを順に解説します。最後まで実施すれば、プログラムから PostScript ファイルを生成し、ピクセル単位の正確さで画像の配置を制御できるようになります。自動レポート作成、印刷ワークフロー、あるいは Java から **generate postscript document** 出力が必要なあらゆるシナリオに最適です。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Page for Java  
- **複数の画像を追加できますか？** はい – 変換と描画の手順を繰り返す  
- **開発用にライセンスが必要ですか？** テストには無料トライアルで動作しますが、本番環境ではライセンスが必要です  
- **サポートされている Java バージョンはどれですか？** Java 8 以降  
- **画像の回転はサポートされていますか？** もちろんです – `AffineTransform.rotate()` を使用してください  

## create postscript java とは？
**create postscript java** 操作は、テキスト、ベクターグラフィック、ラスタ画像をエンコードした PostScript ページ記述ファイルを生成します。Aspose.Page を使用すれば、これらのファイルを Java コードから直接作成でき、レイアウト、スケーリング、回転を完全にプログラムで制御でき、別途 PostScript インタプリタを必要としません。

## 画像操作に Aspose.Page を使用する理由
- **High‑level API:** 低レベルの PostScript コマンドをシンプルな Java メソッドに抽象化します。  
- **Cross‑platform:** Java をサポートする任意の OS で動作します。  
- **Full graphics‑state control:** グラフィックスの保存、復元、平行移動、スケーリング、回転を自由に行えます。  
- **No external dependencies:** 画像の読み込み、フォーマット変換、埋め込みを内部で処理します。

## 前提条件
コードに入る前に、以下が揃っていることを確認してください。

- システムにインストールされた Java Development Kit (JDK)。  
- Aspose.Page for Java ライブラリ。ダウンロードは [here](https://releases.aspose.com/page/java/) から可能です。  
- Java プログラミングの基本的な理解。

## パッケージのインポート
開始するには、Java プロジェクトで必要なパッケージをインポートします。以下のコードスニペットを参考にしてください。

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 手順 1: グラフィックスの保存を書き込む
最初のステップは、ドキュメントにグラフィックスの保存を書き込むことです。これにより、後で行われた変換や変更を必要に応じて元に戻すことができます。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

## 手順 2: 平行移動と変換 (translate and rotate image)
次に、ドキュメントを平行移動し、画像ファイルから `BufferedImage` オブジェクトを作成します。`AffineTransform` を使用して、スケーリングや回転などの一連の変換を適用します。ここで **translate and rotate image** 操作が実行されます。

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

## 手順 3: 画像をドキュメントに追加
次に、変換した画像をドキュメントに追加します。

```java
document.drawImage(image, transform, null);
```

## 手順 4: グラフィックスの復元を書き込む
画像を追加した後、グラフィックスの復元を書き込み、行った変更を確定します。

```java
document.writeGraphicsRestore();
```

## 手順 5: 現在のページを閉じて保存
現在のページを閉じ、ドキュメントを保存します。

```java
document.closePage();
document.save();
```

これらの手順を繰り返すことで、複数の画像を追加したり、要件に応じて変換をカスタマイズしたりできます。

## よくある問題と解決策
- **FileNotFoundException:** `dataDir` パスがファイル区切り文字（`/` または `\\`）で終わっていること、画像ファイル名が正確に一致していることを確認してください。  
- **ImageIO.read returns null:** 画像フォーマットがサポートされているか（例: JPEG、PNG）を確認してください。  
- **Incorrect rotation angle:** `AffineTransform.rotate` はラジアンを期待します。必要に応じて度数をラジアンに変換（`Math.toRadians(degrees)`）してください。  

## よくある質問

**Q: Aspose.Page for Java を他のプログラミング言語と併用できますか？**  
A: Aspose.Page は主に Java をサポートしていますが、他のプログラミング言語向けのバージョンも提供されています。

**Q: Aspose.Page for Java の無料トライアルは利用できますか？**  
A: はい、無料トライアルは [here](https://releases.aspose.com/) からアクセスできます。

**Q: Aspose.Page for Java の一時ライセンスはどのように取得できますか？**  
A: 一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q: Aspose.Page for Java に関するコミュニティサポートやディスカッションはどこで見つけられますか？**  
A: コミュニティサポートは [Aspose.Page Forum](https://forum.aspose.com/c/page/39) をご覧ください。

**Q: Aspose.Page for Java の購入に関する追加リソースはありますか？**  
A: ライブラリは [here](https://purchase.aspose.com/buy) から購入できます。

## 結論
おめでとうございます！Aspose.Page for Java を使用して **create postscript java** ドキュメントを作成し、画像を埋め込む方法を習得しました。ベクターグラフィック、テキストレンダリング、カスタムページサイズなど、より高度な機能や機能については [documentation](https://reference.aspose.com/page/java/) をご確認ください。

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}