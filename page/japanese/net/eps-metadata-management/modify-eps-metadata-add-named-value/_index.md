---
title: Aspose.Page を使用して名前付き値を追加する
linktitle: 名前付き値の追加
second_title: Aspose.Page .NET API
description: Aspose.Page を使用して .NET で名前付きの値を EPS ファイルに追加する方法を学習します。この包括的なチュートリアルでは、プロセスをステップごとに説明します。
weight: 12
url: /ja/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page を使用して名前付き値を追加する

## 導入

.NET によるドキュメント処理の分野では、Aspose.Page は EPS ファイルを処理するための強力なツールとして際立っています。 Aspose.Page を使用すると、開発者は XMP メタデータを操作できるようになり、名前付き値の追加などのタスクが容易になります。このチュートリアルでは、Aspose.Page を使用して名前付き値を EPS ファイルに追加するプロセスを段階的に説明します。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

- C# プログラミング言語の基本的な知識。
- Visual Studio などの統合開発環境 (IDE) がインストールされている。
-  .NET ライブラリの Aspose.Page。インストールされていない場合は、からダウンロードできます[ここ](https://releases.aspose.com/page/net/).

## 名前空間のインポート

まず、必要な名前空間を C# コードにインポートしましょう。これらの名前空間は、Aspose.Page が提供する機能にアクセスするために不可欠です。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## ステップ 1: EPS ファイル入力ストリームを初期化する

最初のステップには、EPS ファイルの入力ストリームの初期化が含まれます。交換する`"Your Document Directory"`ドキュメント ディレクトリへのパスを置き換えます。

```csharp
//例開始:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## ステップ 2: XMP メタデータを取得する

EPS ファイルから XMP メタデータを取得します。 EPS ファイルに XMP メタデータがない場合は、PS メタデータ コメントの値が埋め込まれた新しいファイルが作成されます。

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## ステップ 3: XMP メタデータ値を変更する

次に、XMP メタデータに変更を加えてみましょう。この例では、名前付きの値を「xmpTPg:MaxPageSize」構造に追加します。

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## ステップ 4: 変更された XMP メタデータを含む EPS ファイルを保存する

更新された XMP メタデータを含む EPS ファイルを保存します。出力ストリームを作成し、変更した EPS ファイルを保存します。

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## 結論

おめでとう！ .NET の Aspose.Page を使用して、名前付き値を EPS ファイルに追加することに成功しました。このチュートリアルでは、重要な手順を説明し、ドキュメント操作における Aspose.Page のシンプルさと有効性を示しました。

## よくある質問

### Q1: Aspose.Page はさまざまな EPS ファイル バージョンと互換性がありますか?

A1: Aspose.Page はさまざまな EPS ファイル バージョンをサポートしており、幅広いドキュメントとの互換性を確保しています。

### Q2: Aspose.Page を商用プロジェクトに使用できますか?

 A2: はい、Aspose.Page には商用ライセンスが付属しており、購入できます。[ここ](https://purchase.aspose.com/buy).

### Q3: Aspose.Page に利用できる無料トライアルはありますか?

 A3: はい、無料トライアルを利用して Aspose.Page を探索できます。[ここ](https://releases.aspose.com/).

### Q4: サポートを得たり、Aspose コミュニティに接続したりするにはどうすればよいですか?

 A4: にアクセスしてください。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)サポートを得てコミュニティとつながるために。

### Q5: 仮免許とは何ですか?どうすれば取得できますか?

 A5: テストまたは評価目的で一時ライセンスが必要な場合は、取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
