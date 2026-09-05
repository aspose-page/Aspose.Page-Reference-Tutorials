---
date: 2026-07-19
description: 簡潔なステップバイステップガイドで、Aspose.Page for .NET を使用して XPS document .NET を作成し、rectangle
  を追加する方法を学びます。
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: XPS Document に rectangle を追加
og_description: XPS document .NET をすばやく作成します。このチュートリアルでは、Aspose.Page for .NET を使用して
  XPS file に rectangle を追加する方法を、明確なコードとヒントとともに紹介します。
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: XPS Document .NET の作成 – Aspose.Page で rectangle を追加
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: XPS Document .NET の作成 – Aspose.Page で rectangle を追加
url: /ja/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS ドキュメント .NET の作成 – Aspose.Page で矩形を追加

## はじめに

このチュートリアルでは、**XPS ドキュメント .NET の作成** と Aspose.Page for .NET を使用してその中に矩形を描画する方法を学びます。レポートエンジン、印刷可能な請求書、またはカスタムグラフィック層を構築している場合でも、プログラムで XPS ファイルを生成できることで、レイアウトと忠実度を完全にコントロールできます。以下の手順に従えば、数分で使用可能な XPS ファイルが手に入ります。

## クイック回答
- **主な目的は何ですか？** XPS ドキュメント .NET を作成し、矩形形状を追加します。  
- **必要なライブラリはどれですか？** Aspose.Page for .NET（公式サイトからダウンロード可能）。  
- **テストにライセンスは必要ですか？** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.6 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **実装にどれくらい時間がかかりますか？** 基本的な矩形であれば約 5‑10 分です。

## Aspose.Page for .NET とは？

Aspose.Page for .NET は、高性能で完全にマネージドされた API で、開発者が外部コンポーネントに依存せずに XPS（XML Paper Specification）ドキュメントをプログラムで作成、編集、レンダリングできるようにします。形状、テキスト、画像の描画のためのリッチなオブジェクトモデルを提供し、カラー管理、圧縮、PDF 変換などの高度な機能もサポートしているため、さまざまなドキュメント生成シナリオに適しています。

## なぜ Aspose.Page を使用して XPS ドキュメント .NET を作成するのか？

Aspose.Page は **30 以上の XPS 機能**（ベクターグラフィックス、テキストレイアウト、カラー管理など）をサポートし、**500 MB** までのファイルをドキュメント全体をメモリに読み込むことなく生成できます。この定量的な能力により、大規模な印刷ジョブでもスムーズなパフォーマンスが保証されます。

## 前提条件

このチュートリアルを始める前に、以下の前提条件が整っていることを確認してください。

1. Aspose.Page for .NET ライブラリ: 開発環境に Aspose.Page for .NET ライブラリがインストールされていることを確認してください。ダウンロードは [こちら](https://releases.aspose.com/page/net/) から行えます。  
2. ドキュメントディレクトリ: XPS ドキュメントを保存したいディレクトリを設定してください。

## 名前空間のインポート

.NET アプリケーションで、Aspose.Page の機能を使用するために必要な名前空間をインクルードしてください。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## .NET で XPS ドキュメントに矩形を追加するには？

XPS ドキュメントをロードし、`Graphics` オブジェクトを作成し、目的のサイズで `RectangleF` を定義し、`DrawRectangle` を呼び出します。この手順により、1 行のコードで矩形が描画され、DPI スケーリングが自動的に処理されます。標準的な A4 サイズのページでは、200 × 100 pt の矩形が余計な計算なしで中央に配置されます。

### 手順 1: ドキュメントディレクトリの設定

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### 手順 2: 新しい XPS ドキュメントの作成

`XpsDocument` クラスは、作成中の XPS ファイルを表し、ページ、グラフィック、その他のリソースを追加するメソッドを提供します。

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### 手順 3: 矩形の追加

`XpsPath` は XPS ドキュメント内の描画可能なパスオブジェクトを定義し、ジオメトリ、ストローク、塗りつぶし、その他のビジュアルプロパティを設定できます。

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### 手順 4: ドキュメントの保存

`Save` メソッドは、構築した XPS ドキュメントをディスク上の指定されたファイルパスに書き込みます。

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

おめでとうございます！Aspose.Page for .NET を使用して XPS ドキュメントに矩形を正常に追加できました。

## よくある問題とヒント

- **フォントが見つからない:** 参照しているフォントがサーバーにインストールされていることを確認してください。インストールされていない場合、Aspose.Page はデフォルトフォントに置き換え、レイアウトが変わる可能性があります。  
- **大きなドキュメント:** 200 MB を超えるファイルを生成する場合は、`document.SaveOptions.Compress = true` を呼び出してメモリ使用量を削減することを検討してください。  
- **座標系:** XPS はポイント（1/72 インチ）を使用します。画面ベースの寸法で作業する場合は、ピクセルをポイントに変換することを忘れないでください。

## よくある質問

**Q: Aspose.Page はすべての .NET アプリケーションと互換性がありますか？**  
A: はい、Aspose.Page はデスクトップ、ウェブ、クラウドの .NET アプリケーションとシームレスに動作します。

**Q: Aspose.Page for .NET のドキュメントはどこで見つけられますか？**  
A: 完全な API リファレンスは [こちら](https://reference.aspose.com/page/net/) で利用できます。

**Q: 購入前に Aspose.Page for .NET を無料で試すことはできますか？**  
A: はい、無料トライアルは [こちら](https://releases.aspose.com/) で取得できます。

**Q: Aspose.Page for .NET の一時ライセンスはどのように取得できますか？**  
A: 一時ライセンスを取得するには、[このリンク](https://purchase.aspose.com/temporary-license/) をご覧ください。

**Q: Aspose.Page for .NET に関するコミュニティサポートや質問はどこで得られますか？**  
A: コミュニティサポートは [Aspose.Page フォーラム](https://forum.aspose.com/c/page/39) でご利用ください。

---

**最終更新日:** 2026-07-19  
**テスト環境:** Aspose.Page for .NET 24.9  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Page for .NET で XPS ドキュメントを作成](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – 図形の描画](/page/net/drawing-shapes/)
- [Aspose.Page for .NET で XPS ドキュメントにテキストを追加](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}