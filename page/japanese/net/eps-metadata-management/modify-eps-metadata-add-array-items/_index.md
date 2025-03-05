---
title: Aspose.Page を使用して配列項目を追加する
linktitle: 配列項目の追加
second_title: Aspose.Page .NET API
description: Aspose.Page for .NET を使用して EPS ファイルに配列項目を追加する方法を調べます。シームレスなドキュメント操作については、ステップバイステップのガイドに従ってください。
type: docs
weight: 11
url: /ja/net/eps-metadata-management/modify-eps-metadata-add-array-items/
---
## 導入

.NET でのドキュメントの操作と処理の分野では、Aspose.Page は強力なツールとして際立っています。その多くの機能の中でも、EPS ファイル内の配列項目の処理は一般的な要件です。このチュートリアルでは、.NET 環境で Aspose.Page を使用して配列項目を追加するプロセスを段階的に説明します。経験豊富な開発者であっても、初心者であっても、このガイドではプロセスを明確かつ正確に説明します。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

- .NET プログラミングの基本的な理解。
-  Aspose.Page for .NET がインストールされています。そうでない場合は、からダウンロードできます[ここ](https://releases.aspose.com/page/net/).
- Visual Studio などのコード エディターで例を参照します。

## 名前空間のインポート

.NET プロジェクトでは、Aspose.Page 機能を利用するために必要な名前空間をインポートしてください。コードの先頭に次の行を追加します。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

これらの名前空間は、EPS ファイル操作に必要な必須のクラスとメソッドへのアクセスを提供します。

## ステップ 1: EPS ファイル入力ストリームを初期化する

```csharp
//例開始:3
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";
//EPS ファイル入力ストリームを初期化する
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//ストリームから PsDocument インスタンスを作成する
PsDocument document = new PsDocument(psStream);            
//拡張終了:3
```

ここでは、EPS ファイルの初期入力ストリームを設定し、`PsDocument`実例。

## ステップ 2: XMP メタデータを取得する

```csharp
//例開始:4
//XMP メタデータを取得します。 EPS ファイルに XMP メタデータが含まれていない場合は、PS メタデータ コメント (%%Creator、%%CreateDate、%%Title など) からの値が埋め込まれた新しいファイルを取得します。
XmpMetadata xmp = document.GetXmpMetadata();
//拡張終了:4
```

EPS ファイルから XMP メタデータを取得します。 EPS ファイルに XMP メタデータがない場合は、PS メタデータ コメントの値を使用して新しいファイルが作成されます。

## ステップ 3: XMP メタデータ値を変更する

```csharp
//例開始:5
//XMPメタデータ値を変更する

//もう一つタイトルを追加します。デフォルトでは配列の最後に追加されます。
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

//クリエイターをもう 1 人追加します。インデックス (0) によって配列に追加されます。
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
//拡張終了:5
```

新しいタイトルと作成者を配列に追加して、XMP メタデータを変更します。

## ステップ 4: 変更された XMP メタデータを含む EPS ファイルを保存する

```csharp
//例開始:6
//変更された XMP メタデータを含む EPS ファイルを保存する

//出力ストリームの作成
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    //EPSファイルを保存する
    document.Save(outPsStream);
}
//拡張終了:6
```

最後に、更新された XMP メタデータを含む EPS ファイルを保存します。配列項目に加えられた変更は、出力ファイルに反映されます。

## 結論

このチュートリアルで示すように、.NET で Aspose.Page を使用して配列項目を追加するのは簡単なプロセスです。適切な前提条件とステップバイステップのガイドを使用すると、開発者は EPS ファイルをシームレスに操作し、ドキュメントが特定のメタデータ要件を確実に満たすことができます。

## よくある質問

### Q1: Aspose.Page はすべての .NET 環境と互換性がありますか?

A1: はい、Aspose.Page はすべての .NET 環境でシームレスに動作するように設計されており、プラットフォーム間で一貫した機能を提供します。

### Q2: Aspose.Page は無料で使用できますか?

 A2: Aspose.Page は無料の試用版を提供しており、ユーザーはその機能を試すことができます。継続して使用するには、次からライセンスを購入する必要があります。[ここ](https://purchase.aspose.com/buy).

### Q3: Aspose.Page の一時ライセンスは利用できますか?

 A3: はい、一時ライセンスは次のサイトから取得できます。[ここ](https://purchase.aspose.com/temporary-license/)短期プロジェクトのニーズに対応します。

### Q4: Aspose.Page のコミュニティ サポートはどこで見つけられますか?

A4: コミュニティのディスカッションとサポートについては、次のサイトにアクセスしてください。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39).

### Q5: Aspose.Page for .NET の最新バージョンは何ですか?

 A5: 最新バージョンの Aspose.Page for .NET にアクセスするには、以下を参照してください。[ドキュメンテーション](https://reference.aspose.com/page/net/).