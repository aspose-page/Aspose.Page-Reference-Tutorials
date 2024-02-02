---
title: Aspose.Page for .NET を使用して名前付き値を変更する
linktitle: 名前付き値の変更
second_title: Aspose.Page .NET API
description: Aspose.Page for .NET を使用して EPS ファイル内の名前付き値を変更する方法を学習します。 XMP メタデータを簡単にカスタマイズして、カスタマイズされたドキュメント処理を実現します。
type: docs
weight: 16
url: /ja/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---
## 導入

ドキュメント処理の世界では、Aspose.Page for .NET は EPS ファイルを操作するための強力なツールとして際立っています。これが提供する重要な機能の 1 つは、XMP メタデータ内の名前付き値を変更する機能です。このチュートリアルでは、Aspose.Page for .NET を使用して名前付き値を変更するプロセスを説明し、特定のニーズに応じて EPS ファイルをカスタマイズできるようにします。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Page for .NET: Aspose.Page for .NET ライブラリがインストールされていることを確認します。そうでない場合は、ダウンロードできます[ここ](https://releases.aspose.com/page/net/).

- ドキュメント ディレクトリ: 名前付きの値の変更を実行できる、EPS ファイル用の指定されたディレクトリを用意します。

## 名前空間のインポート

.NET プロジェクトでは、Aspose.Page が提供する機能にアクセスするために必要な名前空間をインポートする必要があります。次の名前空間をコードに追加します。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

ここで、包括的な理解のためにコードを複数のステップに分割してみましょう。

## ステップ 1: EPS ファイル入力ストリームを初期化する

```csharp
//例開始:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
//拡張終了:1
```

このステップでは、変更する EPS ファイルの入力ストリームを設定します。 「Your Document Directory」をドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ 2: XMP メタデータを取得する

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

EPS ファイルから既存の XMP メタデータを取得します。 EPS ファイルに XMP メタデータが含まれていない場合は、PS メタデータ コメントの値を使用して新しいファイルが生成されます。

## ステップ 3: XMP メタデータ値を変更する

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

ここでは、「xmpTPg:MaxPageSize」構造内の 2 つの名前付き値を変更する方法を示します。これは、特定の要件に応じてカスタマイズできます。

## ステップ 4: 変更された XMP メタデータを含む EPS ファイルを保存する

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

変更した EPS ファイルを出力ストリームに保存します。ファイルには、XMP メタデータに加えられた変更が反映されます。

## 結論

このチュートリアルでは、Aspose.Page for .NET を利用して、EPS ファイルの XMP メタデータ内の名前付き値を変更する方法を学習しました。この機能により、特定の要件に合わせてドキュメントをカスタマイズおよび調整する可能性が広がります。

## よくある質問

### Q1: Aspose.Page for .NET を他のドキュメント形式で使用できますか?

A1: はい、Aspose.Page は EPS、XPS、PDF などのさまざまなドキュメント形式をサポートしています。

### Q2: Aspose.Page for .NET の試用版はありますか?

 A2: はい、無料トライアルにアクセスできます。[ここ](https://releases.aspose.com/).

### Q3: Aspose.Page for .NET に関するその他のドキュメントはどこで見つけられますか?

 A3: ドキュメントを参照してください。[ここ](https://reference.aspose.com/page/net/).

### Q4: Aspose.Page for .NET の一時ライセンスを取得するにはどうすればよいですか?

 A4: 仮免許は取得できます。[ここ](https://purchase.aspose.com/temporary-license/).

### Q5: Aspose.Page for .NET ユーザーはどのようなサポート オプションを利用できますか?

 A5: コミュニティフォーラムにアクセスしてください[ここ](https://forum.aspose.com/c/page/39)サポートとディスカッションのため。