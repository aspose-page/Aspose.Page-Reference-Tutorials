---
date: 2026-03-03
description: Aspose.Page を使用して .NET で EPS 画像のサイズ変更方法を学びましょう – ポイント、インチ、ミリメートル、またはパーセンテージで
  EPS をリサイズするステップバイステップガイド。
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: .NET 用 Aspose.Page で EPS 画像をリサイズする方法
url: /ja/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用した EPS 画像のリサイズ方法

## はじめに

**EPS 画像のリサイズ方法** をシームレスに実現したいですか？本チュートリアルは、ポイント、インチ、ミリメートル、パーセンテージといったさまざまな単位で EPS 画像のサイズを簡単に操作するための包括的なガイドです。Aspose.Page for .NET は強力なツールセットを提供しており、本チュートリアルでは手順を一つずつ解説します。

## クイック回答
- **どのライブラリが EPS のリサイズを扱いますか？** Aspose.Page for .NET  
- **対応している単位は何ですか？** ポイント、インチ、ミリメートル、パーセンテージ  
- **本番環境でライセンスは必要ですか？** はい – 商用ライセンスが必要です  
- **複数ファイルを同時にリサイズできますか？** もちろんです – ファイルをループ処理するだけです  
- **.NET Core はサポートされていますか？** はい、API は .NET Framework と .NET Core の両方で動作します  

## EPS リサイズとは？
Encapsulated PostScript (EPS) は、印刷やデザインのワークフローで一般的に使用されるベクターベースのグラフィック形式です。EPS ファイルのリサイズは、アートワークをラスタライズせずにバウンディングボックスを変更することで、任意のスケールでも鮮明さを保ちます。

## EPS 画像をリサイズする理由
- **印刷品質の維持:** ベクタースケーリングによりエッジがシャープに保たれます。  
- **レイアウト要件への適合:** ページやキャンバスサイズに合わせて寸法を調整できます。  
- **バッチジョブの自動化:** 数十個のファイルを数秒でプログラム的にリサイズできます。  

## 前提条件

リサイズの魔法に入る前に、以下の前提条件が整っていることを確認してください。

- Aspose.Page for .NET ライブラリ: Aspose.Page for .NET ライブラリがインストールされていることを確認してください。ダウンロードは [here](https://releases.aspose.com/page/net/) から可能です。

- ドキュメントディレクトリ: 入力 EPS ファイルと出力リサイズファイルを保存するディレクトリを作成してください。

これで準備が整いましたので、必要な名前空間をインポートし、ステップバイステップのガイドに進みましょう。

## 名前空間のインポート

.NET プロジェクトで Aspose.Page を使用するために、必要な名前空間をインポートします。ファイルの先頭に以下のコードを追加してください。

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

## ポイント単位で EPS をリサイズする方法

ポイントは印刷業界で標準的に使用される測定単位です。以下の例は、元の幅と高さを 2 倍にします。

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
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

## インチ単位で EPS をリサイズする方法

インチは、グラフィックデザイナーが印刷用アセットを準備する際に頻繁に使用します。

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
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

## ミリメートル単位で EPS をリサイズする方法

ミリメートルはメートル法を使用する地域で一般的です。

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
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

## パーセンテージで EPS をリサイズする方法

パーセンテージベースのリサイズは、元のサイズに対する相対的なスケーリングを可能にします。

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
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

これらのメソッドをプロジェクトに組み込めば、EPS 画像のリサイズが簡単に行えます。目的の寸法が得られるまで、さまざまな単位で試してみてください。

## よくある問題と解決策
- **ファイルが見つからない:** `dataDir` が正しいフォルダーを指しているか、`input.eps` が存在するか確認してください。  
- **サイズが予期せぬものになる:** `Units.Percents` は 150 のように「150 %」を表す数値を期待します。  
- **ライセンス例外:** ライセンスエラーが表示された場合、`PsDocument` を作成する前に有効な Aspose.Page ライセンスファイルがロードされていることを確認してください。

## 結論

おめでとうございます！Aspose.Page for .NET を使用した **EPS 画像のリサイズ方法** を習得しました。この強力なライブラリは、ベクターグラフィックの操作に無限の可能性をもたらします。印刷でもデジタルメディアでも、Aspose.Page を活用して正確かつカスタマイズされた結果を実現してください。

## FAQ

### Q1: 複数の EPS 画像を同時にリサイズできますか？

A1: はい、EPS ファイルのコレクションをループ処理し、リサイズメソッドを適用できます。

### Q2: Aspose.Page は他の画像形式にも対応していますか？

A2: Aspose.Page は主に PostScript と EPS 形式に焦点を当てています。他の画像形式については Aspose.Imaging の使用をご検討ください。

### Q3: 商用プロジェクトでのライセンスに関する考慮事項はありますか？

A3: はい、有効なライセンスが必要です。ライセンスの詳細は [here](https://purchase.aspose.com/buy) をご覧ください。

### Q4: 購入前に Aspose.Page を試すことはできますか？

A4: もちろんです！無料トライアルは [here](https://releases.aspose.com/) から入手できます。

### Q5: 追加のサポートや問題の議論はどこで行えますか？

A5: コミュニティと交流しサポートを受けるには、[Aspose.Page forum](https://forum.aspose.com/c/page/39) をご利用ください。

## Frequently Asked Questions

**Q: このコードは .NET Core 6 でも動作しますか？**  
A: はい。API は .NET Framework 4.5 以降、.NET Core 3.1 以降、.NET 5 以降、.NET 6 以降と互換性があります。

**Q: 元のカラープロファイルを保持するにはどうすればよいですか？**  
A: `ResizeEps` メソッドはカラー データを変更せず、バウンディングボックスのみを変更します。

**Q: EPS 全体をメモリに読み込まずにリサイズできますか？**  
A: ストリームを使用することでメモリ使用量を抑え、ドキュメントはオンザフライで処理されます。

**Q: 複数のリサイズ操作をチェーンできますか？**  
A: もちろんです。同じ `PsDocument` インスタンスで `ResizeEps` を順次呼び出せます。

**Q: EPS 内に埋め込まれた画像はどうなりますか？**  
A: ベクタ コンテンツと同様に比例してスケーリングされ、品質が保たれます。

---

**最終更新日:** 2026-03-03  
**テスト環境:** Aspose.Page 24.12 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}