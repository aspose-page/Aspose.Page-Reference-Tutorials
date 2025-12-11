---
date: 2025-12-09
description: Aspose.Page を使用して、シームレスな画像操作のために、Java で PostScript ドキュメントを作成し、画像の平行移動と回転を行う方法を学びましょう。
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: JavaでPostScript文書を作成 – Java PostScriptに画像を追加
url: /ja/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript ドキュメント（Java）作成 – Java PostScript に画像を追加

## はじめに
このチュートリアルでは、**PostScript ドキュメント（Java）を作成**し、Aspose.Page for Java ライブラリを使用して画像を埋め込む方法を学びます。ドキュメントの設定から、**画像の平行移動と回転**といった変換の適用まで、各ステップを順に解説します。最後まで実施すれば、プログラムでリッチな PostScript ファイルを生成し、レイアウト要件に合わせて画像の配置をカスタマイズできるようになります。

## クイック回答
- **必要なライブラリは？** Aspose.Page for Java  
- **複数の画像を追加できますか？** はい – 変換と描画の手順を繰り返します  
- **開発にライセンスは必要ですか？** テストには無料トライアルで動作しますが、製品版ではライセンスが必要です  
- **サポートされている Java バージョンは？** Java 8 以降  
- **画像の回転はサポートされていますか？** もちろんです – `AffineTransform.rotate()` を使用します  

## Java で PostScript ドキュメントを作成するとは？
PostScript ドキュメントは、テキスト、グラフィック、画像を記述するページ記述言語ファイルです。Aspose.Page を使用すると、Java でこれらのファイルをプログラム的に生成でき、レイアウトやグラフィック状態、画像処理を完全に制御できるため、PostScript インタプリタが不要になります。

## 画像操作に Aspose.Page を使用する理由
- **ハイレベル API:** 複雑な PostScript コマンドを簡素化します。  
- **クロスプラットフォーム:** Java が動作するすべての OS で利用可能です。  
- **完全なグラフィックス状態制御:** グラフィックの保存、復元、平行移動、拡大縮小、回転を簡単に行えます。  
- **外部依存なし:** 画像の読み込みと変換を内部で処理します。

## 前提条件
- システムに Java Development Kit (JDK) がインストールされていること。  
- Aspose.Page for Java ライブラリ。こちらからダウンロードできます [こちら](https://releases.aspose.com/page/java/)。  
- Java プログラミングの基本的な理解があること。  

## パッケージのインポート
開始するには、Java プロジェクトで必要なパッケージをインポートします。以下のコードスニペットを参照してください。

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## ステップ 1: グラフィックスの保存を書き込む
最初のステップは、ドキュメントにグラフィックスの保存を書き込むことです。これにより、後続の変換や修正を必要に応じてロールバックできるようになります。

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

## ステップ 2: 平行移動と変換（画像の平行移動と回転）
次に、ドキュメントを平行移動し、画像ファイルから `BufferedImage` オブジェクトを作成します。`AffineTransform` を使用してスケーリングや回転などの一連の変換を適用します。ここで **画像の平行移動と回転** が行われます。

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

## ステップ 3: ドキュメントに画像を追加
変換された画像をドキュメントに追加します。

```java
document.drawImage(image, transform, null);
```

## ステップ 4: グラフィックスの復元を書き込む
画像を追加した後、変更を確定するためにグラフィックスの復元を書き込みます。

```java
document.writeGraphicsRestore();
```

## ステップ 5: 現在のページを閉じて保存
現在のページを閉じ、ドキュメントを保存します。

```java
document.closePage();
document.save();
```

これらの手順を繰り返すことで、複数の画像を追加したり、要件に合わせて変換をカスタマイズしたりできます。

## 一般的な問題と解決策
- **FileNotFoundException:** `dataDir` パスがファイル区切り文字（`/` または `\\`）で終わっていること、画像ファイル名が正確に一致していることを確認してください。  
- **ImageIO.read が null を返す:** 画像形式がサポートされているか（例: JPEG、PNG）を確認してください。  
- **回転角度が正しくない:** `AffineTransform.rotate` はラジアンを期待します。必要に応じて度数をラジアンに変換（`Math.toRadians(degrees)`）してください。  

## よくある質問

**Q: Aspose.Page for Java を他のプログラミング言語と併用できますか？**  
A: Aspose.Page は主に Java をサポートしていますが、他のプログラミング言語向けのバージョンも用意されています。

**Q: Aspose.Page for Java の無料トライアルは利用できますか？**  
A: はい、無料トライアルにアクセスできます [こちら](https://releases.aspose.com/)。

**Q: Aspose.Page for Java の一時ライセンスはどのように取得できますか？**  
A: 一時ライセンスは [こちら](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q: Aspose.Page for Java に関するコミュニティサポートやディスカッションはどこで見つけられますか？**  
A: コミュニティサポートは [Aspose.Page Forum](https://forum.aspose.com/c/page/39) をご覧ください。

**Q: Aspose.Page for Java の購入に関する追加リソースはありますか？**  
A: ライブラリは [こちら](https://purchase.aspose.com/buy) から購入できます。

## 結論
おめでとうございます！Aspose.Page for Java を使用して **PostScript ドキュメント（Java）を作成**し、画像を埋め込む方法を習得できました。ベクトルグラフィック、テキスト描画、カスタムページサイズなど、さらに高度な機能については [ドキュメント](https://reference.aspose.com/page/java/) をご参照ください。

---

**最終更新日:** 2025-12-09  
**テスト環境:** Aspose.Page for Java 23.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}