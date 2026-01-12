---
date: 2026-01-12
description: Aspose.Page for .NET を使用して XPS ドキュメントを作成する方法を学びましょう – 高品質な電子文書を生成するステップバイステップガイドです。
linktitle: Create XPS Document
second_title: Aspose.Page .NET API
title: .NET 用 Aspose.Page で XPS ドキュメントを作成する
url: /ja/net/document-creation/create-xps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用した XPS ドキュメントの作成

## はじめに

Aspose.Page for .NET を使用して **XPS ドキュメントの作成方法** をステップバイステップでご紹介します。このチュートリアルでは、電子文書で広く使用されている XPS ファイルの生成プロセスを探ります。経験豊富な開発者でも、Aspose.Page を使い始めたばかりの方でも、このガイドは明確な例と詳細な説明で XPS ドキュメントをシームレスに作成できるように設計されています。

## クイック回答
- **必要なライブラリは？** Aspose.Page for .NET  
- **.NET Core で実行できますか？** はい、ライブラリは .NET Core および .NET 5/6 を完全にサポートしています  
- **コード行数は？** 基本的な XPS ファイルを生成するには 20 行未満です  
- **テストにライセンスは必要ですか？** 無料トライアルが利用可能です。製品版ではライセンスが必要です  
- **出力フォーマットは？** XPS (XML Paper Specification)  

## Aspose.Page for .NET を使用して XPS ドキュメントを作成する方法

以下に、コーディングを開始する前に必要なすべての情報と、簡潔な番号付きの手順を示します。

## 前提条件

チュートリアルに入る前に、以下の前提条件が整っていることを確認してください。

1. Aspose.Page for .NET ライブラリ: [ダウンロードリンク](https://releases.aspose.com/page/net/) から Aspose.Page ライブラリをダウンロードしてインストールします。

2. ドキュメントディレクトリ: 出力 XPS ファイルを保存したい場所にディレクトリを選択または作成します。

それでは、チュートリアルに進みましょう！

## 名前空間のインポート

Aspose.Page for .NET を使用するには、必要な名前空間をプロジェクトにインポートする必要があります。以下の手順に従ってください。

### ステップ 1: Aspose.Page への参照を追加

プロジェクトに Aspose.Page for .NET ライブラリへの参照を追加します。必要な DLL はダウンロードしたパッケージ内にあります。

### ステップ 2: 名前空間をインポート

コードファイルに以下の名前空間を含めます。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

前提条件の設定と必要な名前空間のインポートが完了したので、XPS ドキュメント作成プロセスを複数のステップに分解して説明します。

## ステップ 1: ドキュメントディレクトリの設定

```csharp
string dir = "Your Document Directory";
```

`"Your Document Directory"` を、出力 XPS ファイルを保存したい実際のパスに置き換えてください。

## ステップ 2: XPS ドキュメントの作成

```csharp
XpsDocument xDocs = new XpsDocument();
```

`XpsDocument` クラスを使用して新しい XPS ドキュメントを初期化します。

## ステップ 3: ドキュメントにグリフを追加

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

`AddGlyphs` メソッドを使用して、ドキュメントにグリフ（テキスト）を追加します。必要に応じてフォント、サイズ、スタイル、位置をカスタマイズしてください。

## ステップ 4: グリフの塗りつぶし色を設定

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

追加したグリフの塗りつぶし色を指定します。この例では黒を使用していますが、任意の色を選択できます。

## ステップ 5: 結果を保存

```csharp
xDocs.Save(dir + "output.xps");
```

最後に、指定したディレクトリに希望のファイル名で XPS ドキュメントを保存します。生成された XPS ファイルには "Hello World!" テキストが含まれます。

おめでとうございます！Aspose.Page for .NET を使用して XPS ドキュメントの作成に成功しました。

## 一般的なヒントと落とし穴

- **ディレクトリパス** – 異なる OS でパス区切り文字が欠落しないように、`Path.Combine(dir, "output.xps")` を使用します。  
- **フォントの可用性** – 指定したフォントはコードが実行されるマシンにインストールされている必要があります。インストールされていない場合、Aspose がデフォルトフォントに置き換えます。  
- **複数ページ** – 複数ページの XPS ファイルを作成するには、追加の `XpsPage` オブジェクトをインスタンス化し、保存前に各ページにコンテンツを追加します。

## 結論

このチュートリアルでは、Aspose.Page for .NET を使用して XPS ドキュメントを作成するプロセスを順に解説しました。この強力なライブラリは、電子文書を簡単に生成するシームレスな方法を提供します。さまざまなフォント、スタイル、コンテンツを試して、特定のニーズに合わせた XPS ファイルを作成してください。

## FAQ

### Q1: XPS ドキュメントでカスタムフォントを使用できますか？

A1: はい、XPS ドキュメントにグリフを追加する際にフォントファミリーとサイズを指定できます。

### Q2: Aspose.Page は .NET Core と互換性がありますか？

A2: はい、Aspose.Page は .NET Core をサポートしており、クロスプラットフォームアプリケーションで使用できます。

### Q3: XPS ドキュメントに画像を追加するには？

A3: Aspose.Page は XPS ドキュメントに画像を追加するメソッドを提供しています。詳細な例についてはドキュメントを参照してください。

### Q4: 複数ページの XPS ドキュメントを作成できますか？

A4: もちろんです！Aspose.Page ライブラリを使用して XPS ドキュメントに複数のページを追加できます。

### Q5: トライアル版は利用可能ですか？

A5: はい、[無料トライアル](https://releases.aspose.com/) をダウンロードして Aspose.Page の機能をお試しいただけます。

---

**最終更新日:** 2026-01-12  
**テスト環境:** Aspose.Page 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}