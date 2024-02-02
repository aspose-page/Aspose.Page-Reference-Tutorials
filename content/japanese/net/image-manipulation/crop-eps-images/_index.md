---
title: Aspose.Page for .NET を使用して EPS 画像をトリミングする
linktitle: EPS画像のトリミング
second_title: Aspose.Page .NET API
description: Aspose.Page を使用して、.NET での EPS 画像操作のシームレスな世界を探索してください。画像のトリミングやサイズ変更を簡単に行うことができ、素晴らしい結果が得られます。
type: docs
weight: 10
url: /ja/net/image-manipulation/crop-eps-images/
---
## 導入

.NET アプリケーションでの EPS 画像の操作に苦労していますか?これ以上探さない！このチュートリアルでは、強力な Aspose.Page for .NET ライブラリを使用して EPS 画像をトリミングするプロセスを説明します。経験豊富な開発者であっても、初心者であっても、このステップバイステップのガイドは、正確な画像トリミングを簡単に実現するのに役立ちます。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

- .NET 開発に関する実践的な知識。
-  Aspose.Page for .NET ライブラリがインストールされています。そうでない場合は、ダウンロードできます[ここ](https://releases.aspose.com/page/net/).
- サンプル EPS 画像 (コード内の「input.eps」を実際のファイルに置き換えます)。

## 名前空間のインポート

コードをスムーズに実行するために必要な名前空間をインポートすることから始めましょう。 

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

ここで、チュートリアルを複数のステップに分けてみましょう。

## ステップ 1: PsDocument を初期化する

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

を初期化します`PsDocument`オブジェクトと入力 EPS ストリーム。

## ステップ 2: 境界ボックスを抽出する

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

EPS 画像の初期境界ボックスを取得します。

## ステップ 3: 出力ストリームの作成

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

トリミングされた EPS 画像の出力ストリームを作成します。

## ステップ 4: 新しい境界ボックスを定義する

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

トリミング用の新しい境界ボックスを定義します。新しい値が最初の境界ボックス内にあることを確認してください。

## ステップ 5: 切り取って保存する

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

新しい境界ボックスを使用して EPS 画像をトリミングし、出力ストリームに保存します。

さまざまなサイズ変更シナリオに対してこれらの手順を繰り返します。

## EPS画像のサイズ変更

### インチ単位でサイズ変更

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

EPS 画像のサイズを変更し、インチ単位で指定した寸法で保存します。

### ミリメートル単位でサイズ変更

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

EPS 画像のサイズを変更し、指定した寸法 (ミリメートル単位) で保存します。

### サイズをパーセント単位で変更する

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

EPS 画像のサイズを変更し、パーセンテージで指定した寸法で保存します。

## 結論

おめでとう！ Aspose.Page for .NET を使用して EPS 画像をトリミングおよびサイズ変更する方法を学習しました。ここで、画像操作機能を強化し、.NET アプリケーションを次のレベルに引き上げましょう。

## よくある質問

### Q1: Aspose.Page for .NET を他の画像形式で使用できますか?

A1: Aspose.Page は主に EPS 画像に焦点を当てていますが、Aspose はさまざまな形式に対応するさまざまなライブラリを提供しています。特定の形式については、ドキュメントを確認してください。

### Q2: Aspose.Page for .NET の一時ライセンスを取得するにはどうすればよいですか?

 A2: 訪問[このリンク](https://purchase.aspose.com/temporary-license/)テスト用の一時ライセンスを取得します。

### Q3: Aspose.Page for .NET で処理できる画像サイズに制限はありますか?

A3: Aspose.Page は、さまざまなサイズの画像を処理できるように設計されています。ただし、パフォーマンスは画像の複雑さによって異なる場合があります。

### Q4: Aspose.Page についてディスカッションするためのコミュニティ フォーラムはありますか?

 A4: はい、Aspose.Page コミュニティに参加できます。[ここ](https://forum.aspose.com/c/page/39).

### Q5: Aspose.Page for .NET の詳細なドキュメントはどこで見つけられますか?

 A5: ドキュメントを参照してください。[ここ](https://reference.aspose.com/page/net/).