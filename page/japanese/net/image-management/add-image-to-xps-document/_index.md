---
title: Aspose.Page for .NET を使用して XPS ドキュメントに画像を追加する
linktitle: XPS ドキュメントに画像を追加
second_title: Aspose.Page .NET API
description: Aspose.Page for .NET を使用して、画像を XPS ドキュメントにシームレスに統合する方法を試してください。スムーズな開発体験を得るには、ステップバイステップのガイドに従ってください。
weight: 11
url: /ja/net/image-management/add-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用して XPS ドキュメントに画像を追加する

## 導入

.NET 開発の世界では、画像を XPS ドキュメントに組み込むことが一般的な要件です。 Aspose.Page for .NET はこのプロセスを簡素化し、XPS ドキュメントを簡単に操作および拡張するための強力なツールキットを提供します。このチュートリアルでは、Aspose.Page for .NET を使用して XPS ドキュメントに画像を追加する手順を説明します。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

1.  Aspose.Page for .NET ライブラリ: からライブラリをダウンロードしてインストールします。[Aspose.Page .NET ドキュメント](https://reference.aspose.com/page/net/).

2. 開発環境: Visual Studio などの .NET 開発環境をセットアップします。

3. サンプル画像: XPS ドキュメントに追加するサンプル画像ファイル (「QL_logo_color.tif」など) を用意します。

## 名前空間のインポート

まず、必要な名前空間を .NET プロジェクトにインポートします。これらの名前空間は、Aspose.Page for .NET が提供する機能を利用するために不可欠です。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## ステップ 1: ドキュメント ディレクトリを設定する

まず、ドキュメント ディレクトリへのパスを指定します。この手順により、プロジェクトがファイルの場所と保存場所を認識できるようになります。

```csharp
//例開始:1
string dataDir = "Your Document Directory";
//拡張終了:1
```

## ステップ 2: XPS ドキュメントの作成

Aspose.Page for .NET を使用して新しい XPS ドキュメントを作成します。

```csharp
//例開始:1
XpsDocument doc = new XpsDocument();
//拡張終了:1
```

## ステップ 3: XPS ドキュメントに画像を追加する

次に、画像を XPS ドキュメントに追加しましょう。この例では、「QL_logo_color.tif」という名前のサンプル画像を使用します。

```csharp
//例開始:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
//拡張終了:1
```

## ステップ 4: 結果の XPS ドキュメントを保存する

追加した画像を含む XPS ドキュメントを保存します。

```csharp
//例開始:1
doc.Save(dataDir + "AddImage_outXPS.xps");
//拡張終了:1
```

これで、Aspose.Page for .NET を使用して XPS ドキュメントに画像が正常に追加されました。

## 結論

このチュートリアルでは、Aspose.Page for .NET を利用して画像を XPS ドキュメントにシームレスに組み込む方法を検討しました。このステップバイステップのガイドは、スムーズな統合プロセスを保証し、.NET 開発能力を強化します。

## よくある質問

### Q1: Aspose.Page for .NET は、最新の .NET Framework バージョンと互換性がありますか?

 A1: Aspose.Page for .NET は、最新リリースを含む幅広い .NET Framework バージョンと互換性があるように設計されています。を参照してください。[ドキュメンテーション](https://reference.aspose.com/page/net/)具体的な詳細については。

### Q2: Windows 環境と Linux 環境の両方で Aspose.Page for .NET を使用できますか?

A2: はい、Aspose.Page for .NET はプラットフォームに依存しないため、Windows と Linux の両方の環境での使用に適しています。

### Q3: Aspose.Page for .NET のライセンス オプションはありますか?

 A3: はい、ライセンス オプションを調べて購入できます。[ここ](https://purchase.aspose.com/buy).

### Q4: Aspose.Page for .NET の無料トライアルはありますか?

 A4: はい、次のリンクにアクセスすると、Aspose.Page for .NET を無料で試すことができます。[無料トライアル](https://releases.aspose.com/).

### Q5: Aspose.Page for .NET のサポートを求めたり、コミュニティに参加したりできるのはどこですか?

 A5: にアクセスしてください。[Aspose.Page for .NET フォーラム](https://forum.aspose.com/c/page/39)コミュニティとつながり、サポートを受けることができます。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
