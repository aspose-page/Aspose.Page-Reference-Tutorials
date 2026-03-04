---
date: 2025-12-25
description: Aspose.Page を使用して Java で XPS ドキュメントにグラデーションを追加する方法と、見事な水平効果を得るためにグラデーションストップをカスタマイズする方法を学びましょう。
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Java XPSでグラデーションを追加する方法 – 水平グラデーション
url: /ja/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPSでグラデーションを追加する方法 – 水平グラデーション

## はじめに
このステップバイステップガイドへようこそ。**グラデーションを XPS ドキュメントに追加する方法**を Java で解説します。本チュートリアルでは水平グラデーションの追加方法、その視覚的な効果の重要性、そして**グラデーション ストップのカスタマイズ**による正確な色制御について学びます。Aspose.Page for Java を使用すれば、XPS (XML Paper Specification) ドキュメントの操作がシンプルになり、低レベルのファイル処理に煩わされることなくデザインに集中できます。

## クイックアンサー
- **必要なライブラリは？** Aspose.Page for Java  
- **対応 Java バージョンは？** Java 8 以上のランタイム  
- **ライセンスは必要？** 開発目的であれば無料トライアルで可。商用利用には製品ライセンスが必要です。  
- **グラデーションの方向は変更できる？** はい – リニア ブラシの開始点/終了点を変更するだけです。  
- **複数のグラデーションを追加できる？** もちろん – 異なるブラシでパス作成手順を繰り返すだけです。  

## XPS の水平グラデーションとは？
水平グラデーションとは、形状全体を左から右へ滑らかに色が変化する効果です。XPS では、定義された **グラデーション ストップ** 間を補間するリニア グラデーション ブラシで表現されます。この視覚効果はバナー、ボタン、背景塗りつぶしなどで頻繁に使用されます。

## Aspose.Page for Java を使う理由
- **フル XPS サポート** – サードパーティーツール不要で作成、編集、レンダリングが可能。  
- **シンプル API** – `XpsDocument`、`XpsPath`、`XpsGradientBrush` などの高レベルオブジェクトが XML の複雑さを隠蔽します。  
- **パフォーマンス** – 大規模ドキュメントやバッチ処理に最適化されています。  

## 前提条件
開始する前に以下を確認してください。

1. **Java 開発環境** – 最新の JDK を [java.com](https://www.java.com) からインストール。  
2. **Aspose.Page for Java ライブラリ** – [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) から JAR をダウンロード。  

## パッケージのインポート
必要なクラスをインポートします。このインポートにより、ドキュメント作成、グラデーション操作、基本ジオメトリへのアクセスが可能になります。

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## ステップ 1: XPS ドキュメントの初期化
新しい `XpsDocument` インスタンスを作成し、結果を保存したいフォルダーを指定します。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## ステップ2: 水平グラデーションを作成する
**グラデーション ストップ** のリストを定義します。これにより各遷移点の色と位置が制御されます。以下の例は鮮やかな虹色のグラデーションを構築します。

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### グラデーションの境界をカスタマイズする方法
- **Color** – 任意の ARGB 値は `doc.createColor(alpha, red, green, blue)` で設定します。  
- **Position** – 2 番目の引数（`0` から `1` の `float`）がグラデーションライン上の停止位置を決めます。値を調整して色を左または右にシフトできます。

## ステップ3: グラデーション付きのパスを追加する
矩形パスを作成し、必要に応じて変形を適用し、リニア グラデーション ブラシで塗りつぶします。ブラシは `(10,0)` から `(228,0)` の 2 点を使用し、水平効果を実現します。

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Pro tip:** 複数のパスで同じ `stops` リストを再利用するとパフォーマンスが向上しますが、新しい停止を追加する前に必ず `clear()` してください。

## ステップ4: ドキュメントを保存する
XPS ファイルをディスクに保存します。保存後は任意の XPS ビューアで開き、水平グラデーションが正しく表示されることを確認できます。

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## よくある問題と解決策
| 問題 | 理由 | 修正 |
|-------|-------|-----|
| グラデーションが単色で表示される | グラデーションストップが追加されていないか、ブラシが設定されていない | `path.setFill(...)` で `LinearGradientBrush` が使用され、`getGradientStops().addAll(stops)` によってストップが追加されていることを確認してください。 |
| 色がくすんで見える | アルファ値が正しくありません (最初のパラメータ) | 透明化が必要な場合を除き、完全に不透明な色には `255` を使用してください。 |
| パスのサイズが間違っている | 変換マトリックスの値が間違っている | マトリックスパラメータ (`scaleX, skewY, skewX, scaleY, translateX, translateY`) を調整してください。 |

## よくある質問

**Q: 1 つの XPS ドキュメントに複数のグラデーションを適用できますか？**
A: はい。複数のパスを追加し、それぞれにグラデーションブラシを適用することで、複雑なレイヤーデザインを作成できます。

**Q: Aspose.Page は最新の Java バージョンと互換性がありますか？**
A: Aspose.Page for Java は定期的に更新されており、Java 8 以降のリリースで動作します。

**Q: Aspose.Page では、他の種類のグラデーションも利用できますか？**
A: 線形グラデーションに加えて、Aspose.Page は円形のカラートランジションを実現する放射状グラデーションもサポートしています。

**Q: グラデーションストップの色と位置をカスタマイズできますか？**
A: もちろんです！各ストップの ARGB カラーとその相対位置（0 ～ 1 の範囲）を完全に制御できます。

**Q: Aspose.Page に関するサポートを得られるコミュニティフォーラムはありますか？**
A: はい、[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39) にアクセスしてコミュニティとつながり、サポートを受けることができます。

---

**最終更新日:** 2025年12月25日
**テスト環境:** Aspose.Page for Java 24.11
**作成者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}