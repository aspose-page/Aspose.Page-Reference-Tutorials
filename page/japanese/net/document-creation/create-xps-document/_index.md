---
title: Aspose.Page for .NET を使用して XPS ドキュメントを作成する
linktitle: XPSドキュメントの作成
second_title: Aspose.Page .NET API
description: Aspose.Page for .NET を使用して XPS ドキュメント作成の世界を探索してください。ステップバイステップのガイドに従って、電子ドキュメントを簡単に生成します。
weight: 10
url: /ja/net/document-creation/create-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用して XPS ドキュメントを作成する

## 導入

Aspose.Page for .NET を使用して XPS ドキュメントを作成するためのステップバイステップ ガイドへようこそ。このチュートリアルでは、電子ドキュメントで広く使用されている形式である XPS ファイルを生成するプロセスについて説明します。経験豊富な開発者でも、Aspose.Page を使い始めたばかりでも、このガイドは明確な例と詳細な説明で XPS ドキュメントをシームレスに作成できるように調整されています。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

1.  Aspose.Page for .NET ライブラリ: Aspose.Page ライブラリを次の場所からダウンロードしてインストールします。[ダウンロードリンク](https://releases.aspose.com/page/net/).

2. ドキュメント ディレクトリ: 出力 XPS ファイルを保存するシステム上のディレクトリを選択または作成します。

それでは、チュートリアルに移りましょう!

## 名前空間のインポート

Aspose.Page for .NET を使用するには、必要な名前空間をプロジェクトにインポートする必要があります。次の手順を実行します：

### ステップ 1: Aspose.Page への参照を追加する

プロジェクトに、Aspose.Page for .NET ライブラリへの参照を追加します。必要な DLL は、ダウンロードしたパッケージ内にあります。

### ステップ 2: 名前空間をインポートする

コード ファイルに次の名前空間を含めます。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

前提条件を設定し、必要な名前空間をインポートしたので、XPS ドキュメントを作成するプロセスを複数のステップに分割してみましょう。

## ステップ 1: ドキュメント ディレクトリを設定する

```csharp
string dir = "Your Document Directory";
```

必ず交換してください`"Your Document Directory"`出力 XPS ファイルを保存する実際のパスに置き換えます。

## ステップ 2: XPS ドキュメントの作成

```csharp
XpsDocument xDocs = new XpsDocument();
```

を使用して新しい XPS ドキュメントを初期化します。`XpsDocument`クラス。

## ステップ 3: ドキュメントにグリフを追加する

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

使用`AddGlyphs`ドキュメントにグリフ (テキスト) を追加するメソッド。必要に応じて、フォント、サイズ、スタイル、位置をカスタマイズします。

## ステップ 4: グリフの塗りつぶしの色を設定する

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

追加したグリフの塗りつぶしの色を指定します。この例では黒を使用していますが、任意の色を選択できます。

## ステップ 5: 結果を保存する

```csharp
xDocs.Save(dir + "output.xps");
```

最後に、XPS ドキュメントを目的のファイル名で指定したディレクトリに保存します。結果の XPS ファイルには、「Hello World!」が含まれます。文章。

おめでとう！ Aspose.Page for .NET を使用して XPS ドキュメントが正常に作成されました。

## 結論

このチュートリアルでは、Aspose.Page for .NET を使用して XPS ドキュメントを作成するプロセスを説明しました。この強力なライブラリは、電子ドキュメントを簡単に生成するシームレスな方法を提供します。さまざまなフォント、スタイル、コンテンツを試して、特定のニーズに合わせて XPS ファイルを調整します。

## よくある質問

### Q1: XPS ドキュメントでカスタム フォントを使用できますか?

A1: はい、XPS ドキュメントにグリフを追加するときにフォント ファミリとサイズを指定できます。

### Q2: Aspose.Page は .NET Core と互換性がありますか?

A2: はい、Aspose.Page は .NET Core をサポートしているため、クロスプラットフォーム アプリケーションで使用できます。

### Q3: XPS ドキュメントに画像を追加するにはどうすればよいですか?

A3: Aspose.Page は、XPS ドキュメントに画像を追加するメソッドを提供します。詳細な例については、ドキュメントを参照してください。

### Q4: 複数ページの XPS ドキュメントを作成できますか?

A4：もちろんです！ Aspose.Page ライブラリを使用して、XPS ドキュメントに複数のページを追加できます。

### Q5: 体験版はありますか?

 A5: はい、Aspose.Page の機能を調べるには、[無料トライアル](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
