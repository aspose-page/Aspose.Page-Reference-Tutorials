---
title: Java を使用して XMP の値を変更する
linktitle: Java を使用して XMP の値を変更する
second_title: Aspose.Page Java API
description: Aspose.Page for Java を使用して EPS ドキュメントを強化します。 XMP メタデータを簡単に変更して、カスタマイズされたプロフェッショナルなコンテンツを実現します。 #Java開発
type: docs
weight: 17
url: /ja/java/xmp-metadata-manipulation/change-values/
---
## 導入
ドキュメントの処理と操作の分野では、Aspose.Page for Java は強力なツールとして際立っています。このチュートリアルでは、Java と Aspose.Page ライブラリを使用して、EPS (Encapsulated PostScript) ドキュメント内の XMP (Extensible Metadata Platform) 値を変更するプロセスについて詳しく説明します。提供されるステップバイステップのガイドに従うことで、メタデータを簡単に変更して、ドキュメントを特定の要件に合わせて調整する方法を学びます。
## 前提条件
このチュートリアルを開始する前に、次の前提条件が満たされていることを確認してください。
1. Java 開発環境: マシン上に Java 開発環境が動作していることを確認してください。
2.  Aspose.Page for Java ライブラリ: Aspose.Page for Java ライブラリをダウンロードしてインストールします。必要なパッケージが見つかります[ここ](https://releases.aspose.com/page/java/).
## パッケージのインポート
まず、必要なパッケージを Java プロジェクトにインポートします。これらのパッケージは、EPS ドキュメントを操作したり操作したりするために不可欠です。
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
EPS ドキュメントから XMP メタデータを取得します。 EPS ファイルに XMP メタデータが含まれていない場合は、%%Creator、%%CreateDate、%%Title などの PS メタデータ コメントの値を使用して新しいファイルが作成されます。
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//入力EPSファイルストリームを初期化します
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// XMP メタデータを取得します。 EPS ファイルに XMP メタデータが含まれていない場合は、PS メタデータ コメントの値を使用して新しいファイルが作成されます
XmpMetadata xmp = document.getXmpMetadata();
```
## ステップ 2: 「ModifyDate」値を変更する
XMP メタデータの「ModifyDate」値を変更して、希望の日付を反映します。
```java
// 「ModifyDate」の値を変更する
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## ステップ 3: 「作成者」の値を変更する
XMP メタデータの「Creator」値を更新して、ドキュメントの作成者を指定します。
```java
// 「作成者」の値を変更する
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## ステップ 4: 「タイトル」値を変更する
XMP メタデータの「タイトル」値を変更して、ドキュメントに適切なタイトルを設定します。
```java
//「タイトル」の値を変更する
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## ステップ 5: 変更された XMP メタデータを含むドキュメントを保存する
更新された XMP メタデータを含むドキュメントを新しい EPS ファイルに保存します。
```java
//出力EPSファイルストリームを初期化する
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//変更された XMP メタデータを含むドキュメントを保存する
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## 結論
おめでとう！ Aspose.Page for Java を使用して、EPS ドキュメント内の XMP 値を変更するプロセスを正常にナビゲートできました。このチュートリアルでは、メタデータを変更して、ドキュメントを特定の要件にシームレスに適合させるための知識を習得しました。
## よくある質問
### Q: XMP 値を変更するときにタイムゾーンを考慮するにはどうすればよいですか?
利用する`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`タイムゾーン設定の一貫性を確保するため。
### Q: 1 回の操作で複数の XMP 値を変更できますか?
はい、を使用して、`put`希望する値ごとにメソッドを使用すると、複数の XMP 値を同時に変更できます。
### Q: Aspose.Page for Java の追加ドキュメントはどこで見つけられますか?
包括的なドキュメントを調べる[ここ](https://reference.aspose.com/page/java/).
### Q: Aspose.Page for Java の無料トライアルはありますか?
はい、無料トライアルにアクセスできます[ここ](https://releases.aspose.com/).
### Q: Aspose.Page for Java の一時ライセンスはどのように取得できますか?
仮免許を取得する[ここ](https://purchase.aspose.com/temporary-license/).