---
title: Java で XPS を JPEG に変換する
linktitle: Java で XPS を JPEG に変換する
second_title: Aspose.Page Java API
description: Aspose.Page を使用して Java で XPS を JPEG に変換する方法を学びます。シームレスな統合のための段階的な手順を記載した包括的なガイド。
weight: 11
url: /ja/java/xps-conversion/to-jpeg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java で XPS を JPEG に変換する

## 導入
このチュートリアルでは、Aspose.Page for Java を使用して XPS (XML Paper Supplement) ファイルを JPEG 画像に変換する方法を説明します。 Aspose.Page は、開発者が XPS やその他のドキュメント形式をシームレスに操作できるようにする強力な Java ライブラリです。このステップバイステップのガイドは、プロセスを理解し、Java アプリケーションに実装するのに役立ちます。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- Java 開発環境: マシン上に Java 開発環境がセットアップされていることを確認します。
-  Aspose.Page for Java ライブラリ: Aspose.Page for Java ライブラリをダウンロードしてインストールします。図書館を見つけることができます[ここ](https://releases.aspose.com/page/java/).
- サンプル XPS ドキュメント: JPEG に変換するサンプル XPS ドキュメントを用意します。
## パッケージのインポート
まず、必要なパッケージを Java クラスにインポートします。
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## ステップ 1: パスと XPS ドキュメントを初期化する
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//XPS入力ストリームを初期化する
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## ステップ 2: JpegSaveOptions を設定する
```java
//必要なパラメータを使用してオプション オブジェクトを初期化します。
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## ステップ 3: レンダリング デバイスを作成する
```java
//PDF 形式用のレンダリング デバイスを作成する
ImageDevice device = new ImageDevice();
```
## ステップ 4: XPS を JPEG として保存する
```java
document.save(device, options);
```
## ステップ 5: JPEG ページを反復して保存する
```java
//ドキュメント パーティション (XPS 用語では固定ドキュメント) を反復処理します。
for (int i = 0; i < device.getResult().length; i++) {
    //パーティションページを反復処理する
    for (int j = 0; j < device.getResult()[i].length; j++) {
        //画像出力ストリームを初期化する
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        //画像の書き込み
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //ストリームを閉じる
        imageStream.close();
    }
}
```
この一連の手順により、XPS ドキュメントが JPEG 画像に効果的に変換され、それぞれが個別に保存されます。
## 結論
おめでとう！ Aspose.Page を使用して Java で XPS を JPEG に変換する方法を学習しました。このプロセスは、Java アプリケーションでドキュメント変換を扱う開発者にとって非常に貴重です。
## よくある質問

### Q: Aspose.Page は商用プロジェクトに適していますか?
 A: はい、Aspose.Page は商用製品であり、ライセンス オプションが利用可能です。チェック[ここ](https://purchase.aspose.com/buy)詳細については。
### Q: 購入する前に Aspose.Page を試すことはできますか?
 A: はい、無料トライアルを利用できます[ここ](https://releases.aspose.com/).
### Q: Aspose.Page ドキュメントはどこで見つけられますか?
 A: ドキュメントは入手可能です[ここ](https://reference.aspose.com/page/java/).
### Q: Aspose.Page のサポートを受けるにはどうすればよいですか?
 A: にアクセスしてください。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティベースのサポートのために。
### Q: テストには一時ライセンスが必要ですか?
 A: はい、一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
