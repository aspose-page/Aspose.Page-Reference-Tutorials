---
date: 2025-12-23
description: Aspose.Page JavaでXPSをTIFFに簡単変換。Aspose.Page Javaを使用したシームレスな統合のためのステップバイステップガイドに従ってください。今すぐダウンロード！
linktitle: Convert XSP to TIFF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: Aspose.Page Java を使用して Java で XSP を TIFF に変換する
url: /ja/java/xps-conversion/to-tiff/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# JavaでAspose.Page Javaを使用してXSPをTIFFに変換

今日の急速に変化するソフトウェア環境において、**aspose page java** は Java ドキュメント変換をシンプルかつ信頼性の高いものにします。アーカイブ、印刷、バッチ処理のために **XPS を TIFF に変換** したい場合、本チュートリアルでは正確な手順を示し、各操作の「なぜ」を解説し、すぐに活用できる実践的なヒントを提供します。

## クイックアンサー
- **XPS‑to‑TIFF 変換を担当するライブラリは？** Aspose.Page Java。  
- **本番環境でライセンスは必要ですか？** はい、有効な Aspose.Page Java ライセンスが必要です。  
- **サポートされている Java バージョンは？** JDK 8 以降。  
- **複数の XPS ファイルを同時に変換できますか？** はい、同じコードを使ってバッチ変換ループを構築できます。  
- **印刷用 TIFF の最適解像度は？** 300 DPI が一般的ですが、TiffSaveOptions で調整可能です。

## Aspose.Page Java とは？
Aspose.Page Java は、XPS（XML Paper Specification）から TIFF を含む幅広いラスタ・ベクタ形式へ **java document conversion** を実現する強力な API です。Microsoft XPS Document Writer を必要とせず、複雑なページレイアウト、フォント、グラフィックを処理します。

## XPS から TIFF への変換に Aspose.Page Java を使用する理由
- **高忠実度:** ベクトルデータとテキストのレンダリングを保持。  
- **パフォーマンス:** 大容量ファイルやバッチ XPS 変換シナリオに最適化。  
- **柔軟性:** 解像度、圧縮、ページ選択など `tiff save options` で細かく調整可能。  
- **クロスプラットフォーム:** Java が動作する任意の OS で利用でき、サーバーサイド処理に最適。

## 前提条件
変換プロセスに入る前に、以下を準備してください。

- マシンに Java Development Kit (JDK) がインストールされていること。  
- Aspose.Page for Java ライブラリ。ダウンロードは [here](https://releases.aspose.com/page/java/) から。  
- 有効な Aspose.Page for Java ライセンス。臨時ライセンスは [here](https://purchase.aspose.com/temporary-license/) で取得でき、正式ライセンスは [here](https://purchase.aspose.com/buy) から購入できます。

## パッケージのインポート
Java プロジェクトで必要なパッケージをインポートします。Aspose.Page for Java の JAR がビルドパスに追加されていることを確認してください。

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## ステップ 1: ドキュメントディレクトリの設定
ソース XPS ファイルが格納されているフォルダーへのパスを定義します。

```java
String dataDir = "Your Document Directory";
```

## ステップ 2: XPS ドキュメントの読み込み
入力ファイルを指す `XpsDocument` インスタンスを作成します。

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

## ステップ 3: TiffSaveOptions の初期化
画像品質、解像度、エクスポートするページを制御する **tiff save options** を設定します。

```java
TiffSaveOptions options = new TiffSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

## ステップ 4: レンダリングデバイスの作成
ページを TIFF 画像にレンダリングする `ImageDevice` をインスタンス化します。

```java
ImageDevice device = new ImageDevice();
```

## ステップ 5: ドキュメントを TIFF に保存
デバイスと先ほど定義したオプションを使用して XPS ドキュメントをレンダリングします。

```java
document.save(device, options);
```

## ステップ 6: TIFF イメージの反復処理と保存
レンダリングされた画像バッファをループし、各ページを個別の TIFF ファイルとして書き出します。

```java
for (int i = 0; i < device.getResult().length; i++) {
    for (int j = 0; j < device.getResult()[i].length; j++) {
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoTIFF" + "_" + (i + 1) + "_" + (j + 1) + ".tif");
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

おめでとうございます！**aspose page java** を使用して、Java で **XPS から TIFF への変換** に成功しました。ライブラリのその他の機能については、[ドキュメント](https://reference.aspose.com/page/java/) をご覧ください。

## まとめ
このチュートリアルでは、XPS から TIFF への **java document conversion** を実行するために必要なすべての手順を網羅しました。環境設定から `tiff save options` の微調整まで、Aspose.Page Java を使えば、数十から数百のファイルを自動で処理する **batch XPS conversion** パイプラインも構築できます。

## よくある質問

### Aspose.Page for Java はライセンスなしで使用できますか？

評価用の臨時ライセンスは取得可能ですが、本番環境での使用には有効なライセンスが必要です。ライセンスは [here](https://purchase.aspose.com/buy) から入手してください。

### 変換可能な XPS ファイルのサイズに制限はありますか？

Aspose.Page for Java は様々なサイズのドキュメントを処理できますが、実際の環境で大容量ファイルのテストを行うことを推奨します。

### Aspose.Page for Java に関するサポートや質問を受けるにはどうすればよいですか？

コミュニティサポートやディスカッションは [Aspose.Page forum](https://forum.aspose.com/c/page/39) で行えます。

### Aspose.Page for Java の無料トライアルはありますか？

はい、無料トライアルでライブラリを試すことができます。ダウンロードは [here](https://releases.aspose.com/) から。

### この変換における TIFF 画像の推奨解像度は？

例では 300 DPI の解像度を使用していますが、要件に応じて調整可能です。

---

**最終更新日:** 2025年12月23日
**テスト環境:** Aspose.Page Java 24.11 (執筆時点の最新版)
**作成者:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}