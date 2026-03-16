---
date: 2026-03-16
description: Aspose.Page を使用して .NET で EPS 画像をトリミングし、EPS 画像ファイルのサイズを変更する方法を学びましょう。ステップバイステップのガイドに従って、簡単に
  EPS をトリミングし、サイズ変更できます。
linktitle: Crop EPS Images
second_title: Aspose.Page .NET API
title: .NET 用 Aspose.Page で EPS 画像をトリミングする方法
url: /ja/net/image-manipulation/crop-eps-images/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用した EPS 画像のトリミング方法

## はじめに

.NET アプリケーションで **EPS をトリミングする方法** を知りたい場合は、ここが適切な場所です。このチュートリアルでは、強力な Aspose.Page for .NET ライブラリを使用して EPS ファイルのトリミングとリサイズの手順を解説します。レポートツールを磨く場合でも、Web サービス用のグラフィックを準備する場合でも、この技術をマスターすれば時間を節約でき、ピクセル単位で完璧な結果が得られます。

## クイック回答
- **EPS のトリミングを処理するライブラリは何ですか？** Aspose.Page for .NET  
- **主なメソッドは？** `doc.CropEps(outputStream, newBoundingBox)`  
- **EPS をリサイズすることもできますか？** はい – `ResizeEps` を使用し、インチ、ミリメートル、またはパーセントで指定します。  
- **前提条件は？** .NET (Framework 4.5+ / .NET Core 3.1+)、Aspose.Page がインストール済み、EPS ファイル。  
- **一般的な実装時間は？** 基本的なトリミングとリサイズのワークフローで約10分です。

## 前提条件

コードに取り掛かる前に、以下が揃っていることを確認してください：

- .NET 開発の実務的な知識  
- Aspose.Page for .NET ライブラリがインストール済み。未インストールの場合は、[here](https://releases.aspose.com/page/net/) からダウンロードできます。  
- サンプル EPS 画像（コード中の `"input.eps"` を実際のファイル名に置き換えてください）

## 名前空間のインポート

EPS 処理クラスにアクセスできる名前空間をインポートしましょう。

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## EPS 画像のトリミング – ステップバイステップガイド

### 手順 1: `PsDocument` の初期化

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

`PsDocument` インスタンスを入力 EPS ストリームから作成します。このオブジェクトはメモリ上の EPS ファイルを表し、トリミングやリサイズのメソッドにアクセスできます。

### 手順 2: 元のバウンディングボックスを抽出

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

バウンディングボックスは EPS キャンバスの現在の寸法を示します。これらの値を把握することで、安全なトリミング矩形を定義できます。

### 手順 3: 出力ストリームの作成

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

トリミングされた EPS を保存する書き込み可能なストリームを開きます。`using` ブロックを使用することで、ストリームが適切にクローズされることが保証されます。

### 手順 4: 新しいバウンディングボックスの定義

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

数値を保持したい座標に置き換えてください。新しい値が元のバウンディングボックス内に収まっていることを確認してください。範囲外だと操作は失敗します。

### 手順 5: EPS のトリミングと保存

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

この1行でトリミングを実行し、結果を `output_crop.eps` に書き込みます。このメソッドはメモリ内のドキュメントを変更するため、必要に応じてさらに操作をチェーンできます。

## EPS 画像のリサイズ

トリミング後、表示や印刷のために EPS のサイズを変更したくなることがよくあります。Aspose.Page は 3 つの測定単位をサポートしています。

### インチ単位でリサイズ

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

### ミリメートル単位でリサイズ

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

### パーセント単位でリサイズ

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

各呼び出しは前の出力を上書きするため、サイズごとに別々のファイルが必要な場合は新しいストリームを作成してください。

## よくある問題とトラブルシューティング

| 症状 | 考えられる原因 | 対策 |
|------|----------------|------|
| **バウンディングボックスの値が範囲外** | 新しいボックスが元の寸法を超えている | `initialBoundingBox` の値を確認し、その範囲内の座標を選択してください。 |
| **出力ファイルが空** | 出力ストリームがフラッシュまたはクローズされていない | `using` ブロックが完了してからファイルにアクセスするか、`outputEpsStream.Flush()` を呼び出してください。 |
| **予期しないスケーリング** | 単位が混在している（例: インチとミリメートル） | サイズ値に合わせた正しい `Units` 列挙体を常に指定してください。 |

## FAQ

### Q1: Aspose.Page for .NET を他の画像形式で使用できますか？

A1: Aspose.Page は主に EPS 画像に焦点を当てていますが、Aspose はさまざまな形式向けに複数のライブラリを提供しています。特定の形式についてはドキュメントをご確認ください。

### Q2: Aspose.Page for .NET の一時ライセンスを取得するには？

A2: テスト用の一時ライセンスを取得するには、[this link](https://purchase.aspose.com/temporary-license/) にアクセスしてください。

### Q3: Aspose.Page for .NET で処理できる画像サイズに制限はありますか？

A3: Aspose.Page はさまざまなサイズの画像を処理できるよう設計されていますが、画像の複雑さに応じてパフォーマンスが変わることがあります。

### Q4: Aspose.Page のディスカッション用コミュニティフォーラムはありますか？

A5: はい、Aspose.Page コミュニティに [here](https://forum.aspose.com/c/page/39) で参加できます。

### Q5: Aspose.Page for .NET の詳細なドキュメントはどこで見つけられますか？

A5: ドキュメントは [here](https://reference.aspose.com/page/net/) を参照してください。

---

**最終更新日:** 2026-03-16  
**テスト環境:** Aspose.Page 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}