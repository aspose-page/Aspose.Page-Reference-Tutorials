---
title: Aspose.Page を使用して Java で EPS ファイルのサイズを変更する
linktitle: JavaでEPSファイルのサイズを変更する
second_title: Aspose.Page Java API
description: Aspose.Page for Java を使用して Java で EPS ファイルのサイズを簡単に変更する方法を学びましょう。段階的な手順については、包括的なガイドに従ってください。
type: docs
weight: 11
url: /ja/java/manipulation-eps/resize/
---
## 導入
強力な Aspose.Page ライブラリを使用して Java で EPS ファイルのサイズを変更するためのステップバイステップ ガイドへようこそ。 EPS 画像のサイズをプログラムで調整する必要があった場合は、ここが正しい場所です。このチュートリアルでは、ポイント、インチ、ミリメートル、パーセントなどのさまざまなサイズ変更オプションを検討し、特定の要件に必要な柔軟性を提供します。
## 前提条件
チュートリアルに入る前に、次のものが揃っていることを確認してください。
- Java Development Kit (JDK) がマシンにインストールされています。
-  Java ライブラリの Aspose.Page。ダウンロードできます[ここ](https://releases.aspose.com/page/java/).
- Java プログラミングの基本的な理解。
## パッケージのインポート
Java プロジェクトに、Aspose.Page 機能を使用するために必要なインポートがあることを確認してください。以下に例を示します。
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
ここで、チュートリアルをサイズ変更オプションごとに複数のステップに分割してみましょう。
## ポイントを使用して EPS のサイズを変更する
### ステップ 1: 入力ストリームを設定する
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### ステップ 2: PsDocument オブジェクトを初期化する
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### ステップ 3: EPS 画像の現在のサイズを抽出する
```java
Dimension oldSize = doc.extractEpsSize();
```
### ステップ 4: 出力ストリームを作成する
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### ステップ 5: サイズを変更してポイント単位で保存する
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## インチを使用して EPS のサイズを変更する
例 1 と同様の手順に従い、「ポイント」を「インチ」に置き換え、それに応じて新しいサイズを調整します。
## ミリメートルを使用して EPS のサイズを変更する
例 1 と同様の手順に従い、「ポイント」を「ミリメートル」に置き換え、それに応じて新しいサイズを調整します。
## パーセンテージを使用して EPS のサイズを変更する
例 1 と同様の手順に従い、「ポイント」を「パーセンテージ」に置き換え、それに応じて新しいサイズを調整します。
## 結論
おめでとう！ Aspose.Page を使用して Java で EPS ファイルのサイズを変更する方法を学習しました。このガイドでは、特定のニーズに合わせてサイズ変更プロセスをカスタマイズできるようにするための多彩なオプションを提供します。

## よくある質問
### このライブラリを他の画像形式に使用できますか?
いいえ、Aspose.Page は PostScript および EPS ファイルを処理するために特別に設計されています。
### Aspose.Page for Java に利用できる無料トライアルはありますか?
はい、無料トライアルを試すことができます[ここ](https://releases.aspose.com/).
### 追加のヘルプやディスカッションはどこで見つけられますか?
訪問[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティサポートのために。
### 仮免許はどうやって取得できますか?
仮免許が取得できる[ここ](https://purchase.aspose.com/temporary-license/).
### 利用可能なサンプルプロジェクトはありますか?
はい、ドキュメントを確認してください[ここ](https://reference.aspose.com/page/java/).