---
title: Javaを使用してXMPの名前付き値を変更する
linktitle: Javaを使用してXMPの名前付き値を変更する
second_title: Aspose.Page Java API
description: Aspose.Page for Java をご覧ください - ドキュメント処理を合理化するためのステップバイステップ ガイドを使用して、EPS ファイル内の XMP メタデータを簡単に変更します。
type: docs
weight: 16
url: /ja/java/xmp-metadata-manipulation/change-named-value/
---
ドキュメント操作の分野では、Aspose.Page for Java は強力なツールとして際立っており、開発者は EPS ファイル内の XMP メタデータをシームレスに操作できます。このステップバイステップのガイドでは、Aspose.Page for Java を使用して XMP の名前付き値を変更するプロセスについて説明します。詳細を掘り下げる前に、概要を説明して準備を整えましょう。
## 導入
Aspose.Page for Java は、EPS ファイルの操作と処理を容易にする堅牢な Java ライブラリです。これらのファイル内の XMP メタデータの処理に関しては、Aspose.Page は開発者に包括的な機能セットを提供します。このチュートリアルでは、XMP の名前付き値の変更に焦点を当て、ドキュメント処理機能を強化したいと考えている開発者に明確かつ簡潔なガイドを提供します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
1. Java 開発環境: マシン上に Java 開発環境がセットアップされていることを確認してください。
2.  Aspose.Page for Java ライブラリ: Aspose.Page for Java ライブラリをダウンロードしてプロジェクトに統合します。ライブラリと詳細なドキュメントを見つけることができます[ここ](https://reference.aspose.com/page/java/).
3. サンプル EPS ファイル: 実験用にサンプル EPS ファイルを用意します。お持ちでない場合は、提供されている「xmp4.eps」という名前のサンプル ファイルを使用できます。
## パッケージのインポート
プロセスを開始するには、必要なパッケージを Java コードにインポートします。これらのパッケージは、Aspose.Page for Java と対話するために不可欠です。 Java ファイルの先頭に次の行を含めます。
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
ここで、Aspose.Page for Java を使用して XMP の名前付き値を変更するプロセスを複数のステップに分けてみましょう。
## ステップ 1: 入力 EPS ファイル ストリームを初期化する
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
        
//入力EPSファイルストリームを初期化します
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```
## ステップ 2: PsDocument を初期化する
```java
PsDocument document = new PsDocument(psStream);
```
## ステップ 3: XMP メタデータを取得する
```java
//XMP メタデータを取得します。 EPS ファイルに XMP メタデータが含まれていない場合は、PS メタデータ コメント (%%Creator、%%CreateDate、%%Title など) からの値が埋め込まれた新しいファイルを取得します。
XmpMetadata xmp = document.getXmpMetadata();
```
## ステップ 4: XMP で新しい値を設定する
```java
//構造体「xmpTPg:MaxPageSize」の名前付き値「stDim:unit」に新しい文字列値「Inches」を設定します。
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```
## ステップ 5: 出力 EPS ファイル ストリームを初期化する
```java
//出力EPSファイルストリームを初期化する
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```
## ステップ 6: 変更された XMP メタデータを含むドキュメントを保存する
```java
//変更された XMP メタデータを含むドキュメントを保存する
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## ステップ 7: 入力 EPS ストリームを閉じる
```java
//入力 EPS ストリームを閉じる
psStream.close();
```
このステップバイステップのガイドでは、Aspose.Page for Java を使用して XMP の名前付き値を変更するための体系的なアプローチを保証します。以下の手順に従うことで、この機能を Java アプリケーションにシームレスに統合できます。
## 結論
結論として、Aspose.Page for Java は、EPS ファイル内の XMP メタデータを操作するプロセスを簡素化します。このチュートリアルでは、XMP の名前付き値を効率的に変更し、ドキュメント処理能力を強化するための知識を習得しました。
## よくある質問
### Aspose.Page for Java を他のプログラミング言語で使用できますか?
Aspose.Page は主に Java をサポートしますが、Aspose はさまざまなプログラミング言語に同様のライブラリを提供します。
### Aspose.Page for Java に利用できる無料トライアルはありますか?
はい、Aspose.Page for Java の無料トライアルを試すことができます。[ここ](https://releases.aspose.com/).
### Aspose.Page for Java に関する追加のサポートやディスカッションはどこで見つけられますか?
訪問[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティのサポートとディスカッションのために。
### Aspose.Page for Java の一時ライセンスを取得するにはどうすればよいですか?
仮免許を取得できます[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java はどこで購入できますか?
 Aspose.Page for Java を購入するには、次のサイトにアクセスしてください。[購入ページ](https://purchase.aspose.com/buy).