---
title: Java を使用して XMP に単純なプロパティを追加する
linktitle: Java を使用して XMP に単純なプロパティを追加する
second_title: Aspose.Page Java API
description: EPS ファイル内の XMP メタデータにプロパティを追加するガイドを参照して、Aspose.Page for Java の可能性を解き放ってください。文書処理を簡単に向上させます。
weight: 14
url: /ja/java/xmp-metadata-manipulation/add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java を使用して XMP に単純なプロパティを追加する

## 導入
進化し続けるドキュメント処理の状況では、メタデータを効率的に管理することが非常に重要です。 Aspose.Page for Java を使用すると、開発者は Extensible Metadata Platform (XMP) データをシームレスに操作できるようになります。このチュートリアルでは、Java を使用して単純なプロパティを XMP に追加するプロセスを説明し、包括的なステップバイステップのガイドを提供します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- Java プログラミングの基本的な知識。
-  Aspose.Page for Java ライブラリがインストールされています。ダウンロードできます[ここ](https://releases.aspose.com/page/java/).
- メタデータを含むサンプル EPS ファイル。お持ちでない場合は、提供されている「xmp3.eps」ファイルを自由に使用してください。
## パッケージのインポート
プロジェクトを開始するために必要なパッケージをインポートしていることを確認してください。
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## ステップ 1: XMP メタデータを取得する
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//入力EPSファイルストリームを初期化します
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
//XMP メタデータを取得します。 EPS ファイルに XMP メタデータが含まれていない場合は、PS メタデータ コメント (%%Creator、%%CreateDate、%%Title など) からの値が埋め込まれた新しいファイルを取得します。
XmpMetadata xmp = document.getXmpMetadata();
```
## ステップ 2: 日付プロパティを追加する
```java
//日付プロパティ「xmp:Date1」値を追加
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## ステップ 3: 整数プロパティを追加する
```java
//整数プロパティ「xmp:Intg1」値を追加
xmp.put("xmp:Intg1", new XmpValue(111));
```
## ステップ 4: Double プロパティを追加する
```java
//double プロパティ「xmp:Double1」値を追加
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## ステップ 5: 文字列プロパティを追加する
```java
//文字列プロパティ「xmp:String1」値を追加
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## ステップ 6: ドキュメントを保存する
```java
//出力EPSファイルストリームを初期化する
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//変更された XMP メタデータを含むドキュメントを保存する
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## ステップ 7: ストリームを閉じる
```java
//入力 EPS ストリームを閉じる
psStream.close();
```
## 結論
Aspose.Page for Java は、EPS ファイル内の XMP メタデータを操作するプロセスを簡素化します。このステップバイステップのガイドに従うことで、簡単なプロパティを簡単に追加してドキュメントのメタデータを強化できます。
## よくある質問
### Aspose.Page for Java を他のプログラミング言語で使用できますか?
Aspose.Page は主に Java をサポートしていますが、.NET などの他の言語で利用できるバージョンもあります。
### Aspose.Page for Java の無料トライアルは利用できますか?
はい、無料トライアルを取得して、Aspose.Page の機能を探索できます。[ここ](https://releases.aspose.com/).
### Aspose.Page for Java の詳細なドキュメントはどこで見つけられますか?
ドキュメントは利用可能です[ここ](https://reference.aspose.com/page/java/).
### Aspose.Page for Java の一時ライセンスを取得するにはどうすればよいですか?
仮免許が取得できる[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java はどこで購入できますか?
製品を購入できます[ここ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
