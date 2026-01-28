---
date: 2026-01-28
description: Aspose.Page for .NET を使用して EPS を PNG に変換し、シームレスなドキュメント処理のためにメータード ライセンスを適用する方法を学びましょう。
linktitle: Apply Metered License
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET を使用して EPS を PNG に変換し、メータードライセンスを適用する
url: /ja/net/getting-started/apply-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# EPS を PNG に変換し、Aspose.Page for .NET でメーターライセンスを適用する方法

## Introduction

Aspose.Page for .NET の **EPS から PNG への変換** とメーターライセンスの適用により、機能を最大限に活用できます。このチュートリアルでは、EPS ファイルの読み込みから PNG 画像として保存するまでの手順をすべて解説し、評価版の透かしなしでドキュメントを効率的に処理できるようにします。

## Quick Answers
- **このチュートリアルで扱う内容は？** EPS ファイルを PNG 画像に変換し、Aspose.Page for .NET でメーターライセンスを適用する方法。  
- **ライセンスは必要ですか？** はい、本番環境で使用するにはメーターライセンスが必要です。  
- **対応している .NET バージョンは？** .NET Framework 4.5 以降、.NET Core 3.1 以降、.NET 5/6/7。  
- **実装にかかる時間は？** 基本的な変換で約 10〜15 分。  
- **Linux/macOS でも実行できますか？** もちろんです。Aspose.Page はクロスプラットフォームです。

## What is “convert EPS to PNG”?
EPS から PNG への変換とは、ベクターベースの Encapsulated PostScript (EPS) ファイルをビットマップ画像の PNG にラスタライズすることです。EPS をサポートしないウェブページやレポート、UI コンポーネントにグラフィックを表示・埋め込む際に便利です。

## Why use a metered license for EPS to image conversion?
メーターライセンスを使用すると、処理したページ数に応じて支払うだけで済むため、変動するワークロードに最適です。また、無料トライアルで表示される赤い評価バナーが除去され、エンドユーザーに対してクリーンな出力が提供できます。

## Prerequisites

手順に入る前に、以下の前提条件が整っていることを確認してください。

- 有効な Aspose.Page for .NET ライセンス: [purchase.aspose.com](https://purchase.aspose.com/buy) から取得できます。  
- Aspose.Page ライブラリがインストール済み: インストール手順は [documentation](https://reference.aspose.com/page/net/) を参照してください。  
- .NET 開発環境: マシンに動作する .NET 環境が構築されていることを確認してください。

## Import Namespaces

.NET プロジェクトで Aspose.Page の機能にアクセスするために、必要な名前空間をインポートします。

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## How to convert EPS to PNG with a metered license?

以下は、必要な手順をすべて網羅したステップバイステップガイドです。

### Step 1: Set Metered Public and Private Keys

`Aspose.Page.Metered` クラスを初期化し、メーターの公開キーとプライベートキーを設定します。`<type public key here>` と `<type private key here>` を実際のキーに置き換えてください。

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

### Step 2: Load EPS File and Create Document

EPS ファイルへのパスを指定し、ストリームで内容を読み取ります。その後、ストリームから `PsDocument` クラスのインスタンスを作成します。

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

### Step 3: Convert EPS to PNG Image

EPS ファイルを PNG 画像に変換するための `ImageDevice` を作成します。`ImageSaveOptions` を使用して画像として保存します。

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

### Step 4: Retrieve Image Bytes

画像バイト列を取得します。各バイト配列は 1 ページを表します。この例では 1 ページだけです。

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

### Step 5: Save Image Bytes to File

取得したバイト列をファイルに保存し、EPS から PNG への変換が正常に行われたことを確認します。

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

### Step 6: Verify Metered License

メーターライセンスが正しく適用されたか目視で確認します。結果画像に赤い評価メッセージが表示されていなければ、ライセンスは問題なく適用されています。

これで、メーターライセンスを使用した Aspose.Page for .NET のフル機能を活用できるようになりました！

## Common Issues and Solutions

| 問題 | 原因 | 対策 |
|------|------|------|
| 赤い評価バナーがまだ表示される | ライセンスが設定されていない、またはキーが間違っている | 公開キー/プライベートキーを再確認し、`SetMeteredKey` をドキュメント処理の前に呼び出す |
| 出力ファイルが作成されない | `dataDir` パスが間違っている、または書き込み権限がない | ディレクトリが存在するか確認し、アプリケーションに書き込み権限があることを確認 |
| 複数ページが保存されない | 最初のページだけを書き出している | `imagesBytes` をループし、各配列を別々の PNG ファイルとして書き出す |

## Frequently Asked Questions

**Q: CI/CD パイプラインでメーターライセンスを使用できますか？**  
A: はい。キーを環境変数などで安全に保管し、ビルドプロセス中に `SetMeteredKey` を呼び出すことができます。

**Q: PNG 変換時にカラープロファイルの保持はサポートされていますか？**  
A: PNG 出力は元のカラー情報を保持しますが、`ImageSaveOptions` でさらにカスタマイズ可能です。

**Q: EPS を他のラスタ形式（JPEG、BMP）に変換できますか？**  
A: もちろんです。`ImageSaveOptions` のフォーマットを目的の形式に変更すれば対応できます。

**Q: サポートされる最大 EPS ファイルサイズは？**  
A: Aspose.Page は大容量ファイルを処理できますが、画像解像度が高いほどメモリ使用量が増加します。非常に大きなドキュメントはページ単位で処理することを検討してください。

**Q: プログラムから EPS ファイルのページ数を取得する方法は？**  
A: `PsDocument` をロードした後、`document.PagesCount` を使用します。

## FAQ's

### Q1: Aspose.Page for .NET のメーターライセンスはどうやって取得しますか？

A1: 有効なライセンスは [purchase.aspose.com](https://purchase.aspose.com/buy) から取得してください。

### Q2: Aspose.Page for .NET のドキュメントはどこにありますか？

A2: 詳細なドキュメントは [Aspose.Page .NET](https://reference.aspose.com/page/net/) を参照してください。

### Q3: Aspose.Page のフォーラムやサポートはありますか？

A3: はい、[forum](https://forum.aspose.com/c/page/39) でコミュニティと交流し、支援を受けられます。

### Q4: 購入前に Aspose.Page for .NET を試すことはできますか？

A4: もちろんです！無料トライアルは [here](https://releases.aspose.com/) からアクセスできます。

### Q5: Aspose.Page for .NET の一時ライセンスはどう取得しますか？

A5: 一時ライセンスは [temporary license/](https://purchase.aspose.com/temporary-license/) から取得できます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

---

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}