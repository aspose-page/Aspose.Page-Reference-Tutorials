---
title: Aspose.Page for .NET を使用して単純なプロパティを追加する
linktitle: 単純なプロパティの追加
second_title: Aspose.Page .NET API
description: Aspose.Page for .NET を使用して EPS ファイルを拡張します。カスタマイズされたドキュメントのメタデータに簡単なプロパティを簡単に追加できます。
weight: 14
url: /ja/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用して単純なプロパティを追加する

## 導入

ドキュメントの操作と拡張の分野では、Aspose.Page for .NET が強力なツールとして登場し、開発者に EPS ファイル内の XMP メタデータをシームレスに追加および変更する機能を提供します。このチュートリアルでは、Aspose.Page for .NET を使用して単純なプロパティを EPS ファイルに追加するプロセスを説明します。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

1.  Aspose.Page for .NET: 開発環境に Aspose.Page for .NET がインストールされていることを確認します。そうでない場合は、ダウンロードできます[ここ](https://releases.aspose.com/page/net/).

2. ドキュメント ディレクトリ: EPS ファイルを保存するディレクトリを設定します。を更新します`dataDir`提供されたコード スニペット内の変数をドキュメント ディレクトリへのパスに置き換えます。

## 名前空間のインポート

まず、Aspose.Page for .NET との通信を可能にするために必要な名前空間をインポートします。コード ファイルの先頭に次の行を追加します。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## ステップ 1: EPS ファイル入力ストリームを初期化する

```csharp
//例開始:1
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";
//EPS ファイル入力ストリームを初期化する
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//ストリームから PsDocument インスタンスを作成する
PsDocument document = new PsDocument(psStream);
```

## ステップ 2: XMP メタデータを取得する

```csharp
//XMP メタデータを取得します。 EPS ファイルに XMP メタデータが含まれていない場合は、PS メタデータ コメント (%%Creator、%%CreateDate、%%Title など) からの値が埋め込まれた新しいファイルを取得します。
XmpMetadata xmp = document.GetXmpMetadata();
```

## ステップ 3: XMP メタデータ値を変更する

```csharp
//XMPメタデータ値を変更する
DateTime now = DateTime.UtcNow;

//整数プロパティを追加
xmp.Add("xmp:Intg1", new XmpValue(111));

//DateTime プロパティを追加
xmp.Add("xmp:Date1", new XmpValue(now));

//Double プロパティを追加
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//文字列プロパティを追加
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## ステップ 4: 変更された XMP メタデータを含む EPS ファイルを保存する

```csharp
//変更された XMP メタデータを含む EPS ファイルを保存する

//出力ストリームの作成
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    //EPSファイルを保存する
    document.Save(outPsStream);
}
```

## ステップ 5: FileStream を閉じる

```csharp
finally
{
    psStream.Close();
}
```

これらの手順に従うと、Aspose.Page for .NET を使用して簡単なプロパティを EPS ファイルに簡単に組み込むことができます。

## 結論

結論として、Aspose.Page for .NET は、カスタム XMP メタデータで EPS ファイルを強化しようとしている開発者にとって、非常に貴重な資産であることがわかります。単純なプロパティを追加することで、特定の要件を満たすようにドキュメントをカスタマイズおよび強化することができ、ドキュメント操作の可能性が広がります。

## よくある質問

### Q1: Aspose.Page for .NET はすべての EPS ファイルと互換性がありますか?

A1: Aspose.Page for .NET は、幅広い EPS ファイルをサポートしています。ただし、互換性は個々のファイルの複雑さと構造によって異なる場合があります。

### Q2: Aspose.Page for .NET を使用して既存の XMP メタデータを変更できますか?

A2: もちろんです！このチュートリアルで説明したように、既存の XMP メタデータ値を簡単に変更したり、ニーズに合わせて新しい値を追加したりできます。

### Q3: 追加できるプロパティの種類に制限はありますか?

A3: Aspose.Page for .NET は、整数、日付、倍精度浮動小数点数、文字列など、プロパティのさまざまなデータ型をサポートしています。メタデータに適切なタイプを柔軟に選択できます。

### Q4: Aspose.Page for .NET のテクニカル サポートを受けるにはどうすればよいですか?

 A4: 技術的なサポートについては、次のサイトにアクセスしてください。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)または、[ドキュメンテーション](https://reference.aspose.com/page/net/)総合的な指導を行います。

### Q5: Aspose.Page for .NET の無料トライアルはありますか?

 A5: はい、無料トライアルにアクセスできます。[ここ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
