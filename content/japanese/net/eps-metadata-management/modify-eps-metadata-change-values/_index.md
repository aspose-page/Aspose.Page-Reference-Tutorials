---
title: Aspose.Page for .NET を使用して値を変更する
linktitle: 値の変更
second_title: Aspose.Page .NET API
description: Aspose.Page for .NET を使用して EPS ファイル操作をマスターします。 XMP メタデータ値を簡単に変更できます。
type: docs
weight: 17
url: /ja/net/eps-metadata-management/modify-eps-metadata-change-values/
---
## 導入

ドキュメント処理の動的な世界では、Aspose.Page for .NET は強力なツールとして際立っており、開発者に EPS ファイルを簡単に操作できる機能を提供します。このチュートリアルでは、Aspose.Page for .NET を使用して EPS ファイル内の値を変更するプロセスを詳しく説明します。経験豊富な開発者であっても、好奇心旺盛な初心者であっても、このステップバイステップのガイドでは、EPS ファイル内の XMP メタデータを効率的に変更するために必要なスキルを身につけることができます。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

### 1. .NET ライブラリの Aspose.Page

開発環境に Aspose.Page for .NET ライブラリがインストールされていることを確認してください。そうでない場合は、ダウンロードできます[ここ](https://releases.aspose.com/page/net/).

### 2. ドキュメントディレクトリ

ドキュメント用のディレクトリを設定します。これは、EPS ファイルが保存される場所になります。

前提条件を整理したので、次の重要な手順に進みましょう。

## 名前空間のインポート

どの .NET プロジェクトでも、Aspose.Page の機能を利用するために必要な名前空間をインポートすることが不可欠です。その方法は次のとおりです。

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
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";
//EPS ファイル入力ストリームを初期化する
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## ステップ 2: ストリームから PsDocument インスタンスを作成する

```csharp
//ストリームから PsDocument インスタンスを作成する
PsDocument document = new PsDocument(psStream);
```

準備が整ったので、チュートリアルの核心である EPS ファイル内の XMP メタデータ値の変更に進みましょう。

## ステップ 3: XMP メタデータを取得する

```csharp
//XMP メタデータを取得します。 EPS ファイルに XMP メタデータが含まれていない場合は、PS メタデータ コメント (%%Creator、%%CreateDate、%%Title など) からの値が埋め込まれた新しいファイルを取得します。
XmpMetadata xmp = document.GetXmpMetadata();
```

## ステップ 4: XMP メタデータ値を変更する

ここで、XMP メタデータのいくつかのキー値を変更しましょう。

### ステップ 4.1: ModifyDate 値を変更する

```csharp
//ModifyDate 値を変更する
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### ステップ 4.2: Creator の値を変更する

```csharp
//Creator の値を変更する
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### ステップ 4.3: タイトルの値を変更する

```csharp
//タイトルの値を変更する
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

これらの変更を加えたら、最後のステップ、つまり変更した EPS ファイルを保存する作業に進みましょう。

## ステップ 5: 変更された XMP メタデータを含む EPS ファイルを保存する

### ステップ 5.1: 出力ストリームの作成

```csharp
//出力ストリームの作成
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### ステップ 5.2: EPS ファイルを保存する

```csharp
//EPSファイルを保存する
document.Save(outPsStream);
```

最後に、入力ストリームを閉じます。

```csharp
finally
{
    psStream.Close();
}
```

おめでとう！ Aspose.Page for .NET を使用して、EPS ファイル内の XMP メタデータ値を正常に変更できました。

## 結論

このチュートリアルでは、Aspose.Page for .NET を使用して EPS ファイル内の値を変更するシームレスなプロセスを検討しました。開発者は、ドキュメントを効率的に操作するための強力なツールを自由に使えるようになりました。

## よくある質問

### Q1: Aspose.Page for .NET を他のファイル形式で使用できますか?

A1: Aspose.Page は主に EPS ファイルの操作に重点を置いています。他の形式については、Aspose のさまざまな製品をご覧ください。

### Q2: 体験版はありますか?

 A2: はい、利用可能な無料トライアルで Aspose.Page for .NET を試すことができます。[ここ](https://releases.aspose.com/).

### Q3: 詳細なドキュメントはどこで入手できますか?

 A3: 包括的なドキュメントが見つかります。[ここ](https://reference.aspose.com/page/net/).

### Q4: 仮免許はどのように取得すればよいですか?

 A4: 仮免許は取得できます。[ここ](https://purchase.aspose.com/temporary-license/).

### Q5: Aspose.Page for .NET を購入できますか?

 A5：もちろんです！購入ページにアクセスする[ここ](https://purchase.aspose.com/buy)ライセンスオプションについては、