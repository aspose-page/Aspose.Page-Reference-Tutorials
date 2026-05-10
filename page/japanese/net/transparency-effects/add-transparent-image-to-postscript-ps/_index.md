---
date: 2026-03-26
description: Aspose.Page を使用して .NET で PostScript ドキュメントを作成し、透明画像を追加する方法を学びましょう。このステップバイステップ
  ガイドでは、前提条件、コード、ヒントを取り上げています。
linktitle: Add Transparent Image to PostScript (PS)
second_title: Aspose.Page .NET API
title: 透明画像付きPostScriptドキュメントを.NETで作成 (Aspose.Page)
url: /ja/net/transparency-effects/add-transparent-image-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 透明画像付き PostScript ドキュメントを .NET で作成する (Aspose.Page)

## Introduction

このチュートリアルでは、**PostScript ドキュメント .NET を作成**し、Aspose.Page for .NET を使用して透明 PNG を埋め込む方法を学びます。透明画像を追加することで、透かしやオーバーレイ、UI モックアップなど、レイヤー構造の豊かなグラフィックを構築できます。環境設定から不透明画像と透明画像の両方の描画まで、すべての手順を順を追って解説します。

## Quick Answers
- **What does Aspose.Page do?** Aspose.Page は何をするか？  
  .NET で PostScript (PS) および XPS ドキュメントを生成、編集、レンダリングするためのフル機能 API を提供します。  
- **Can I add transparent PNGs?** 透明 PNG を追加できますか？  
  はい — `DrawTransparentImage` を使用して不透明度を制御できます。  
- **Which .NET versions are supported?** 対応している .NET バージョンは？  
  最近の .NET Framework、.NET Core、.NET 5/6 のすべてのリリースをサポートしています。  
- **Do I need a license?** ライセンスは必要ですか？  
  無料トライアルで評価は可能ですが、本番環境ではライセンスが必要です。  
- **How long does implementation take?** 実装にかかる時間は？  
  基本的なサンプルでおおよそ 10‑15 分です。

## Prerequisites

開始する前に以下を用意してください。

- **Aspose.Page for .NET** – [download link](https://releases.aspose.com/page/net/) からダウンロード。  
- PS ドキュメントと埋め込む画像を保存するフォルダー。  
- 透明レイヤーとして使用する透過 PNG（例: `mask1.png`）。

## Import Namespaces

まず、必要なクラスが含まれる名前空間をインポートします。これにより、PS ドキュメントモデル、グラフィックユーティリティ、基本的な .NET 描画型にアクセスできます。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Set Up Your Document Directory

ソース画像と出力 PS ファイルが配置されるパスを定義します。プレースホルダーを実際のマシン上のパスに置き換えてください。

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Step 2: Create Output Stream for PostScript Document

生成した PS コンテンツを書き込むファイルストリームを作成します。このストリームは後で `PsDocument` コンストラクタに渡されます。

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTransparentImage_outPS.ps", FileMode.Create))
{
    // Your code for the next steps will go here.
}
```

## Step 3: Set Save Options and Background Color

`PsSaveOptions` を構成して、ファイルの保存方法を定義します。背景色を設定すると、透明要素の背後に固定されたキャンバスを持たせることができます。

```csharp
PsSaveOptions options = new PsSaveOptions();
options.BackgroundColor = Color.FromArgb(211, 8, 48);
```

## Step 4: Create a New 1‑Paged PS Document

上記で定義したストリームとオプションを使用してドキュメントを作成します。`false` フラグは Aspose.Page にストリームを自動的に閉じさせないよう指示します。

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 5: Write Graphics Save and Translate

描画を開始する前に、現在のグラフィック状態を保存し、原点を平行移動して画像がページ上の目的位置に表示されるようにします。

```csharp
document.WriteGraphicsSave();
document.Translate(20, 100);
```

## How to add transparent image to a PostScript document

### Step 6: Add Opaque RGB Image

まず、同じ PNG を通常の不透明画像として追加します。これにより、後で透明度を適用したときの視覚的な違いが分かります。

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 100, 0), Color.Empty);
}
```

### Step 7: Add Transparent Image

次に `DrawTransparentImage` を使用して PNG を不透明度付きで描画します。第 3 パラメータ（`255`）は完全不透明を表し、値を小さくすると透明度が高くなります。ここで **set image transparency .NET** を行います。

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawTransparentImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 350, 0), 255);
}
```

> **Pro tip:** 画像を 50 % 透明にしたい場合は、`255` の代わりに `128` を渡してください。

## Step 8: Write Graphics Restore and Close Page

描画が終わったら、以前のグラフィック状態を復元し、ページを閉じてコンテンツを確定させます。

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## Step 9: Save the Document

最後に PS ファイルをディスクに保存します。

```csharp
document.Save();
```

これらの手順に従うことで、**PostScript ドキュメント .NET を作成**し、不透明画像と透明画像の両方を含むファイルが完成します。これにより Aspose.Page を使用した **draw transparent image C#** の方法が示されました。

## Why use Aspose.Page for transparency effects?

- **Full control** over graphics state, matrices, and opacity levels.  
- **No external dependencies**—everything runs inside pure .NET code.  
- **Cross‑platform** support lets you generate PS files on Windows, Linux, or macOS.

## Common Pitfalls & Troubleshooting

| Issue | Solution |
|-------|----------|
| Image appears fully opaque even after `DrawTransparentImage` | Ensure the alpha value (third argument) is less than `255`. |
| PS file shows a blank page | Verify that the background color is set and that the stream path is correct. |
| Exception “File not found” | Double‑check `dataDir` and that `mask1.png` exists in that folder. |

## Frequently Asked Questions

**Q: Can I use other image formats besides PNG for transparency?**  
A: Yes—Aspose.Page supports PNG, GIF, and TIFF for transparent rendering.

**Q: Is Aspose.Page compatible with the latest .NET framework?**  
A: Absolutely. The library is regularly updated for .NET 6, .NET 7 and newer.

**Q: Can I apply transparency to an existing PS document?**  
A: Yes. Open the document with `PsDocument`, add a new page or modify an existing one, then use the same `DrawTransparentImage` approach.

**Q: What advantages does Aspose.Page offer over generic graphics libraries?**  
A: It is purpose‑built for PS/XPS, offering precise control over vector graphics, fonts, and image handling without needing a full rendering engine.

**Q: Are there limits to the transparency level I can set?**  
A: No. You can specify any alpha value from `0` (completely transparent) to `255` (fully opaque).

## Conclusion

本稿では **PostScript ドキュメント .NET を作成**し、Aspose.Page を使用して不透明画像と透明画像の両方を埋め込む方法を示しました。この手法により、プログラムから C# で高度なドキュメントレイアウト、透かし、レイヤードグラフィックを生成できるようになります。

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}