---
date: 2026-04-24
description: Aspose.Page を使用して Java XPS で矩形の色を設定し、矩形を追加する方法を学びます。このガイドでは、Java で矩形を追加し、矩形のストロークを変更する方法をカバーしています。
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: Java XPSで矩形を追加する
second_title: Aspose.Page Java API
title: Java XPSで矩形の色を設定し、矩形を追加する
url: /ja/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPSで矩形の色を設定し、矩形を追加する

## はじめに
このガイドでは、Aspose.Page ライブラリを使用して Java XPS で **矩形の色を設定** し、**矩形を追加** する方法を学びます。レポート用にシンプルな形状を描く場合でも、複雑なベクターグラフィックを作成する場合でも、矩形のスタイリングを習得すれば XPS ドキュメントを正確に制御できます。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Page for Java  
- **矩形のストロークを変更できますか？** Yes, using `setStroke` and `setStrokeThickness`  
- **CMYK カラープロファイルはサポートされていますか？** Absolutely – you can load ICC profiles as shown  
- **本番環境でライセンスが必要ですか？** Yes, a commercial license is required for non‑evaluation use  
- **実装にどれくらい時間がかかりますか？** Typically under 10 minutes for a basic rectangle

## **set rectangle color** とは何ですか？
矩形の色を設定するとは、最終的な XPS ドキュメントで形状が描画される際の塗りつぶし色またはストローク色を定義することです。Aspose.Page を使用すると、RGB、CMYK、あるいはカスタム ICC カラープロファイルを利用して正確な色合わせが可能です。

## Aspose.Page を使用して **add rectangle java** と **change rectangle stroke** を行う理由は？
- **フル機能 API** – ソリッドカラーとグラデーションの両方をサポート。  
- **クロスプラットフォーム** – ネイティブ依存なしで任意の Java ランタイムで動作。  
- **豊富なジオメトリサポート** – 複雑なパスを作成し、変換を適用し、ストロークの太さを簡単に管理。

## 前提条件
コードに入る前に、以下を確認してください。

- Java プログラミングの基本知識。  
- Aspose.Page ライブラリがインストールされていること。未インストールの場合は、[Aspose.Page Java ドキュメント](https://reference.aspose.com/page/java/) からダウンロードしてください。  
- 動作する Java 開発環境（IDE、JDK など）。

## パッケージのインポート
開始するには、必要なパッケージを Java プロジェクトにインポートします。Aspose.Page ライブラリがクラスパスに正しく追加されていることを確認してください。以下は基本的な例です。
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

それでは、提供された例を複数のステップに分解し、Java XPS で **矩形を追加** し、**色を設定** していきましょう。

## 手順 1: ドキュメントディレクトリの設定
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
`"Your Document Directory"` を、XPS ファイルの読み書きを行いたい絶対パスに置き換えてください。

## 手順 2: 新しい XPS ドキュメントの作成
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
この行は、形状を保持する新しい XPS ドキュメントを初期化します。

## 手順 3: CMYK ソリッドカラーのストローク付き矩形を追加
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
このステップでは、CMYK のソリッドカラーを持つ **ストローク付き矩形** を追加します。`setStroke` メソッドは矩形の輪郭色を定義し、`setStrokeThickness` は線幅を制御します—**矩形のストロークを変更** するのに最適です。

### プロのコツ:
RGB カラーを使用したい場合は、`createColor` の呼び出しを `doc.createColor(0, 0, 255)` に置き換えて、ソリッドな青色の塗りつぶしにしてください。

## 手順 4: 結果の XPS ドキュメントを保存
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
最後に、XPS ドキュメントをディスクに保存します。ファイル `AddRectangle_out.xps` には、設定した色とストロークを持つ矩形が含まれます。

## よくある問題と解決策
| 問題 | 原因 | 解決策 |
|-------|-------|----------|
| **矩形が表示されない** | パスジオメトリが正しくない、またはストロークの太さが 0 に設定されている | `"M 20,10 L 220,10 220,100 20,100 Z"` のパス文字列を確認し、`setStrokeThickness` が 0 より大きいことを確認してください。 |
| **色が間違っている** | 目的のカラースペースと一致しない ICC プロファイルを使用している | RGB には `doc.createColor(r, g, b)` を使用するか、ICC ファイルのパスを再確認してください。 |
| **ファイルが保存されない** | `dataDir` が存在しないフォルダーを指している、または書き込み権限がない | 事前にフォルダーを作成するか、書き込み可能な場所を選択してください。 |

## よくある質問

**Q:** *単一の XPS ドキュメントに複数の矩形を追加できますか？*  
A: Yes. Simply repeat the geometry creation and styling steps for each rectangle you need.

**Q:** *ストロークではなく矩形の塗りつぶし色を変更するにはどうすればよいですか？*  
A: Use `path.setFill(...)` with a solid color brush, similar to how `setStroke` is used.

**Q:** *複雑な XPS ドキュメントの操作に Aspose.Page は適していますか？*  
A: Absolutely. The library supports advanced features like gradients, transformations, and embedded fonts.

**Q:** *追加のサンプルやコミュニティサポートはどこで見つけられますか？*  
A: Explore the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for more code samples and peer assistance.

**Q:** *購入前に Aspose.Page を試すことはできますか？*  
A: Yes, you can explore a [free trial](https://releases.aspose.com/) to evaluate the API’s capabilities.

---

**最終更新日:** 2026-04-24  
**テスト環境:** Aspose.Page for Java 24.12  
**作者:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}