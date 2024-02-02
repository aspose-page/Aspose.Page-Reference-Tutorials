---
title: Aspose.Page for .NET を使用して XPS ドキュメントに四角形を追加する
linktitle: XPS ドキュメントに四角形を追加
second_title: Aspose.Page .NET API
description: Aspose.Page for .NET を使用してドキュメント作成を強化します。このステップバイステップのチュートリアルで、XPS ドキュメントに四角形を追加する方法を学びます。
type: docs
weight: 13
url: /ja/net/drawing-shapes/add-rectangle-to-xps-document/
---
## 導入

Aspose.Page for .NET は、.NET アプリケーションで XPS (XML Paper Specification) ドキュメントを操作するためのさまざまな機能を提供する強力なライブラリです。このチュートリアルでは、Aspose.Page for .NET を使用して XPS ドキュメントに四角形を追加することに焦点を当てます。このステップバイステップのガイドに従って、ドキュメント作成プロセスを強化してください。

## 前提条件

このチュートリアルを始める前に、次の前提条件が満たされていることを確認してください。

1.  Aspose.Page for .NET ライブラリ: 開発環境に Aspose.Page for .NET ライブラリがインストールされていることを確認します。ダウンロードできます[ここ](https://releases.aspose.com/page/net/).

2. ドキュメント ディレクトリ: XPS ドキュメントを保存するディレクトリを設定します。

## 名前空間のインポート

.NET アプリケーションに、Aspose.Page 機能を使用するために必要な名前空間を含めます。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## ステップ 1: ドキュメント ディレクトリを設定する

```csharp
//例開始:3
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";
//拡張終了:3
```

## ステップ 2: 新しい XPS ドキュメントを作成する

```csharp
//例開始:4
//新しい XPS ドキュメントの作成
XpsDocument doc = new XpsDocument();
//拡張終了:4
```

## ステップ 3: 長方形を追加する

```csharp
//例開始:5
//左下の CMYK (青) 単色ストローク長方形
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
//拡張終了:5
```

## ステップ 4: ドキュメントを保存する

```csharp
//例開始:6
//結果の XPS ドキュメントを保存する
doc.Save(dataDir + "AddRectangleXPS_out.xps");
//拡張終了:6
```

おめでとう！ Aspose.Page for .NET を使用して XPS ドキュメントに四角形を追加することに成功しました。

## 結論

Aspose.Page for .NET はドキュメント操作タスクを簡素化し、開発者が XPS ドキュメントを簡単に作成および変更できるようにします。このステップバイステップのガイドでは、XPS ドキュメントに四角形を追加する方法を説明し、さらに詳しく調べるための強固な基盤を提供します。

## よくある質問

### Q1: Aspose.Page はすべての .NET アプリケーションと互換性がありますか?

A1: はい、Aspose.Page はすべての .NET アプリケーションとシームレスに動作するように設計されています。

### Q2: Aspose.Page for .NET のドキュメントはどこで見つけられますか?

 A2: ドキュメントは入手可能です[ここ](https://reference.aspose.com/page/net/).

### Q3: 購入する前に、Aspose.Page for .NET を無料で試用できますか?

 A3: はい、無料トライアルを利用できます。[ここ](https://releases.aspose.com/).

### Q4: Aspose.Page for .NET の一時ライセンスを取得するにはどうすればよいですか?

 A4: 訪問[このリンク](https://purchase.aspose.com/temporary-license/)仮免許を取得するためです。

### Q5: どこでコミュニティ サポートを求めたり、Aspose.Page for .NET に関連する質問をしたりできますか?

 A5: にアクセスしてください。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティサポートのために。