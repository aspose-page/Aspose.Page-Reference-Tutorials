---
date: 2025-12-21
description: Aspose.Page XMP チュートリアル – Java 用 Aspose.Page を使用して EPS ファイルの XMP メタデータを変更する方法を、わかりやすくステップバイステップで学びましょう。
linktitle: Change Named Value in XMP using Java
second_title: Aspose.Page Java API
title: Aspose Page XMP チュートリアル – Java で XMP の名前付き値を変更する
url: /ja/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page XMP チュートリアル – Java を使用して XMP の名前付き値を変更する

モダンなドキュメントワークフローでは、**Aspose.Page for Java** を使用すると、EPS ファイル内の XMP メタデータの読み取り、編集、書き込みが簡単に行えます。この **aspose page xmp tutorial** では、XMP パケット内の名前付き値を変更する手順を説明します。これにより、ドキュメントのメタデータを正確かつ検索可能に保つことができます。ページサイズ、作者情報、カスタムタグの更新など、以下の手順で Java での具体的な方法を示します。

## クイック回答
- **このチュートリアルの対象は何ですか？** Aspose.Page for Java を使用して EPS ファイルの名前付き XMP 値を変更することです。  
- **どのライブラリバージョンが必要ですか？** 最近の Aspose.Page for Java リリースであればどれでも使用可能です（API は数年にわたり安定しています）。  
- **ライセンスは必要ですか？** 本番環境では一時ライセンスまたはフルライセンスが必要です。テスト目的であれば無料トライアルで動作します。  
- **実装にどれくらい時間がかかりますか？** Java I/O に慣れた開発者であれば約 10‑15 分です。  
- **他のファイル形式でも使用できますか？** XMP API は PDF、SVG など、Aspose.Page がサポートする他の形式でも利用可能です。

## XMP メタデータとは？

XMP（Extensible Metadata Platform）は、作成者、タイトル、カスタムプロパティなどのリッチなメタデータをファイル内部に直接埋め込むための標準化されたフォーマットです。EPS ドキュメントでは、XMP は従来の PostScript コメントと並存して存在し、ビジュアルコンテンツを変更せずにメタデータの読み取りや変更が可能です。

## なぜ Aspose.Page for Java を使用して XMP を編集するのか？

- **フルコントロール** – 生の XML を解析することなく、カスタム構造を含む任意の XMP プロパティにアクセスできます。  
- **クロスフォーマットの一貫性** – 同じ API が EPS、PDF、SVG で動作し、コード保守が容易になります。  
- **外部依存なし** – ネイティブコードや追加パーサーが不要な純粋な Java ライブラリです。  
- **堅牢なエラーハンドリング** – 組み込みのバリデーションにより、生成された EPS が標準準拠であることが保証されます。

## はじめに

Aspose.Page for Java は、EPS ファイルの操作と処理を支援する堅牢な Java ライブラリです。これらのファイル内で XMP メタデータを扱う際、Aspose.Page は開発者に包括的な機能セットを提供します。本チュートリアルでは、XMP の名前付き値を変更する方法に焦点を当て、ドキュメント処理機能を強化したい開発者向けに明確で簡潔なガイドを提供します。

## 前提条件

1. **Java 開発環境** – マシンに Java 開発環境が設定されていることを確認してください。  
2. **Aspose.Page for Java ライブラリ** – Aspose.Page for Java ライブラリをダウンロードし、プロジェクトに統合してください。ライブラリと詳細なドキュメントは[こちら](https://reference.aspose.com/page/java/)にあります。  
3. **サンプル EPS ファイル** – 実験用にサンプル EPS ファイルを用意してください。お持ちでない場合は、提供されている例のファイル **"xmp4.eps"** を使用できます。

## パッケージのインポート

プロセスを開始するには、Java コードで必要なパッケージをインポートします。これらのパッケージは Aspose.Page for Java とやり取りするために必須です。Java ファイルの冒頭に以下の行を追加してください。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

Now, let's break down the process of changing a named value in XMP using Aspose.Page for Java into multiple steps:

## 手順 1: 入力 EPS ファイルストリームの初期化
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## 手順 2: PsDocument の初期化
```java
PsDocument document = new PsDocument(psStream);
```

## 手順 3: XMP メタデータの取得
```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## 手順 4: XMP に新しい値を設定
```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## 手順 5: 出力 EPS ファイルストリームの初期化
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## 手順 6: 変更された XMP メタデータでドキュメントを保存
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 手順 7: 入力 EPS ストリームを閉じる
```java
// Close input EPS stream
psStream.close();
```

このステップバイステップガイドに従うことで、Aspose.Page for Java を使用した XMP の名前付き値の変更を体系的に実施できます。これらの手順を踏めば、Java アプリケーションにこの機能をシームレスに統合できます。

## よくある問題と解決策
- **FileNotFoundException** – `dataDir` が正しいフォルダーを指しており、`xmp4.eps` が存在することを確認してください。  
- **LicenseException** – ライセンスエラーが表示された場合は、`PsDocument` を作成する前に有効な Aspose.Page ライセンスファイルがロードされていることを確認してください。  
- **Metadata Not Updated** – 保存後、生成された EPS をメタデータビューア（例: Adobe Bridge）で開き、新しい値が表示されていることを確認してください。

## 結論

結論として、Aspose.Page for Java は EPS ファイル内の XMP メタデータ操作をシンプルにします。本チュートリアルにより、XMP の名前付き値を効率的に変更する方法を習得し、ドキュメント処理能力を向上させることができます。

## よくある質問
### Aspose.Page for Java を他のプログラミング言語で使用できますか？
Aspose.Page は主に Java をサポートしていますが、Aspose はさまざまなプログラミング言語向けに類似のライブラリを提供しています。

### Aspose.Page for Java の無料トライアルは利用できますか？
はい、Aspose.Page for Java の無料トライアルは[こちら](https://releases.aspose.com/)でお試しいただけます。

### Aspose.Page for Java に関する追加のサポートやディスカッションはどこで見つけられますか？
コミュニティサポートやディスカッションは[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)をご覧ください。

### Aspose.Page for Java の一時ライセンスはどのように取得できますか？
一時ライセンスは[こちら](https://purchase.aspose.com/temporary-license/)から取得できます。

### Aspose.Page for Java はどこで購入できますか？
Aspose.Page for Java を購入するには、[購入ページ](https://purchase.aspose.com/buy)をご覧ください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2025-12-21  
**テスト環境:** Aspose.Page for Java（最新リリース）  
**作者:** Aspose