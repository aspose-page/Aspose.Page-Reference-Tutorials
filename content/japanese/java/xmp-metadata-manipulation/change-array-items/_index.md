---
title: Java を使用して XMP の配列項目を変更する
linktitle: Java を使用して XMP の配列項目を変更する
second_title: Aspose.Page Java API
description: Aspose.Page for Java を使用して XMP で配列項目を変更する方法を学習します。ステップバイステップのガイドを使用して、メタデータを簡単に変更します。 EPS ドキュメントを今すぐ強化してください。
type: docs
weight: 15
url: /ja/java/xmp-metadata-manipulation/change-array-items/
---
## 導入
Aspose.Page for Java を使用して XMP で配列項目を変更するための包括的なガイドへようこそ。 Aspose.Page は、EPS ファイル内の XMP メタデータをシームレスに操作できるようにする強力な Java ライブラリです。このチュートリアルでは、XMP メタデータ内の配列項目を変更するプロセスを説明し、EPS ドキュメントの強化とカスタマイズに役立ちます。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- Java Development Kit (JDK) がシステムにインストールされています。
-  Java 用の Aspose.Page ライブラリ。からダウンロードできます[ここ](https://releases.aspose.com/page/java/).
## パッケージのインポート
まず、必要なパッケージを Java プロジェクトにインポートしましょう。 Aspose.Page ライブラリがプロジェクトに含まれていることを確認してください。
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;

```
## ステップ 1: XMP メタデータを取得する
まず、EPS ファイルから XMP メタデータを取得します。 EPS ファイルにまだ XMP メタデータが含まれていない場合は、%%Creator、%%CreateDate、%%Title などの PS メタデータ コメントの値を使用して新しいファイルが作成されます。
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//入力EPSファイルストリームを初期化します
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// XMP メタデータを取得します。 EPS ファイルに XMP メタデータが含まれていない場合、新しいファイルには PS メタデータ コメントの値が埋め込まれます。
XmpMetadata xmp = document.getXmpMetadata();
```
## ステップ 2: 「dc:title」配列項目を設定する
ここで、「dc:title」配列項目のインデックス 0 に新しい値を設定しましょう。
```java
// 「dc:title」配列項目をインデックス 0 で設定します
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```
## ステップ 3: 「dc:creator」配列項目を設定する
同様に、「dc:creator」配列項目のインデックス 0 に新しい作成者の値を設定します。
```java
// 「dc:creator」配列項目をインデックス 0 で設定します
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```
## ステップ 4: 出力 EPS ファイル ストリームを初期化する
変更されたドキュメントが保存される出力 EPS ファイル ストリームを準備します。
```java
//出力EPSファイルストリームを初期化する
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
## ステップ 5: 変更された XMP メタデータを含むドキュメントを保存する
更新された XMP メタデータを含むドキュメントを保存します。
```java
//変更された XMP メタデータを含むドキュメントを保存する
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## 結論
おめでとう！ Aspose.Page for Java を使用して XMP で配列項目を変更する方法を学習しました。このチュートリアルでは、カスタマイズされたメタデータを使用して EPS ドキュメントを簡単に強化できるように、段階的なガイダンスを提供しました。

## よくある質問
### Aspose.Page for Java を他のプログラミング言語で使用できますか?
Aspose.Page は主に Java 用に設計されていますが、Aspose は他の言語用にも同様のライブラリを提供します。
### Aspose.Page for Java の詳細なドキュメントはどこで見つけられますか?
ドキュメントは利用可能です[ここ](https://reference.aspose.com/page/java/).
### Aspose.Page for Java に利用できる無料トライアルはありますか?
はい、無料トライアルを利用できます[ここ](https://releases.aspose.com/).
### Aspose.Page for Java の一時ライセンスを取得するにはどうすればよいですか?
仮免許が取得できる[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java のフルバージョンはどこで購入できますか?
フルバージョンを購入できます[ここ](https://purchase.aspose.com/buy).