---
date: 2026-01-12
description: Aspose.Page for .NET を使用して XPS ドキュメントを変更する方法を学び、シンプルなコード例で XPS ファイルにテキストを追加する方法を発見しましょう。
linktitle: Modify XPS Document
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET を使用して XPS ドキュメントを変更する
url: /ja/net/document-creation/modify-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用した XPS ドキュメントの変更

## はじめに

Aspose.Page for .NET を使用した **xps ドキュメントの変更方法** のステップバイステップガイドへようこそ。署名を挿入したり、透かしを追加したり、ページにカスタムテキストを配置したりする必要がある場合でも、このチュートリアルでは数分で XPS ドキュメントに **テキストを追加する方法** を正確に示します。コードの各行を詳しく解説し、なぜその手順が重要なのかを説明し、一般的な落とし穴を回避するためのヒントも提供します。

### クイック回答
- **このチュートリアルの対象は何ですか？** XPS ファイルの選択したページに署名テキスト（「Confirmed」）を追加します。  
- **必要なライブラリはどれですか？** Aspose.Page for .NET（最新バージョン）。  
- **ライセンスは必要ですか？** テスト用には一時ライセンスで動作しますが、本番環境ではフルライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **実装にどれくらい時間がかかりますか？** 基本的な署名挿入で約10分です。

## XPS ドキュメントの変更とは？

XPS（XML Paper Specification）は Microsoft の固定レイアウト文書形式で、PDF に似ています。XPS ドキュメントを変更するとは、ファイルを別の形式に変換せずに、テキスト、画像、図形などの視覚コンテンツをプログラムで変更することを意味します。Aspose.Page は、.NET コードから直接 XPS ファイルを編集できる豊富なオブジェクトモデルを提供します。

## なぜ Aspose.Page を使用して XPS ドキュメントを変更するのか？

* **フルコントロール** – ページ、グリフ、ブラシ、変換を低レベルで操作できます。  
* **外部依存なし** – 純粋な .NET ライブラリで、Office や Adobe コンポーネントは不要です。  
* **クロスプラットフォーム** – .NET Core 経由で Windows、Linux、macOS 上で動作します。  
* **高性能** – 大規模なドキュメントを効率的に処理し、先進的な組版をサポートします。

## 前提条件

- **Aspose.Page for .NET** – NuGet パッケージをインストールするか、公式ドキュメント **[here](https://reference.aspose.com/page/net/)** からライブラリをダウンロードしてください。  
- **入力 XPS ファイル** – **[Aspose releases page](https://releases.aspose.com/page/net/)** からサンプル XPS ドキュメント（例: `input1.xps`）を取得してください。  
- **作業ディレクトリ** – マシン上にフォルダーを作成し、入力および出力ファイルを保存します。そのフルパスをコード内の `dir` 変数に割り当てます。  
- **開発環境** – Visual Studio 2019/2022、.NET Framework 4.7.2 以降、または任意の .NET Core/5/6 プロジェクト。

すべての準備が整ったので、コードに入りましょう。

## 名前空間のインポート

.NET プロジェクトで、まず Aspose.Page に必要な名前空間をインポートします。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## 手順 1: XPS ドキュメント ストリームを開く

ソース XPS ファイルをストリームとして開き、ドキュメント全体を表す `XpsDocument` オブジェクトを作成します。

```csharp
// ExStart:3
// The path to the documents directory.
string dir = "Your Document Directory";
// Open a stream of XPS file
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // Create PS document from stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // Continue to the next step...
}
// ExEnd:3
```

*プロのコツ:* ストリームを `using` ブロックでラップして、ファイルハンドルが自動的に解放されるようにします。

## 手順 2: 署名テキストの作成

次に、署名グリフを描画するための単色ブラシを作成します。

```csharp
// ExStart:4
// Create fill of the signature text
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Continue to the next step...
// ExEnd:4
```

`Color.BlueViolet` は、ブランドに合わせた任意の `System.Drawing.Color` に変更できます。

## 手順 3: ページの定義と署名の追加

署名を付与するページを指定し、各ページにグリフを追加します。

```csharp
// ExStart:5
// Define pages where signature will be set
int[] pageNumbers = new int[] {1, 2, 3};

// For every defined page set signature "Confirmed" at coordinates x=650 and y=950
for (int i = 0; i < pageNumbers.Length; i++)
{
    // Define active page
    document.SelectActivePage(pageNumbers[i]);

    // Create glyphs object
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // Define fill for glyphs
    glyphs.Fill = textFill;
}
// Continue to the next step...
// ExEnd:5
```

*なぜこの座標か？* X と Y の値はポイント（1/72 インチ）で測定されます。ページレイアウト上でテキストを正確に配置できるように調整してください。

## 手順 4: XPS ドキュメントへの変更保存

最後に、変更したドキュメントをディスクに書き戻します。

```csharp
// ExStart:6
// Save changed XPS document
document.Save(dir + "input1_out.xps");
// ExEnd:6
```

新しいファイル `input1_out.xps` には、ページ 1‑3 に「Confirmed」署名が含まれています。

## よくある問題と解決策

| Issue | Cause | Solution |
|-------|-------|----------|
| **署名が表示されない** | 座標が間違っている、またはページが選択されていない | `SelectActivePage` が各ページで呼び出されていることを確認し、X/Y 値を調整してください。 |
| **`AddGlyphs` の例外** | サーバーにフォントがインストールされていない | 指定したフォント（例: Arial）が利用可能であることを確認するか、`document.AddFont` を使用してカスタムフォントを埋め込んでください。 |
| **出力ファイルが破損している** | ストリームが正しく閉じられていない | すべてのストリームで `using` 文を使用し、必要に応じて `document.Dispose()` を呼び出してください。 |
| **大きなファイルでのパフォーマンス低下** | ドキュメント全体をメモリに読み込んでいる | ページをバッチ処理するか、（新しいバージョンで利用可能な場合）`XpsLoadOptions` のストリーミングオプションを使用してください。 |

## よくある質問

**Q: Aspose.Page は最新の .NET フレームワークに対応していますか？**  
A: はい、Aspose.Page は定期的に更新され、.NET Framework 4.5+、.NET Core 3.1+、.NET 5、.NET 6 をサポートしています。

**Q: 追加するテキストのフォントやスタイルをカスタマイズできますか？**  
A: もちろんです。`AddGlyphs` のパラメータ（フォント名、サイズ、`FontStyle`）を変更してデザインに合わせてください。

**Q: XPS ファイルにサイズ制限はありますか？**  
A: Aspose.Page は大規模なドキュメントを処理できますが、ファイルサイズが大きくなるほどメモリ使用量も増加します。非常に大きなファイルの場合は、ページ単位で処理することを検討してください。

**Q: Aspose.Page の一時ライセンスはどこで取得できますか？**  
A: 一時ライセンスは **[here](https://purchase.aspose.com/temporary-license/)** から取得できます。

**Q: サポートやコミュニティはどこで利用できますか？**  
A: 質問や情報共有は **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** で行えます。

## 結論

このチュートリアルでは、Aspose.Page for .NET を使用して **xps ドキュメント** にカスタム署名テキストを追加する方法を示しました。これで、特定のページにテキスト、透かし、注釈などを自由に挿入できる基礎ができました。フォント、色、位置を変えてアプリケーションのブランディング要件に合わせ、さらに高度なグラフィックやレイアウト機能を活用してください。

---

**最終更新日:** 2026-01-12  
**テスト環境:** Aspose.Page 24.11 for .NET（執筆時点の最新バージョン）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}