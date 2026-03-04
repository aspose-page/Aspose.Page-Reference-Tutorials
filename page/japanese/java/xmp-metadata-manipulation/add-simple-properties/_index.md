---
date: 2025-12-20
description: Aspose.Page for Java を使用して、EPS ファイルに XMP メタデータを作成する方法を学びます。シンプルな XMP
  プロパティをプログラムで追加するステップバイステップ ガイドです。
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: JavaでXMPメタデータEPSを作成する方法
url: /ja/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java を使用して XMP にシンプルなプロパティを追加する

## はじめに
最新のドキュメントワークフローでは、**XMP メタデータ EPS** ファイルをプログラムで作成できることにより、グラフィックの記述、検索、アーカイブ方法を完全にコントロールできます。Aspose.Page for Java を使用すれば、Java のエコシステムを離れることなく EPS ドキュメント内の XMP パケットを読み取り、変更し、書き込むことが可能です。このチュートリアルでは、EPS ファイルにシンプルな XMP プロパティを追加する手順を詳しく解説し、カスタムメタデータでグラフィックを迅速かつ確実に強化できるようにします。

## クイック回答
- **“create xmp metadata eps” とは何ですか？** XMP パケット（XML ベースのメタデータ）を EPS ファイルに追加することです。  
- **必要なライブラリは？** Aspose.Page for Java（Aspose のサイトからダウンロード可能）。  
- **テストにライセンスは必要ですか？** 開発には無料トライアルで十分です。商用利用には正式ライセンスが必要です。  
- **コード行数は？** Java のコードは 30 行未満（インポート文を含めても）。  
- **他のデータ型も追加できますか？** はい、日付、整数、倍精度実数、文字列、配列などがサポートされています。

## “create xmp metadata eps” とは？
XMP（Extensible Metadata Platform）は、ファイル内部にリッチなメタデータを埋め込むための標準です。**XMP メタデータ EPS を作成する** ことで、XML パケットを EPS（Encapsulated PostScript）ドキュメントに埋め込み、下流のアプリケーションが作者、作成日、カスタムタグなどの情報を取得できるようになります。

## EPS ファイルに XMP メタデータを追加するメリット
- **検索性:** DAM システムによる自動インデックスが可能になります。  
- **コンプライアンス:** 法的情報やライセンス情報をファイル内に直接保存できます。  
- **自動化:** 下流パイプラインが埋め込まれたデータに基づいて意思決定できます。  
- **ポータビリティ:** メタデータが EPS と共に搬送されるため、プラットフォーム間での一貫性が保たれます。

## 前提条件
開始する前に以下を用意してください。

- Java プログラミングの基本知識。  
- Aspose.Page for Java ライブラリのインストール。**[こちら](https://releases.aspose.com/page/java/)** からダウンロードできます。  
- メタデータを含むサンプル EPS ファイル。お持ちでない場合は、提供されている **`xmp3.eps`** ファイルをご利用ください。

## パッケージのインポート
まず、必要なクラスをインポートします。インポート文は元の例と全く同じです。

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

## 手順 1: EPS ドキュメントを読み込み XMP メタデータを取得
EPS ファイルを開き、`PsDocument` インスタンスを作成し、XMP パケットを取得（または作成）します。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## 手順 2: 日付プロパティを追加
日付は `Date` オブジェクトを作成し、XMP マップに格納するだけです。

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## 手順 3: 整数プロパティを追加
数値の識別子やバージョン番号などを整数値で保存できます。

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## 手順 4: 倍精度実数プロパティを追加
測定値や評価スコアなど、浮動小数点数が必要な場合に使用します。

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## 手順 5: 文字列プロパティを追加
プロジェクトコードなどのカスタムテキストタグは文字列として保存します。

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## 手順 6: 更新した EPS ファイルを保存
すべてのプロパティを追加したら、ドキュメントをディスクに書き戻します。

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 手順 7: リソースのクリーンアップ
ファイルハンドル漏れを防ぐため、必ず入力ストリームを閉じてください。

```java
// Close input EPS stream
psStream.close();
```

## よくある問題と解決策
| 問題 | 原因 | 対策 |
|------|------|------|
| **Null XMP メタデータ** | EPS に XMP パケットがなく、ライブラリが PS コメントを推測できなかった | ソース EPS に少なくとも 1 つの PS コメント（例: `%%Creator`）を含めてください。ライブラリは自動的に最小限の XMP パケットを生成します。 |
| **タイムゾーンの不一致** | 別アプリケーションで開くと日付がずれる | 手順 2 の前に `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` を設定してください。 |
| **ライセンス例外** | 実行時に `LicenseException` がスローされる | 有効な Aspose.Page ライセンスを適用するか、評価目的でトライアルモードで実行してください。 |

## 結論
本手順に従うことで、Aspose.Page for Java を使用して **XMP メタデータ EPS** ファイルを作成する方法が習得できました。日付、整数、倍精度実数、文字列といったシンプルなプロパティの追加は簡単で、結果として得られる EPS ファイルはリッチで検索可能なメタデータを保持し、下流のワークフロー全体に価値をもたらします。

## FAQ
### Aspose.Page for Java を他のプログラミング言語と併用できますか？
Aspose.Page は主に Java をサポートしていますが、.NET など他の言語向けのバージョンも提供されています。

### Aspose.Page for Java の無料トライアルはありますか？
はい、[こちら](https://releases.aspose.com/) から無料トライアルを取得して機能をお試しいただけます。

### Aspose.Page for Java の詳細ドキュメントはどこで確認できますか？
ドキュメントは [こちら](https://reference.aspose.com/page/java/) にあります。

### Aspose.Page for Java の一時ライセンスはどこで取得できますか？
一時ライセンスは [こちら](https://purchase.aspose.com/temporary-license/) から取得できます。

### Aspose.Page for Java の購入先はどこですか？
製品は [こちら](https://purchase.aspose.com/buy) から購入できます。

---

**最終更新日:** 2025-12-20  
**テスト環境:** Aspose.Page for Java 24.11（執筆時点の最新バージョン）  
**作成者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}