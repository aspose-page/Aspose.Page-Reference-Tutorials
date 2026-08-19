---
date: 2026-03-03
description: Aspose.Page for .NET を使用して、カスタムページサイズを設定し、PostScript ドキュメントに 2 ページ目の
  PS ページを追加する方法を学びましょう。
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Aspose.Page を使用して PS ドキュメントのカスタムページサイズを設定する
url: /ja/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page を使用した PostScript (PS) ドキュメントへのページ追加

## はじめに

.NET 開発において、**カスタムページサイズの設定** と **2 ページ目の PS ページの追加** ができることは、生成された印刷物、レポート、グラフィックのレイアウトを細かく制御できることを意味します。Aspose.Page for .NET は、クリーンでオブジェクト指向の API を提供し、この作業をシンプルにします。このチュートリアルでは、マルチページの PS ファイルを作成し、各ページにカスタムサイズを定義し、結果を保存する方法を、数行の C# コードで学びます。

## クイック回答
- **カスタムページサイズを設定できますか？** はい – ページを開くときに幅と高さを渡すだけです。  
- **2 ページ目の PS ページはどうやって追加しますか？** `document.OpenPage(width, height)` を2回目に呼び出します。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **ライセンスは必要ですか？** テスト用の一時ライセンスで動作しますが、本番環境ではフルライセンスが必要です。  
- **Aspose.Page はどこからダウンロードできますか？** 以下の公式ダウンロードページから入手できます。

## 前提条件

チュートリアルに入る前に、以下の前提条件が整っていることを確認してください：

- .NET 開発の実務的な知識。  
- マシンに Visual Studio がインストールされていること。  
- Aspose.Page for .NET ライブラリ（[こちら](https://releases.aspose.com/page/net/) からダウンロード可能）。  
- テスト用の任意のドキュメントディレクトリ。

## 名前空間のインポート

プロジェクトで Aspose.Page が提供する機能にアクセスできるよう、必要な名前空間をインクルードしてください。上記の例では暗黙的に名前空間が含まれていますが、プロジェクト構成に応じて確認し、必要に応じて調整することが重要です。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 手順 1: プロジェクトのセットアップ

Visual Studio で新しい .NET プロジェクトを作成し、必要な設定を行ってください。プロジェクトに Aspose.Page ライブラリへの参照を追加することを忘れないでください。

## カスタムページサイズの設定と 2 ページ目の PS ページの追加

このセクションでは、各ページに対して **カスタムページサイズを設定** し、同じドキュメントに **2 ページ目の PS ページを追加** する方法を具体的に示します。

### 手順 2: ドキュメントの初期化

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### 手順 3: 最初のページを追加 (デフォルトサイズ)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### 手順 4: 異なる（カスタム）サイズで 2 ページ目を追加

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### 手順 5: ドキュメントを保存

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

これらの手順を正確に実行すれば、Aspose.Page for .NET を使用して PostScript ドキュメントに **カスタムページサイズを設定** し、 **2 ページ目の PS ページを追加** することに成功します。

## これが重要な理由

- **精密なレイアウト** – カスタムページ寸法により、プリンターの仕様に合わせたり、ユニークなパンフレット形式を作成できます。  
- **複数ページ** – 2 ページ目（またはそれ以上）を追加することで、外部の結合ツールを使わずにマルチページレポートが可能になります。  
- **クロスプラットフォーム** – 生成された PS ファイルは、PostScript 対応デバイスで表示でき、後で PDF に変換することもできます。

## よくある落とし穴とトラブルシューティング

- **パスが正しくない** – `dataDir` がパス区切り文字で終わっていることを確認するか、`Path.Combine` を使用してください。  
- **ライセンスの問題** – 有効なライセンスがない場合、ライブラリは透かしを追加したり、ページ数を制限したりすることがあります。  
- **単位の混乱** – 幅と高さはポイントで測定されます（1 ポイント = 1/72 インチ）。それに合わせて調整してください。

## よくある質問

**Q1: Aspose.Page は他のドキュメント形式と互換性がありますか？**  
A1: Aspose.Page は主に PostScript ドキュメントの操作に特化しています。他の形式については、目的に合わせた Aspose ライブラリをご検討ください。

**Q2: Aspose.Page でページサイズをカスタマイズできますか？**  
A2: もちろん可能です！チュートリアルで示したように、要件に応じて各ページのサイズを個別に指定できます。

**Q3: さらに多くのサンプルやドキュメントはどこで見つけられますか？**  
A3: 詳細情報や多数のサンプルは、[documentation](https://reference.aspose.com/page/net/) をご覧ください。

**Q4: Aspose.Page の一時ライセンスはどのように取得しますか？**  
A4: テスト目的の一時ライセンスは、[this link](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q5: コミュニティサポートや質問はどこで受けられますか？**  
A5: 他の開発者と交流し、経験を共有し、支援を求めるには、[Aspose.Page community forum](https://forum.aspose.com/c/page/39) に参加してください。

---

**最終更新日:** 2026-03-03  
**テスト環境:** Aspose.Page 24.11 for .NET  
**作成者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}