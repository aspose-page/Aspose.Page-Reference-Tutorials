---
title: Aspose.Page for .NET を使用して EPS 画像のサイズを変更する
linktitle: EPS画像のサイズを変更する
second_title: Aspose.Page .NET API
description: Aspose.Page を使用して、.NET で EPS 画像のサイズを変更するシームレスなプロセスを調べてください。ポイント、インチ、ミリメートル、パーセント単位の精度を簡単に実現します。
weight: 11
url: /ja/net/image-manipulation/resize-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用して EPS 画像のサイズを変更する

## 導入

Aspose.Page for .NET を使用して EPS 画像のサイズをシームレスに変更したいと考えていますか?このチュートリアルは、EPS 画像のサイズをポイント、インチ、ミリメートル、パーセンテージなどのさまざまな単位で簡単に操作するための包括的なガイドです。 Aspose.Page for .NET は強力なツール セットを提供します。このチュートリアルでは、そのプロセスを段階的に説明します。

## 前提条件

サイズ変更のマジックに入る前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Page for .NET ライブラリ: Aspose.Page for .NET ライブラリがインストールされていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/page/net/).

- ドキュメント ディレクトリ: 入力 EPS ファイルとサイズ変更された出力ファイルを保存するディレクトリを作成します。

すべての設定が完了したので、必要な名前空間のインポートに進み、ステップバイステップのガイドを詳しく見てみましょう。

## 名前空間のインポート

.NET プロジェクトで、Aspose.Page を操作するために必要な名前空間をインポートすることから始めます。ファイルの先頭に次のコードを追加します。

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

## ステップ 1: ポイント単位でサイズを変更する

EPS 画像のサイズをポイント単位で変更することから始めましょう。ポイントは印刷業界の標準測定単位です。

```csharp
public static void ResizeInPoints()
{
    //あなたのドキュメントディレクトリ
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## ステップ 2: インチ単位でサイズを変更する

ここで、グラフィック デザインでよく使用される単位であるインチで EPS 画像のサイズを変更しましょう。

```csharp
public static void ResizeInInches()
{
    //あなたのドキュメントディレクトリ
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## ステップ 3: ミリメートル単位でサイズを変更する

ここで、デザインや印刷で広く使用されているもう 1 つの単位であるミリメートルで EPS 画像のサイズを変更してみましょう。

```csharp
public static void ResizeInMillimeters()
{
    //あなたのドキュメントディレクトリ
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## ステップ 4: パーセント単位でサイズを変更する

最後に、パーセンテージを使用して EPS 画像のサイズを変更し、画像サイズを調整する柔軟な方法を提供します。

```csharp
public static void ResizeInPercents()
{
    //あなたのドキュメントディレクトリ
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

これらの方法をプロジェクトに自由に統合すると、EPS 画像のサイズを簡単に変更できるようになります。希望の寸法を達成するために、さまざまな単位を試してください。

## 結論

おめでとう！ Aspose.Page for .NET を使用して EPS 画像のサイズを変更する技術を習得しました。この強力なライブラリは、ベクター グラフィックスを操作する可能性の世界を開きます。印刷メディア用にデザインしている場合でも、デジタル メディア用にデザインしている場合でも、Aspose.Page を使用すると、正確でカスタマイズされた結果を達成できます。

## よくある質問

### Q1: 複数の EPS 画像を同時にサイズ変更できますか?

A1: はい、EPS ファイルのコレクションをループして、それに応じてサイズ変更方法を適用できます。

### Q2: Aspose.Page は他の画像形式と互換性がありますか?

A2: Aspose.Page は主に PostScript および EPS 形式に焦点を当てています。他の画像形式の場合は、Aspose.Imaging の使用を検討してください。

### Q3: 商用プロジェクトの場合、ライセンスに関する考慮事項はありますか?

 A3: はい、有効なライセンスを持っていることを確認してください。訪問[ここ](https://purchase.aspose.com/buy)ライセンスの詳細については、

### Q4: 購入する前に Aspose.Page を試すことはできますか?

 A4：もちろんです！無料トライアルを利用できます[ここ](https://releases.aspose.com/).

### Q5: 追加のサポートを求めたり、問題について話し合ったりできる場所はどこですか?

 A5: にアクセスしてください。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティとつながり、支援を受けることができます。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
