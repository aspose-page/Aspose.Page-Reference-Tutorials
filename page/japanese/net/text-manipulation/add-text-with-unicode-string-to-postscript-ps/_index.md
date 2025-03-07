---
title: Aspose.Page を使用して Unicode 文字列を含むテキストを PostScript (PS) に追加する
linktitle: Unicode 文字列を含むテキストを PostScript (PS) に追加する
second_title: Aspose.Page .NET API
description: Aspose.Page for .NET を使用して Unicode テキストを PostScript ファイルに追加する方法を学習します。ドキュメントの操作を簡単に強化します。
weight: 11
url: /ja/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page を使用して Unicode 文字列を含むテキストを PostScript (PS) に追加する

## 導入

ドキュメント操作の分野では、Aspose.Page for .NET は、開発者がさまざまなドキュメント形式を作成、編集、変換できるようにする堅牢なライブラリとして際立っています。その強力な機能の 1 つは、Unicode 文字列を使用してテキストを PostScript (PS) ファイルに追加できることです。このチュートリアルでは、Aspose.Page を使用する開発者にシームレスなエクスペリエンスを提供する、このタスクを実行するためのステップバイステップのガイドを学習します。

## 前提条件

チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。

- C# プログラミング言語に関する実践的な知識。
-  Aspose.Page for .NET ライブラリがインストールされています。からダウンロードできます。[Aspose.Page for .NET ドキュメント](https://reference.aspose.com/page/net/).
- 必要な構成が設定された開発環境。

## 名前空間のインポート

C# コードで、Aspose.Page for .NET 機能を使用するために必要な名前空間をインポートします。

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## ステップ 1: ドキュメント ディレクトリとフォント フォルダーをセットアップする

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## ステップ 2: PostScript ドキュメントの出力ストリームを作成する

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    //A4サイズで保存オプションを作成する
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    //... (追加のオプションはここで設定できます)
    
    //新しい 1 ページの PS ドキュメントを作成する
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (さらなる手順については以下で説明します)
    
    //文書を保存する
    document.Save();
}
```

## ステップ 3: カスタム フォントを使用して Unicode テキストを追加する

```csharp
string str = "試してみます.";  //Unicode テキスト
int fontSize = 48;

//テキストの塗りつぶしにカスタム フォントを使用する
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## ステップ 4: 現在のページを閉じる

```csharp
document.ClosePage();
```

## ステップ 5: ドキュメントを完成させて保存する

```csharp
document.Save();
```

## 結論

このチュートリアルでは、Aspose.Page for .NET を使用して Unicode テキストを PostScript ドキュメントに追加するプロセスを説明しました。開発者はその強力な機能を活用してドキュメント操作ワークフローを強化し、柔軟性と精度を確保できます。

## よくある質問

### Q1: Aspose.Page for .NET を他のプログラミング言語で使用できますか?

A1: Aspose.Page は主に .NET 用に設計されていますが、Java 用の他のバージョンも利用できます。

### Q2: Aspose.Page for .NET の一時ライセンスを取得するにはどうすればよいですか?

 A2: 訪問[仮免許](https://purchase.aspose.com/temporary-license/)仮免許取得のため。

### Q3: Aspose.Page についてのディスカッションのためのコミュニティ フォーラムはありますか?

 A3: はい、次のサイトにアクセスしてください。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティサポートのために。

### Q4: Aspose.Page for .NET はどのような形式に対応していますか?

A4: Aspose.Page は、XPS、PS、EPS、PDF などを含むさまざまな形式をサポートしています。

### Q5: 追加したテキストの外観をカスタマイズできますか?

A5: はい、Aspose.Page でテキストのフォント、サイズ、色、その他のプロパティをカスタマイズできます。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
