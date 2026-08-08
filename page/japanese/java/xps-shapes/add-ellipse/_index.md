---
date: 2026-04-24
description: ラジアルグラデーション楕円を使用した XPS ドキュメントの Java 作成方法を学びましょう。このステップバイステップ ガイドでは、Aspose.Page
  を使用してストロークの太さを設定し、パスジオメトリを定義する方法を示します。
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: Java XPSで楕円を追加する
second_title: Aspose.Page Java API
title: JavaでXPSドキュメントを作成 – 放射状グラデーション楕円を追加
url: /ja/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page を使用した放射状グラデーション楕円の追加

## はじめに
このチュートリアルでは、Aspose.Page for Java を使用して、美しい放射状グラデーションのストロークが付いた楕円を持つ **create XPS document Java** の作成方法を学びます。Aspose.Page は低レベルの XPS 詳細を抽象化する堅牢なライブラリで、ファイル形式の複雑さではなくデザインに集中できます。このガイドの最後までに、レポートや請求書、または任意の文書生成ワークフローに埋め込める、すぐに使用できる XPS ファイルが手に入ります。

## クイック回答
- **このコードは何を生成しますか？** マルチカラーの放射状グラデーションでストロークされた楕円を含む、単一ページの XPS ファイルです。  
- **使用されている主要 API はどれですか？** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, etc.)。  
- **サンプルを実行するのにライセンスは必要ですか？** 評価用の一時ライセンスで動作しますが、本番環境ではフルライセンスが必要です。  
- **設定する主なプロパティは何ですか？** ストロークブラシ（放射状グラデーション）、スプレッドメソッド、グラデーションストップ、ストロークの太さ。  
- **楕円のサイズを変更できますか？** はい – パスジオメトリ文字列またはグラデーションブラシの座標を変更します。

## “create XPS document Java” とは何ですか？
Java で XPS ドキュメントを作成することは、XML Paper Specification（XPS）ファイルをプログラムで生成することを意味します。XPS は PDF に似た固定レイアウトの文書形式です。Aspose.Page は高レベルのオブジェクトモデル（`XpsDocument`, `XpsCanvas` など）を提供し、XML マークアップを抽象化するため、標準的な Java オブジェクトを操作する感覚で簡単に扱えます。

## なぜ放射状グラデーション楕円を使用するのか？
放射状グラデーションは立体感を演出し、レポートのビジュアルハイライトやロゴ、装飾要素に最適です。単色ストロークに比べ、ファイルサイズを大幅に増やさずに深みを加えることができ、XPS 形式はベクター品質を保持するため、任意の拡大縮小でも鮮明です。

## 前提条件
開始する前に、以下の項目が揃っていることを確認してください。
- Java Development Kit (JDK) がマシンにインストールされていること。
- Aspose.Page for Java ライブラリをダウンロードしてください。入手は [here](https://releases.aspose.com/page/java/) から。
- お好みのコードエディタ（Eclipse、IntelliJ など）で Java コードを書き、実行できる環境。

## パッケージのインポート
Aspose.Page を使用するために、Java プロジェクトに必要なパッケージがインポートされていることを確認してください。以下のインポート文を Java ファイルの先頭に追加します。

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```

## 手順 1: ドキュメントディレクトリの設定
XPS ドキュメントを保存するディレクトリへのパスを定義します。

```java
String dataDir = "Your Document Directory";
```

## 手順 2: XPS ドキュメントの作成
以下のコードで新しい XPS ドキュメントを初期化します。

```java
XpsDocument doc = new XpsDocument();
```

## 手順 3: 放射状グラデーション ストップの定義
放射状グラデーションストローク楕円のためのグラデーションストップのリストを作成します。

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## 手順 4: パスジオメトリの作成
パスジオメトリを使用して放射状グラデーションストローク楕円を定義します。

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## 手順 5: キャンバスとパスの追加
ドキュメントに新しいキャンバスを追加し、定義したジオメトリでパスを追加します。

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## 手順 6: ストロークとグラデーションの設定
放射状グラデーションブラシでパスのストロークを構成します。

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## 手順 7: ストロークの太さの設定
パスの **set stroke thickness** を指定します。

```java
path.setStrokeThickness(12f);
```

## 手順 8: ドキュメントの保存
生成された XPS ドキュメントを保存します。

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

おめでとうございます！Aspose.Page を使用して **create XPS document Java** を作成しながら、放射状グラデーションストローク楕円を正常に追加できました。

## よくある問題と解決策
| 問題 | 発生理由 | 解決策 |
|-------|----------------|-----|
| **楕円が平坦に見える** | `XpsSpreadMethod.Pad` を使用しているため、`Reflect` に変更してください | Step 6 の例のように、スプレッドメソッドを `XpsSpreadMethod.Reflect` に変更します。 |
| **出力ファイルがありません** | `dataDir` が存在しないフォルダーを指しています | ディレクトリが存在することを確認するか、絶対パスを使用してください。 |
| **グラデーションの色がずれている** | グラデーションストップの順序が正しくありません | `offset` 値 (0 → 1) が単調に増加しているか確認してください。 |
| **コンパイルエラー** | クラスパスに Aspose.Page の JAR がありません | `aspose-page-xx.jar` をプロジェクトの依存関係に追加してください。 |

## よくある質問

**Q: Aspose.Page for Java を他の Java ライブラリと併用できますか？**  
A: はい、Aspose.Page for Java は他の Java ライブラリとシームレスに統合できます。

**Q: 大規模な文書処理に Aspose.Page は適していますか？**  
A: もちろんです！Aspose.Page は大規模な文書処理を効率的に処理できるよう設計されています。

**Q: Aspose.Page for Java のチュートリアルやサンプルはどこで見つけられますか？**  
A: 包括的なチュートリアルとサンプルは、[Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) をご覧ください。

**Q: Aspose.Page for Java の一時ライセンスはどう取得できますか？**  
A: 一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q: Aspose.Page のディスカッション用コミュニティフォーラムはありますか？**  
A: はい、[Aspose.Page community forum](https://forum.aspose.com/c/page/39) に参加して他の開発者と交流し、サポートを受けてください。

---

**最終更新日:** 2026-04-24  
**テスト環境:** Aspose.Page for Java 24.11 (執筆時点での最新バージョン)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}