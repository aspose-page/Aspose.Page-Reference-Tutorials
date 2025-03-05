---
title: Aspose.Page for .NET を使用した変換 PS
linktitle: 変換PS
second_title: Aspose.Page .NET API
description: PostScript 変換に関するこの包括的なガイドを使用して、Aspose.Page for .NET の可能性を解き放ちます。ダイナミックなグラフィックスを簡単に作成できます。
type: docs
weight: 12
url: /ja/net/canvas-manipulation/transformationsps/
---
## 導入

Aspose.Page for .NET の世界へようこそ。ここでは、PostScript ドキュメントの変換の力を解き放つことができます。このチュートリアルでは、移動、スケーリング、回転、せん断、複雑な変換などのさまざまな変換をガイドし、視覚的に魅力的でダイナミックなグラフィックスを作成できるようにします。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Page for .NET ライブラリ: Aspose.Page for .NET ライブラリがプロジェクトに統合されていることを確認します。からダウンロードできます。[ダウンロードリンク](https://releases.aspose.com/page/net/).

- ドキュメント ディレクトリ: ドキュメント用のディレクトリを設定し、コード内のプレースホルダーを実際のパスに置き換えます。

## 名前空間のインポート

.NET プロジェクトで、Aspose.Page を操作するために必要な名前空間をインポートします。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

次に、各例をステップバイステップのガイド形式で複数のステップに分けて説明します。


## 変換なし

### ステップ 1: 出力ストリームを作成する

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";

//PostScript ドキュメントの出力ストリームを作成する
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    //デフォルト値を使用して保存オプションを作成する
    PsSaveOptions options = new PsSaveOptions();

    //新しい 1 ページの PS ドキュメントを作成する
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    //四角形からグラフィックス パスを作成する
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    //上位レベルのグラフィックス状態にペイントを設定します
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    //上位レベルのグラフィックス状態にある最初の四角形を変換せずに塗りつぶします。
    document.Fill(path);

    //現在のページを閉じる
    document.ClosePage();

    //文書を保存する
    document.Save();
}
```

このコードは、変形を行わずに四角形をオレンジ色で塗りつぶす PostScript ドキュメントを作成します。

## 翻訳

### ステップ 1: グラフィックス状態を保存する

```csharp
//グラフィックス状態を保存して、変換後にこの状態に戻します
document.WriteGraphicsSave();
```

このステップにより、現在のグラフィックス状態が保存され、変換後にその状態に戻ることができます。

### ステップ 2: グラフィックス状態を変換する

```csharp
//現在のグラフィックス状態を右に 250 ずらします
document.Translate(250, 0);
```

変換コンポーネントを追加して現在のグラフィックス状態を変換し、現在のグラフィックス状態のペイントを青色に設定します。

### ステップ 3: 平行移動変換で四角形を塗りつぶす

```csharp
//現在のグラフィックス状態でペイントを設定する
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

//現在のグラフィックス状態で 2 番目の四角形を塗りつぶします (変換変換あり)。
document.Fill(path);
```

このステップにより、現在のグラフィックス状態で 2 番目の四角形が塗りつぶされます。これには、変換変換が含まれます。

### ステップ 4: グラフィックス状態を復元する

```csharp
//グラフィックス状態を以前の (上位) レベルに復元します
document.WriteGraphicsRestore();
```

長方形を塗りつぶした後、グラフィックスの状態を前のレベルに戻します。

スケーリング、回転、シアリング、複雑な変換などの各変換タイプについて、このステップバイステップのガイドを続けてください。

## 結論

おめでとう！ Aspose.Page for .NET の変革的な機能を正常に操作できました。次に、さまざまな組み合わせを試して、PostScript ドキュメントの変換で創造性を発揮してください。

## よくある質問

### Q1: 単一のオブジェクトに複数の変換を適用するにはどうすればよいですか?

A1: 複数の変換を適用するには、`Transform`カスタム変換行列を使用したメソッド。

### Q2: ドキュメントを保存する前に変換をプレビューできますか?

A2: はい、ドキュメントをレンダリングして適切なビューアでプレビューすることで、変換を視覚化できます。

### Q3: ドキュメント内の特定の要素に変換を適用することはできますか?

A3: はい、ドキュメント内の特定のグラフィック要素への変換を分離できます。

### Q4: 複雑な変換を処理する場合、パフォーマンスに関する考慮事項はありますか?

A4: 複雑な変換はパフォーマンスに影響を与える可能性があるため、効率を高めるためにコードを最適化してください。

### Q5: Aspose.Page 関連のクエリについてサポートを受けたり支援を求めたりするにはどうすればよいですか?

 A5: にアクセスしてください。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティのサポートとディスカッションのために。