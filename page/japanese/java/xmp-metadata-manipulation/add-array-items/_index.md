---
date: 2026-03-05
description: Aspose.Page for Java を使用して EPS ファイルの XMP メタデータに dc:title 配列項目を追加する方法を学びましょう。迅速な結果を得るために、このステップバイステップ
  ガイドに従ってください。
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: JavaでXMPメタデータにdc:title配列項目を追加する方法
url: /ja/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java を使用した XMP メタデータへの配列項目の追加

## はじめに
このチュートリアルでは、Aspose.Page for Java を使用して EPS ファイル内の XMP メタデータに **dc:title**（およびその他の配列項目）を追加する方法を学びます。XMP メタデータの更新は、タイトル、作成者、キーワードなどの検索可能な情報をグラフィック ファイルに直接埋め込む必要がある場合に便利です。各ステップを順に説明し、各行が重要な理由を解説し、変更を検証する方法を示します。

## クイック回答
- **“dc:title” は何を表しますか？** XMP 配列として保存されている Dublin Core のタイトルプロパティです。  
- **なぜ XMP メタデータを変更するのですか？** 資産管理、検索性、標準への準拠が向上します。  
- **既存の XMP ブロックは必要ですか？** いいえ—不足している場合、Aspose.Page が PS コメントから自動生成します。  
- **どのライブラリ バージョンが必要ですか？** 最近の Aspose.Page for Java のリリースであればどれでも構いません（最新の 2026 ビルドでテスト済み）。  
- **他の配列プロパティも追加できますか？** はい—`dc:creator` のようなプロパティには同じ `addArrayItem` メソッドを使用します。

## 前提条件
本題に入る前に、以下が揃っていることを確認してください：

- Aspose.Page for Java ライブラリがインストールされていること（JAR をプロジェクトのクラスパスに追加）。  
- 基本的な Java 開発経験（JDK 8 以上推奨）。  
- XMP メタデータが既に含まれている、または少なくとも PS メタデータコメント（例：`%%Title`、`%%Creator`）がある EPS ファイル。

## パッケージのインポート
まず、EPS ファイルの読み取り、操作、保存に必要なクラスをインポートします：

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## ステップ 1: EPS ドキュメントをロードし XMP メタデータを取得する
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

ここでは EPS ファイルを開き、Aspose.Page に XMP ブロックを取得させます。ファイルに XMP が無い場合、ライブラリは既存の PS コメントを使用して自動的に作成し、常に操作できるメタデータ コンテナが確保されます。

## ステップ 2: 新しい **dc:title** 配列項目を追加する  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

この行は **dc:title の追加方法** を示しています。`"NewTitle"` を埋め込みたい実際のタイトルに置き換えてください。このメソッドは既存のタイトル配列に値を追加し、以前のタイトルを保持します。

## ステップ 3: 新しい **dc:creator** 配列項目を追加する  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

同様に、`dc:creator` プロパティを拡充できます。複数の作成者を保存でき、呼び出すたびに別のエントリが追加されます。

## ステップ 4: 出力ストリームの準備  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

変更後の EPS ファイル用にストリームを作成します。別のファイル名（`xmp3_changed.eps`）を使用することで、元のファイルはそのまま残ります。

## ステップ 5: 更新された XMP メタデータでドキュメントを保存する  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

`save` 呼び出しは更新された XMP ブロックと共に EPS データを書き込みます。`finally` ブロックは例外が発生した場合でもファイルハンドルが解放されることを保証します。

## なぜ重要なのか
正確な `dc:title` と `dc:creator` の値を埋め込むことで、以下が向上します：

- **検索性** デジタル資産管理（DAM）システムにおいて。  
- **コンプライアンス** メタデータを必要とする出版標準への適合。  
- **コラボレーション**、チームメンバーが EPS を開かずにファイル内容をすぐに把握できる。

## よくある落とし穴とヒント
- **落とし穴:** 既存の配列項目を意図せず上書きしてしまうこと。  
  **ヒント:** 新しい項目を追加する前に `xmp.getArrayItems("dc:title")` で現在の値を確認してください。  
- **落とし穴:** ストリームを閉じ忘れ、ファイルがロックされること。  
  **ヒント:** 例にあるように、I/O は常に try‑with‑resources または `finally` ブロックでラップしてください。  
- **ヒント:** �数の `addArrayItem` 呼び出しをチェーンして、一度に複数のタイトルや作成者を追加できます。

## Frequently Asked Questions

### Aspose.Page for Java を他のドキュメント形式でも使用できますか？
はい、Aspose.Page は EPS、PDF、XPS などさまざまなドキュメント形式をサポートしています。

### Aspose.Page for Java の無料トライアルはありますか？
はい、無料トライアルは[こちら](https://releases.aspose.com/)から利用できます。

### Aspose.Page for Java のドキュメントはどこで見つけられますか？
ドキュメントは[こちら](https://reference.aspose.com/page/java/)で入手できます。

### Aspose.Page for Java はどこで購入できますか？
製品は[こちら](https://purchase.aspose.com/buy)から購入できます。

### Aspose.Page for Java の一時ライセンスは利用可能ですか？
はい、一時ライセンスは[こちら](https://purchase.aspose.com/temporary-license/)で取得できます。

---

**最終更新日:** 2026-03-05  
**テスト環境:** Aspose.Page for Java（最新 2026 リリース）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}