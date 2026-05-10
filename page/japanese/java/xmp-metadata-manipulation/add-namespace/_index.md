---
date: 2026-03-08
description: Aspose.Page for Java を使用して EPS ファイルに XMP 名前空間を追加する方法を学びましょう – XMP と XMP
  名前空間の追加方法をステップバイステップで解説した Java ガイド.
linktitle: Add Namespace in XMP using Java
second_title: Aspose.Page Java API
title: Aspose.Page を使用して EPS ファイルに XMP 名前空間を追加する方法 – Java チュートリアル
url: /ja/java/xmp-metadata-manipulation/add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page を使用して EPS ファイルに XMP 名前空間を追加する方法 – Java チュートリアル

EPS ファイルのメタデータを変更または拡張する必要がある場合、この **how to add xmp** チュートリアルでは、Java と Aspose.Page を使用して XMP 名前空間を追加する方法を正確に示します。ガイドの最後までに、任意の EPS ドキュメントにカスタムメタデータを注入するための再利用可能なパターンを手に入れることができます。

## Quick Answers
- **主な目的は何ですか？** EPS ファイルにカスタム XMP 名前空間とプロパティを追加することです。  
- **必要なライブラリはどれですか？** Aspose.Page for Java。  
- **テストにライセンスは必要ですか？** 開発には無料トライアルで動作しますが、製品版には商用ライセンスが必要です。  
- **必要なコード変更は何件ですか？** 各ステップごとに 1 つずつ、合計 5 つの短いコードスニペットだけです。  
- **このパターンを他の名前空間でも再利用できますか？** はい、`registerNamespaceURI` 呼び出しのプレフィックスと URI を変更するだけです。

## XMP 名前空間とは？

XMP (Extensible Metadata Platform) 名前空間は、関連するメタデータプロパティを共通の URI の下にまとめるための一意の識別子です。名前空間を登録することで、既存の標準と衝突することなく、独自のデータ（たとえば独自タグ）を保存できます。

## XMP 操作に Aspose.Page を使用する理由

- **Adobe ツール不要で** EPS および PDF のメタデータを完全に制御できます。  
- **自動作成**：XMP ブロックが存在しない場合、PS コメントに基づいて自動的に作成されます。  
- **クロスプラットフォームの Java サポート**により、既存のパイプラインへの統合が容易です。

## 前提条件

- Aspose.Page for Java：ライブラリがインストールされていることを確認してください。ダウンロードは[こちら](https://releases.aspose.com/page/java/)。
- Java 開発環境：システムに Java 環境をセットアップしてください。
- ドキュメントファイル：XMP メタデータを含む EPS ファイルを用意してください。XMP メタデータが無い場合、ライブラリは PS メタデータコメントに基づいて自動的に作成します。

## パッケージのインポート

まず、必要なパッケージを Java プロジェクトにインポートします。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## 手順 1: XMP メタデータの取得

```java

// The path to the documents directory.
String dataDir = "Your Document Directory";

// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, create a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

### なぜ重要か
`XmpMetadata` オブジェクトを取得すると、ドキュメントのメタデータへのライブハンドルが得られ、保存前に読み取り、変更、拡張が可能になります。

## 手順 2: 新しい名前空間の登録 *(how to add xmp namespace)*

```java
// Add new XML namespace "http://www.some.org/schema/tmp#" with prefix "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

### 説明
`registerNamespaceURI` メソッドは短いプレフィックス（`tmp`）を完全な URI にマッピングします。このステップは次の操作に必須で、XMP プロパティは登録済みの名前空間で修飾される必要があります。

## 手順 3: 新しいプロパティの追加

```java
// Add new property "tmp:newKey" in the new XML namespace
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

### 何が起きているか？
ここでは `tmp:newKey` というカスタムプロパティを作成し、値を `"NewValue"` に設定しています。キーと値はビジネスロジックに合わせて任意のものに置き換えられます。

## 手順 4: ドキュメントの保存

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

### ヒント
`save` 呼び出しは常に `try/finally` ブロック（または try‑with‑resources）でラップし、例外が発生しても出力ストリームが確実に閉じられるようにしてください。

## 手順 5: ストリームのクローズ

```java
// Close input EPS stream
psStream.close();
```

### ベストプラクティス
入力ストリームを閉じることでファイルハンドルが速やかに解放され、Windows システムでのファイルロック問題を防止します。

## よくある問題と解決策

| 問題 | 考えられる原因 | 対策 |
|------|----------------|------|
| 保存後に XMP ブロックが表示されない | 元の EPS に XMP がなく、コメントが不十分だった | EPS に標準的な PS コメント（`%%Creator`、`%%Title` など）を含めるか、名前空間を登録する前に空の `XmpMetadata` オブジェクトを手動で作成してください。 |
| `registerNamespaceURI` が例外をスローする | プレフィックスが既に使用されている | 一意なプレフィックスを選択するか、`xmp.getRegisteredNamespaces()` で既存の名前空間を確認してください。 |
| 保存したファイルが破損している | 出力ストリームがフラッシュされていない | `try‑with‑resources` を使用するか、クローズ前に明示的に `outPsStream.flush()` を呼び出してください。 |

## 結論

この **how to add xmp** チュートリアルに従うことで、Aspose.Page for Java を使用して EPS ファイルにカスタム名前空間とプロパティを追加する再利用可能な方法を習得しました。この機能により、ワークフロー識別子、独自タグ、下流システム向けの統合データなど、よりリッチなメタデータ戦略を実現できます。

## FAQ

### Aspose.Page for Java を他のプログラミング言語と併用できますか？

Aspose.Page は主に Java をサポートしていますが、.NET など他の言語向けのバージョンも提供されています。

### 無料トライアルは利用できますか？

はい、[こちら](https://releases.aspose.com/)で無料トライアルをご利用いただけます。

### 包括的なドキュメントはどこで見つけられますか？

ドキュメントは[こちら](https://reference.aspose.com/page/java/)をご参照ください。

### 一時ライセンスはどのように取得できますか？

一時ライセンスは[こちら](https://purchase.aspose.com/temporary-license/)から取得できます。

### Aspose.Page のコミュニティフォーラムはありますか？

はい、[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)でコミュニティに参加できます。

**最終更新日:** 2026-03-08  
**テスト環境:** Aspose.Page for Java 24.10（最新）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}