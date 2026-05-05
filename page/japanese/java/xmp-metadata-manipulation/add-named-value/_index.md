---
date: 2026-05-05
description: Aspose.Page for Java を使用して EPS ファイルに XMP の名前付き値を追加する方法を学ぶ – コード例付きのステップバイステップガイド。
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
linktitle: Java を使用して XMP に名前付き値を追加する
second_title: Aspose.Page Java API
title: Javaを使用してEPSファイルにXMPの名前付き値を追加する方法
url: /ja/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java を使用して XMP メタデータに名前付き値を追加する

## はじめに
現代の Java 開発において、EPS ファイル内に **XMP を追加する方法** のメタデータを学ぶことは、ドキュメントの出所を保持し、検索性を向上させるために不可欠です。**asp** (Aspose.Page for Java) を使用すれば、カスタムの名前付き値を XMP パケットに簡単に注入できます。このチュートリアルでは、コードスニペットを交えた正確な手順を順に解説するので、すぐに EPS ドキュメントに XMP メタデータを追加し始めることができます。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Page for Java (asp)  
- **対象となるファイルタイプは？** XMP メタデータを含む EPS ファイル  
- **主なユースケースは？** XMP にカスタムの名前付き値（例: ページサイズ制限）を追加する  
- **前提条件は？** JDK 8+ and the Aspose.Page for Java library  
- **実装にかかる目安の時間は？** 5〜10 minutes once the library is set up  

## asp とは何ですか？
*asp* は **Aspose** の略称で、ドキュメント処理を簡素化する .NET と Java の API ファミリーです。Aspose.Page for Java コンポーネントを使用すると、PostScript および EPS ファイルを作成、編集、変換でき、XMP を含むメタデータへの完全なプログラム的アクセスが提供されます。

## なぜ XMP メタデータに名前付き値を追加するのですか？
- **検索エンジンフレンドリー:** カスタムタグは発見性を向上させます。  
- **ワークフロー自動化:** 下流ツールはカスタム値を読み取り、意思決定に利用できます。  
- **コンプライアンス:** 規制情報をドキュメントパッケージに直接埋め込むことができます。  

## なぜ重要なのか
XMP に名前付き値を追加すると、EPS ファイル全体を解析せずに任意のキー‑バリュー ペアを保存でき、読み取ることができます。この機能は、メタデータが下流のアクションを駆動する自動出版パイプライン、デジタル資産管理システム、コンプライアンス主導のワークフローで特に有用です。

## 前提条件
始める前に、以下が揃っていることを確認してください：

- **Java Development Kit (JDK):** マシンにインストールされた最新の JDK（8 以上）。  
- **Aspose.Page for Java Library:** 公式の [download link](https://releases.aspose.com/page/java/) からダウンロードし、JAR をプロジェクトのクラスパスに追加してください。  
- **EPS ファイル**: XMP メタデータが既に含まれているか、または自動的に生成されるもの。  

## パッケージのインポート
まず必要な Java パッケージをインポートします。これらのインポートにより、ファイルストリーム、EPS ドキュメントモデル、XMP 処理クラスにアクセスできます。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Java を使用して EPS ファイルに XMP 名前付き値を追加する方法
以下は、EPS ドキュメントに **XMP を追加する方法** の名前付き値を正確に示す、簡潔な番号付き手順です。

### ステップ 1: 入力 EPS ファイルストリームの初期化
ソース EPS ファイルを `FileInputStream` にロードします。このストリームはドキュメントを Aspose の API に供給します。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **プロのヒント:** `dataDir` 変数を設定可能に保つことで、同じコードが環境間で動作します。

### ステップ 2: XMP メタデータの取得
既存の XMP パケットを取得します。EPS ファイルに XMP が無い場合、Aspose は PS コメントから生成された新しい XMP オブジェクトを作成します。

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### ステップ 3: 名前付き値の追加
XMP 構造にカスタムの名前付き値を挿入します。この例では `xmpTPg:MaxPageSize` 名前空間の下に新しいキーを追加します。

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **この重要性:** 名前付き値により、下流アプリケーションがドキュメント全体を解析せずに任意のキー‑バリュー ペアを保存・読み取ることができます。

### ステップ 4: 出力 EPS ファイルストリームの初期化
変更された EPS を保存するための `FileOutputStream` を用意します。

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### ステップ 5: ドキュメントの保存
変更を永続化します。`save` 呼び出しにより、更新された XMP パケットが EPS ファイルに書き戻されます。

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### ステップ 6: 入力 EPS ストリームのクローズ
リソースリークを防ぐために、元のファイルハンドルを解放します。

```java
psStream.close();
```

これらの 6 つのステップに従うことで、**asp** (Aspose.Page for Java) を使用して **XMP メタデータに名前付き値を追加** することに成功しました。

## 一般的な問題と解決策
| 問題 | 原因 | 対策 |
|-------|-------|-----|
| `xmp` 上の `NullPointerException` | EPS ファイルに XMP がなく、Aspose が生成できなかった | EPS に少なくとも 1 つの PS コメントが含まれていることを確認するか、手動で新しい `XmpMetadata` インスタンスを作成してください。 |
| 出力ファイルが空 | 出力ストリームがフラッシュまたはクローズされていない | `outPsStream.close()` が `finally` ブロックで呼び出されていることを確認してください（上記参照）。 |
| 重複キーエラー | 同じ名前付き値が二度追加された | 追加する前に `xmp.containsNamedValue(...)` でキーが既に存在するか確認してください。 |

## よくある質問

**Q: Aspose.Page for Java を他の Java ライブラリと併用できますか？**  
A: はい、Aspose.Page for Java は他の Java ライブラリとシームレスに連携できるよう設計されており、開発環境に柔軟性を提供します。

**Q: Aspose.Page for Java の無料トライアルは利用可能ですか？**  
A: はい、Aspose.Page for Java の無料トライアルは [here](https://releases.aspose.com/) からアクセスできます。

**Q: Aspose.Page for Java の一時ライセンスはどのように取得できますか？**  
A: Aspose.Page for Java の一時ライセンスは [this link](https://purchase.aspose.com/temporary-license/) から取得してください。

**Q: Aspose.Page for Java のチュートリアルやサンプルはどこで見つけられますか？**  
A: 包括的なチュートリアルとサンプルは [documentation](https://reference.aspose.com/page/java/) をご覧ください。

**Q: Aspose.Page for Java は大規模プロジェクトに適していますか？**  
A: はい、Aspose.Page for Java は大規模プロジェクトを効率的に処理できるよう設計されており、堅牢なドキュメント操作機能を提供します。

## 結論
このガイドでは、**asp** (Aspose.Page for Java) が EPS ファイル内の **XMP メタデータに名前付き値を追加** することをいかに簡単に行えるかを示しました。上記の手順に従うことで、ドキュメントにカスタムメタデータを付加し、検索性を向上させ、より賢い下流処理を実現できます。

---

**最終更新日:** 2026-05-05  
**テスト環境:** Aspose.Page for Java 24.12 (latest at time of writing)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}