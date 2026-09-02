---
date: 2026-04-30
description: Aspose.Page Java を使用して、Java で XPS ドキュメントを作成し、オパシティ マスクを追加する方法を学びましょう。コード例付きのステップバイステップ
  ガイド。
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: Java XPSで不透明度マスクを設定する
second_title: Aspose.Page Java API
title: JavaでXPSドキュメントを作成 – Aspose.Pageで不透明度マスクを設定
url: /ja/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPSで不透明度マスクを設定する（Aspose.Page Java 使用）

## はじめに
このチュートリアルでは **create XPS document Java** ファイルを作成し、グラフィックに洗練された半透明の外観を与える不透明度マスクの適用方法を学びます。直感的な Aspose.Page Java API を使用して、XPS ドキュメントの初期化、キャンバスの追加、矩形の描画、画像ベースの不透明度マスクの付与までの全工程を順に解説します。最後まで実施すれば、プログラムでプロフェッショナルな XPS ファイルを生成し、必要な任意の形状にマスクを再利用できるようになります。

## クイック回答
- **不透明度マスクは何をするものですか？** 形状の透明度レベルを可変に定義し、下にあるコンテンツが透けて見えるようにします。  
- **どのライブラリが必要ですか？** Aspose.Page for Java (aspose page java)。  
- **ライセンスは必要ですか？** テスト用の一時ライセンスで動作しますが、本番環境では正式なライセンスが必要です。  
- **コード行数はどれくらいですか？** Java で約20行に加えて数行のセットアップ文です。  
- **マスクを複数の形状で再利用できますか？** はい、同じ `ImageBrush` を複数のパスに割り当てることができます。

## XPSにおける不透明度マスクとは？
不透明度マスクはビットマップまたはベクターで、形状内の各ピクセルのアルファ（透明度）を制御します。矩形に適用すると、矩形の一部が完全に不透明になったり、部分的に透明になったり、完全に透明になったりし、余分な描画レイヤーを使用せずに高度な視覚効果を実現します。

## Aspose.Page Java を使用して **create XPS document java** を行う理由は？
- **Pure Java API** – ネイティブ依存がなく、Windows、Linux、macOS のいずれでも同じコードが動作します。  
- **Full XPS spec compliance** – マスクは XPS 標準で定義された通りに正確に描画されます。  
- **Object‑oriented design** – .NET に似た設計で、他言語の Aspose を使用したことがある方でも習得が容易です。  
- **High performance** – 大規模ドキュメントやバッチ処理に最適化されています。

## 主な使用例
- **ウォーターマーキング** – ページ全体に半透明ロゴを適用します。  
- **動的テーマ** – 生成レポートの UI 要素の視覚スタイルを変更します。  
- **印刷プレビュー** – 印刷前に不透明度を変化させたデザインを確認できます。

## 前提条件
開始する前に以下を確認してください：
- Java プログラミングの基本的な理解。  
- Aspose.Page for Java ライブラリがインストール済み。**[here](https://releases.aspose.com/page/java/)** からダウンロードできます。  
- 有効な Aspose.Page ライセンス。お持ちでない場合は **[here](https://purchase.aspose.com/temporary-license/)** から一時ライセンスを取得してください。  
- Java アプリケーションをコンパイル・実行できる開発環境（例：IntelliJ IDEA、Eclipse、VS Code）。

## パッケージのインポート
まず Aspose.Page ライブラリから必要なクラスをインポートします。これにより API がプロジェクトで利用可能になります。

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## 手順ガイド

### 手順 1: 新しい XPS ドキュメントを作成する
まず、すべてのグラフィックを保持する新しい XPS ドキュメントのインスタンスを生成します。

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### 手順 2: キャンバスを追加する
キャンバスは XPS ページ内の描画領域として機能します。

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### 手順 3: 矩形を追加し、単色塗りつぶしを適用する
ここでは矩形パスを作成し、単色の赤で塗りつぶします。この矩形は後で不透明度マスクを受け取ります。

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### 手順 4: ImageBrush を使用して不透明度マスクを追加する
TIFF 画像を読み込み、ソース矩形とデスティネーション矩形を定義し、必要に応じてマスクが繰り返されるようにブラシをタイルモードに設定します。

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### 手順 5: 結果の XPS ドキュメントを保存する
最後に、ドキュメントをディスクに永続化します。出力ファイルには不透明度マスクが適用された矩形が含まれます。

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

これらの手順を注意深く実行すれば、Aspose.Page を使用して Java XPS ドキュメントに **add opacity mask** 機能を組み込むことができます。

## よくある問題とトラブルシューティング
- **画像が見つからない** – `dataDir` が正しいフォルダーを指しているか、`R08SY_NN.tif` が存在するか確認してください。  
- **マスクが完全に不透明に見える** – ソース画像に実際に可変のアルファ値が含まれていることを確認してください。完全に不透明な画像では透明度は表示されません。  
- **タイルモードが反映されない** – デスティネーション矩形はソース矩形より小さく設定する必要があります。そうしないとタイル効果が目立ちません。

## よくある質問

**Q: Aspose.Page はすべての Java 開発環境と互換性がありますか？**  
A: はい、Aspose.Page はさまざまな Java IDE やビルドツールでシームレスに動作するよう設計されています。

**Q: ライセンスなしで Aspose.Page を使用できますか？**  
A: 一時ライセンスで評価は可能ですが、本番環境で使用する場合は正式なライセンスが必要です。

**Q: トライアル版に制限はありますか？**  
A: トライアル版ではサイズや機能に制限が課される場合があります。詳細は公式ドキュメントをご確認ください。

**Q: Aspose.Page のサポートはどのように受けられますか？**  
A: **[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)** でコミュニティの助けを得るか、プレミアムサポートが必要な場合はライセンスをご購入ください。

**Q: Aspose.Page に返金保証はありますか？**  
A: 返金ポリシーの詳細は **[購入ページ](https://purchase.aspose.com/buy)** をご参照ください。

---

**最終更新日:** 2026-04-30  
**テスト環境:** Aspose.Page Java 24.11（執筆時点の最新バージョン）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}