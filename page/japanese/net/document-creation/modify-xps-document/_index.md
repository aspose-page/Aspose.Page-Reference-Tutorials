---
title: Aspose.Page for .NET を使用して XPS ドキュメントを変更する
linktitle: XPSドキュメントの変更
second_title: Aspose.Page .NET API
description: XPS ドキュメントを簡単に変更できる Aspose.Page for .NET の機能を試してください。ステップバイステップのガイドに従って、文書処理を強化し、パーソナライズされた署名テキストを追加します。
type: docs
weight: 12
url: /ja/net/document-creation/modify-xps-document/
---
## 導入

Aspose.Page for .NET を使用して XPS ドキュメントを変更する方法に関するステップバイステップ ガイドへようこそ。 Aspose.Page は、開発者が XPS ファイルを簡単に操作できるようにする強力なライブラリです。このチュートリアルでは、XPS ドキュメント内の指定されたページに署名テキスト「確認済み」を追加するプロセスを説明します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

- Aspose.Page for .NET: Aspose.Page ライブラリがインストールされていることを確認してください。ドキュメントを見つけることができます[ここ](https://reference.aspose.com/page/net/).

- 必要なファイルをダウンロードする: 入力 XPS ドキュメントを含む必要なファイルを次の場所からダウンロードします。[Aspose リリースページ](https://releases.aspose.com/page/net/).

- ドキュメント ディレクトリ: ドキュメント用のディレクトリを設定し、`dir`コード内の変数を適切なパスに置き換えます。

すべての設定が完了したので、ステップバイステップのガイドに進みましょう。

## 名前空間のインポート

.NET プロジェクトで、Aspose.Page に必要な名前空間をインポートすることから始めます。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## ステップ 1: XPS ドキュメント ストリームを開く

```csharp
//例開始:3
//ドキュメントディレクトリへのパス。
string dir = "Your Document Directory";
// XPS ファイルのストリームを開く
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    //ストリームから PS ドキュメントを作成する
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    //次のステップに進みます...
}
//拡張終了:3
```

## ステップ 2: 署名テキストを作成する

```csharp
//例開始:4
//署名テキストの塗りつぶしを作成する
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
//次のステップに進みます...
//拡張終了:4
```

## ステップ 3: ページを定義し、署名を追加する

```csharp
//例開始:5
//署名を設定するページを定義する
int[] pageNumbers = new int[] {1, 2, 3};

//定義されたすべてのページに対して、座標 x=650 および y=950 で署名「確認済み」を設定します。
for (int i = 0; i < pageNumbers.Length; i++)
{
    //アクティブなページを定義する
    document.SelectActivePage(pageNumbers[i]);

    //グリフオブジェクトを作成する
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    //グリフの塗りつぶしを定義する
    glyphs.Fill = textFill;
}
//次のステップに進みます...
//拡張終了:5
```

## ステップ 4: XPS ドキュメントへの変更を保存する

```csharp
//例開始:6
//変更された XPS ドキュメントを保存する
document.Save(dir + "input1_out.xps");
//拡張終了:6
```

おめでとう！ Aspose.Page for .NET を使用して XPS ドキュメントを正常に変更しました。ドキュメント処理を強化するために、Aspose.Page が提供する追加の機能を自由に探索してください。

## 結論

このチュートリアルでは、Aspose.Page for .NET を使用して XPS ドキュメントを変更するための重要な手順について説明しました。これらの手順に従うことで、署名テキストを特定のページにシームレスに統合し、文書にパーソナライズされたタッチを追加できます。

## よくある質問

### Q1: Aspose.Page は最新の .NET フレームワークと互換性がありますか?

A1: はい、Aspose.Page は最新の .NET フレームワークをサポートするために定期的に更新されます。

### Q2: 追加したテキストのフォントやスタイルをカスタマイズできますか?

A2: もちろんです！要件に応じてフォント、スタイル、その他の属性を変更できます。

### Q3: Aspose.Page が処理できるドキュメント サイズに制限はありますか?

A3: Aspose.Page はさまざまなサイズのドキュメントを処理できるように設計されていますが、特定の詳細については常にドキュメントを確認することをお勧めします。

### Q4: Aspose.Page の一時ライセンスを取得するにはどうすればよいですか?

 A4: 仮免許を取得できます。[ここ](https://purchase.aspose.com/temporary-license/).

### Q5: どこで助けを求めたり、Aspose コミュニティに連絡したりできますか?

 A5: にアクセスしてください。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)質問したり、コミュニティと交流したりするためです。