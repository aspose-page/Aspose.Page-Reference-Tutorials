---
title: Aspose.Page Java との簡単な従量制ライセンスの統合
linktitle: Java で従量制ライセンスを設定する
second_title: Aspose.Page Java API
description: Aspose.Page と Java のシームレスな統合を検討してください。従量制ライセンスを簡単にセットアップし、ドキュメント処理機能を強化します。
type: docs
weight: 10
url: /ja/java/license-management/set-metered-license/
---
## 導入
Aspose.Page を使用して Java で従量制ライセンスを設定するための包括的なガイドへようこそ。ドキュメント処理機能を強化し、Aspose.Page とのシームレスな統合を確保したい場合は、ここが最適な場所です。このチュートリアルでは、各ステップを理解しやすい部分に分けてプロセスを説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- Java プログラミングの基本的な知識。
-  Aspose.Page ライブラリがインストールされています。からダウンロードできます[ここ](https://releases.aspose.com/page/java/).
- 従量制の公開キーと秘密キー。Aspose アカウントを通じて取得できます。
## パッケージのインポート
Java プログラムに必要なパッケージをインポートすることから始めましょう。 Aspose.Page ライブラリがプロジェクトに統合されていることを確認してください。
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## ステップ 1: ドキュメントと画像のフォーマットを初期化する
最初のステップは、ドキュメントを設定し、目的の画像形式を定義することです。
```java
//従量制の公開鍵と秘密鍵を設定する
com.aspose.page.Metered metered = new com.aspose.page.Metered();
//setMeteredKey プロパティにアクセスし、公開キーと秘密キーをパラメータとして渡します。
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## ステップ 2: PostScript 入力ストリームを初期化する
このステップでは、処理のために PostScript 入力ストリームを初期化します。
```java
// PostScript 入力ストリームを初期化する
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## ステップ 3: ドキュメントのライセンスを確認する
続行する前に、ドキュメントが適切にライセンスされているかどうかを確認することが重要です。
```java
//ドキュメントがライセンスされているかどうかを確認する
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## ステップ 4: オプションとイメージ デバイスを初期化する
次に、オプションと画像デバイスをデフォルトのパラメータで初期化しましょう。
```java
//デフォルトのパラメータを使用してオプション オブジェクトを初期化します。
ImageSaveOptions options = new ImageSaveOptions();
// ImageDevice オブジェクトをデフォルトのパラメータで初期化します。
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## ステップ 5: EPS ファイルを画像として保存する
定義されたオプションとデバイスを使用して、EPS ファイルを画像として保存します。
```java
// EPSファイルを画像として保存
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## ステップ 6: 画像バイトを取得して保存する
画像バイトを取得してファイルに保存します。
```java
//画像バイトを取得します。 1 ページに 1 バイトの配列。私たちの場合、ページは 1 つあります。
byte[][] imagesBytes = device.getImagesBytes();
//画像バイトをファイルに保存
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## 結論
おめでとう！ Aspose.Page を使用して Java で従量制ライセンスを正常にセットアップできました。このチュートリアルでは、統合プロセスをスムーズに進めるためのステップバイステップのガイドを提供しました。
## よくある質問
### Q: 従量制の公開キーと秘密キーを取得するにはどうすればよいですか?
これらのキーは、Aspose アカウントを通じて取得できます。
### Q: Aspose.Page ライブラリは無料ですか?
 Aspose.Page には、無料試用版と有料版の両方が用意されています。訪問[ここ](https://releases.aspose.com/)無料トライアルのため。
### Q: Aspose.Page を商用プロジェクトに使用できますか?
はい、Aspose.Page は商用ライセンスを提供しています。購入できます[ここ](https://purchase.aspose.com/buy).
### Q: 追加のドキュメントはどこで入手できますか?
ドキュメントを参照してください[ここ](https://reference.aspose.com/page/java/).
### Q: 一時ライセンスを取得するにはどうすればよいですか?
仮免許も取得できる[ここ](https://purchase.aspose.com/temporary-license/).