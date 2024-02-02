---
title: Aspose.Page for .NET を使用して従量制ライセンスを適用する
linktitle: 従量制ライセンスを適用する
second_title: Aspose.Page .NET API
description: 従量制ライセンスの適用に関するこのステップバイステップ ガイドを使用して、Aspose.Page for .NET のシームレスな統合を確認してください。ドキュメント処理を簡単に最適化します。
type: docs
weight: 10
url: /ja/net/getting-started/apply-metered-license/
---
## 導入

従量制ライセンスを適用することで、Aspose.Page for .NET の可能性を最大限に引き出します。このチュートリアルでは、従量制ライセンスを設定して適用するプロセスを説明し、この強力な .NET ライブラリをスムーズかつ最適化して使用できるようにします。

## 前提条件

手順に入る前に、次の前提条件が満たされていることを確認してください。

- 有効な Aspose.Page for .NET ライセンス: 次から入手できます。[購入.aspose.com](https://purchase.aspose.com/buy).
-  Aspose.Page ライブラリがインストールされています:[ドキュメンテーション](https://reference.aspose.com/page/net/)インストール手順については。
- .NET 開発環境: マシン上に動作する .NET 環境がセットアップされていることを確認します。

## 名前空間のインポート

.NET プロジェクトで、Aspose.Page 機能にアクセスするために必要な名前空間をインポートします。

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

## ステップ 1: 従量制の公開キーと秘密キーを設定する

を初期化します`Aspose.Page.Metered`クラスを作成し、従量制の公開鍵と秘密鍵を設定します。交換する`<type public key here>`そして`<type private key here>`実際のキーを使用して。

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## ステップ 2: EPS ファイルをロードしてドキュメントを作成する

EPS ファイルへのパスを指定し、そのコンテンツを読み取るストリームを作成します。次に、のインスタンスを作成します。`PsDocument`ストリームからのクラス。

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## ステップ 3: EPS を PNG 画像に変換する

を作成します`ImageDevice`EPS ファイルを PNG 画像に変換します。 EPS ファイルを画像として保存するには、`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## ステップ 4: 画像バイトを取得する

画像バイトを取得します。各バイト配列は 1 ページを表します。この場合、ページは 1 つあります。

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## ステップ 5: 画像バイトをファイルに保存する

画像バイトをファイルに保存し、EPS から PNG への変換を確実に成功させます。

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## ステップ 6: 従量制ライセンスを確認する

従量制課金ライセンスが正常に適用されているかどうかを視覚的に確認します。結果のイメージに赤色の評価メッセージが含まれていない場合は、従量制ライセンスが問題なく適用されていることを示します。

これで、従量制ライセンスで Aspose.Page for .NET の全機能を活用する準備が整いました。

## 結論

このステップバイステップ ガイドでは、Aspose.Page for .NET を使用して従量制ライセンスをシームレスに適用するための知識を提供します。ドキュメント処理機能を強化し、この強力なライブラリが提供する膨大な機能を探索してください。

## よくある質問

### Q1: Aspose.Page for .NET の従量制ライセンスを取得するにはどうすればよいですか?

 A1: 訪問[購入.aspose.com](https://purchase.aspose.com/buy)有効なライセンスを取得するため。

### Q2: Aspose.Page for .NET のドキュメントはどこで見つけられますか?

 A2: を参照してください。[Aspose.Page .NET](https://reference.aspose.com/page/net/)包括的なドキュメントを作成します。

### Q3: Aspose.Page のディスカッションとサポートのためのフォーラムはありますか?

 A3: はい、訪問します[フォーラム](https://forum.aspose.com/c/page/39)コミュニティと関わり、支援を求めます。

### Q4: 購入する前に Aspose.Page for .NET を試すことはできますか?

 A4：もちろんです！無料トライアルにアクセスするには、[ここ](https://releases.aspose.com/).

### Q5: Aspose.Page for .NET の一時ライセンスを取得するにはどうすればよいですか?

 A5: 訪問[仮免許/](https://purchase.aspose.com/temporary-license/)仮免許を取得するためです。