---
date: 2026-02-18
description: Aspose.Page を使用して Java で塗りつぶしの色を設定し、PostScript 楕円を作成する方法を学びます。このガイドでは、Java
  で楕円を塗りつぶす方法、楕円の輪郭を描く方法、そしてストロークの太さを設定する方法を示します。
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: JavaでPostScript楕円を描くために塗りの色を設定する
url: /ja/java/postscript-shapes/add-ellipse/
weight: 10
---

.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# JavaでPostScript楕円を描画するためのペイントカラー設定

## はじめに
ベクターグラフィックを描画する際に **ペイントカラーを設定** したい場合、Aspose.Page for Java ライブラリを使用すれば、すべてのストロークや塗りつぶしを完全にコントロールできます。このチュートリアルでは、**ペイントカラーの設定**、**Javaで楕円を塗りつぶす**、そして **楕円の輪郭を描く** 方法をステップバイステップで解説します。最後まで読めば、請求書やレポート、その他印刷可能なドキュメントに高品質な PostScript 楕円を追加できるようになります。

## クイック回答
- **JavaでPostScriptグラフィックを描画するのに最適なライブラリは？** Aspose.Page for Java。  
- **楕円を単色で塗りつぶすことはできますか？** はい – `fill` の前に `document.setPaint(Color.YOUR_COLOR)` を呼び出します。  
- **楕円の輪郭だけを描くには？** ペイントとストロークを設定し、`document.draw(...)` を呼び出します。  
- **本番環境で使用するにはライセンスが必要ですか？** 商用ライセンスが必要です。テスト用の一時ライセンスも利用可能です。  
- **サポートされている Java バージョンは？** 現行の Aspose.Page リリースは Java 8 以降のランタイムで動作します。

## PostScript 楕円とは？
PostScript 楕円は、外接矩形で定義されるベクタ形状です。ラスタ画像とは異なり、品質を損なうことなく拡大縮小できるため、高解像度印刷や PDF 変換に最適です。

## Aspose.Page で PostScript 楕円を作成するメリット
- **描画プリミティブ（線、曲線、楕円）をフルコントロール**。  
- **クロスプラットフォーム** – Windows、Linux、macOS で動作。  
- **外部依存なし** – 純粋な Java API、ネイティブコード不要。  
- **既存の Java アプリケーションやビルドツールへの容易な統合**。

## 前提条件
開始する前に以下を用意してください。

1. 動作する Java 開発環境（JDK 8 以上）。  
2. プロジェクトに Aspose.Page for Java ライブラリを追加。**[こちら](https://releases.aspose.com/page/java/)** からダウンロードできます。  

## パッケージのインポート
Java ソースファイルで、PostScript コンテンツの描画と保存に必要なクラスをインポートします。

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 楕円のペイントカラーを設定する方法
ペイントカラーの設定は、塗りつぶしやストローク操作の最初のステップです。`setPaint` メソッドは、次に実行する描画コマンドで使用される色を決定します。

### 手順 1: PostScript ドキュメントのセットアップ
出力ストリームを作成し、ページサイズを設定し、`PsDocument` のインスタンスを生成します。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 手順 2: 楕円を塗りつぶす – ペイントカラーを使用
**楕円を塗りつぶす** には、まず目的の塗りつぶし色で `setPaint` を呼び出し、次に `Ellipse2D` インスタンスを渡して `fill` を実行します。

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### 手順 3: 楕円の輪郭を描き、ストローク幅を設定
塗りつぶしの後、ペイントを別の色に変更し、`BasicStroke` で線幅を制御して楕円の輪郭を描画します。

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### 手順 4: ドキュメントを閉じて保存
ページを確定し、PostScript ファイルをディスクに書き出します。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

これで、オレンジで塗りつぶされた楕円と、赤で輪郭が描かれた楕円の 2 つを含む PostScript ファイルが作成されました。座標、サイズ、カラーを自由に変更して、デザイン要件に合わせて実験してみてください。

## よくある落とし穴とトラブルシューティング
- **ファイルパスが間違っている** – `dataDir` が OS に適した区切り文字（`/` または `\\`）で終わっていることを確認してください。  
- **ライセンスが未設定** – 有効なライセンスがない場合、ライブラリは評価モードで動作し、透かしが付くことがあります。  
- **カラーが適用されない** – 各 `fill` または `draw` 呼び出しの **直前** に `document.setPaint(...)` を設定してください。ペイント設定は別々の操作間で自動的に保持されません。

## FAQ

**Q: Aspose.Page for Java を他の Java ライブラリと併用できますか？**  
A: はい、Aspose.Page for Java は他の Java ライブラリとシームレスに統合できるよう設計されています。

**Q: Aspose.Page for Java の一時ライセンスはどこで取得できますか？**  
A: テスト目的の一時ライセンスは **[こちら](https://purchase.aspose.com/temporary-license/)** から取得できます。

**Q: 商用プロジェクトで Aspose.Page を使用しても問題ありませんか？**  
A: もちろんです！商用利用向けのライセンスオプションは **[こちら](https://purchase.aspose.com/buy)** でご確認ください。

**Q: Aspose.Page に関する質問や議論はどこでできますか？**  
A: **[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)** に参加して情報交換やサポートを受けられます。

**Q: Aspose.Page for Java の学習に無料リソースはありますか？**  
A: **[無料トライアル](https://releases.aspose.com/)** を利用し、ドキュメント内のサンプルを確認してください。

## 結論
Aspose.Page for Java を使えば、**ペイントカラーの設定**、**楕円の塗りつぶし**、そして **楕円の輪郭描画** がシンプルに行えます。上記の手順に従うだけで、任意の印刷可能ドキュメントにプロフェッショナルなベクタグラフィックをすぐに追加できます。複数形状の組み合わせやグラデーション適用、PDF 変換など、さらに高度な機能については公式 **[ドキュメント](https://reference.aspose.com/page/java/)** を参照してください。

---

**最終更新日:** 2026-02-18  
**テスト環境:** Aspose.Page for Java 24.11  
**作者:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}