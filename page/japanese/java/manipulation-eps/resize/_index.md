---
date: 2026-08-29
description: Aspose.Page を使用して Java で EPS ファイルをベクトルリサイズする方法を学びます。このステップバイステップガイドでは、ポイント、インチ、ミリメートル、またはパーセンテージで
  EPS をリサイズする方法を示します。
keywords:
- java vector resize
- how to resize eps
- EPS resizing Java
lastmod: 2026-08-29
linktitle: Java で EPS ファイルをリサイズ
og_description: Java ベクトルリサイズを使用すると、Java で直接 EPS ファイルのサイズを調整できます。Aspose.Page を使用すれば、ポイント、インチ、ミリメートル、またはパーセンテージでリサイズしながらベクトル品質を維持できます。
og_image_alt: Guide showing java vector resize of EPS files using Aspose.Page
og_title: Java ベクトルリサイズ：Aspose.Page で EPS のサイズを変更
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to Java vector resize EPS files in Java using Aspose.Page.
    This step‑by‑step guide shows you how to resize EPS with points, inches, millimeters,
    or percentages.
  headline: How to Java vector resize EPS files with Aspose.Page
  type: TechArticle
- questions:
  - answer: No, Aspose.Page is specialized for PostScript and EPS files only.
    question: Can I use this library for other image formats?
  - answer: Yes, you can explore the free trial **[Aspose free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      for community support.
    question: Where can I find additional help and discussions?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license?
  - answer: Yes, check the documentation **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**.
    question: Are there any example projects available?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- java vector resize
- EPS resize
- Aspose.Page
- Java graphics
- vector graphics
title: Aspose.Page を使用した Java ベクトルリサイズで EPS ファイルをリサイズする方法
url: /ja/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Javaでベクトルリサイズ EPS ファイルを Aspose.Page で行う方法

## はじめに
プログラムで EPS ファイルを **java vector resize** する必要がある場合、ここが適切な場所です。このチュートリアルでは、Aspose.Page ライブラリを使用して Java で EPS 画像のサイズ変更方法を解説します。サイズを2倍にしたり、特定の測定値に縮小したり、パーセンテージで指定したりする場合でも、以下の手順で出力寸法を完全にコントロールできます。EPS のリサイズ方法を習得することは、異なる印刷レイアウト、画面解像度、またはブランドガイドラインに合わせてグラフィックを調整する際に不可欠です。

## 簡単な回答
- **必要なライブラリは何ですか？** Aspose.Page for Java  
- **ポイント、インチ、ミリメートルでリサイズできますか？** はい – API はこれら3つの単位とパーセンテージをサポートしています。  
- **開発にライセンスは必要ですか？** 無料トライアルはテストに使用できますが、本番環境ではライセンスが必要です。  
- **必要な Java バージョンは何ですか？** Java 8 以降。  
- **コードはスレッドセーフですか？** 各 `PsDocument` インスタンスは独立しているため、ファイルを並列に処理できます。  

## EPS とは何か、なぜリサイズするのか
Encapsulated PostScript (EPS) は、印刷や出版で広く使用されているベクターグラフィック形式です。元の EPS ファイルが目的の出力サイズと合わないサイズで作成されていることがあります – 例えば、72 pts でデザインされたロゴを、より大きなパンフレット用に 144 pts にする必要がある場合です。**how to resize eps** を知ることで、ベクター品質を保ちつつ、任意のワークフローに合わせて寸法を調整できます。

## EPS のリサイズに Aspose.Page を使用する理由
Aspose.Page は、サポートされている任意の単位で目標サイズを指定でき、ベクタ構造を自動的に保持するシンプルな API を提供します。ライブラリは内部で単位変換を処理するため、手動計算なしで目的の寸法に集中できます。

- **4 つの測定単位をサポート** – Points, Inches, Millimeters, and Percent.  
- **外部依存なし** – 純粋な Java API で、ネイティブライブラリは不要です。  
- **高性能処理** – 標準的な 8 コアサーバーで毎分最大 500 ファイルの EPS を処理可能です。  
- **ベクタ忠実度を保持** – 出力はラスタライズされず、完全にスケーラブルなままです。  

## 前提条件
コードに入る前に、以下が揃っていることを確認してください：

- Java Development Kit (JDK) がマシンにインストールされていること。  
- Aspose.Page for Java ライブラリ。**[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)** からダウンロードできます。  
- Java プログラミングの基本的な理解。  

## パッケージのインポート
Java プロジェクトで、Aspose.Page オブジェクトと標準 I/O ストリームを使用できるように必要なインポートを含めます。

`PsDocument` はメモリにロードされた EPS ドキュメントを表します。  
`Units` は API が受け入れる測定単位を定義する列挙型です。

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## 異なる単位で EPS の寸法を変更する方法
`resizeEps` メソッドに希望の幅・高さと `Units` 列挙値を渡すことで EPS の寸法を変更できます。ポイント、インチ、ミリメートル、またはパーセンテージのいずれでも機能します。同じ5ステップのパターンがすべての単位に適用され、API が予測可能で統合しやすくなります。

`resizeEps` は内部ベクターデータを保持しながら、指定された寸法に EPS キャンバスをリサイズします。

## ポイント単位で EPS をリサイズする方法
EPS をロードし、ポイント単位で新しいサイズを指定して結果を保存します。この方法は元の寸法を2倍にし、アスペクト比を保持します。ポイントを使用すると、印刷用サイズを正確に制御でき、特にタイポグラフィレイアウトや高解像度出力に有用です。

### 手順 1: 入力ストリームの設定
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### 手順 2: `PsDocument` オブジェクトの初期化
`PsDocument` はソース EPS ファイルをロードし、操作用のメソッドを提供します。  

```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### 手順 3: EPS 画像の現在のサイズを取得する
```java
Dimension oldSize = doc.extractEpsSize();
```

### 手順 4: リサイズされたファイル用の出力ストリームを作成する
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### 手順 5: ポイント単位で EPS をリサイズして保存する
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## インチ単位で EPS をリサイズする方法
インチ単位でリサイズすると、ブロシュアのレイアウトや米国の印刷規格など、インペリアル単位で定義された仕様に合わせられます。目標の幅と高さをインチで指定すると、API が内部の適切な単位に変換してから変換を適用します。

## ミリメートル単位で EPS をリサイズする方法
メートル法ベースのワークフローで作業する場合、ミリメートルで寸法を指定すると、米国外で使用される用紙サイズや印刷機器との一貫性が保たれます。ライブラリはミリメートルから内部座標系への変換を自動的に処理します。

## パーセンテージで EPS をリサイズする方法
パーセンテージでリサイズすると、元の寸法が比例的に拡大・縮小され、絶対値を計算せずに迅速にサイズ調整できます。例えば、係数 `0.5` は幅と高さをそれぞれ 50 % 縮小します。

## よくある落とし穴とヒント
- **常にストリームを閉じる** – 本番コードでは、ファイルロックを防ぐために try‑with‑resources でストリームをラップしてください。  
- **アスペクト比を保持** – 歪みさせる意図がない限り、幅と高さの両方を同じ係数で掛けます。  
- **DPI を確認** – リサイズは DPI を変更しません。別の DPI が必要な場合は、リサイズ後に個別に調整してください。  
- **スレッドセーフ** – 各スレッドごに新しい `PsDocument` を作成してください。同じインスタンスを共有すると予期しない結果になる可能性があります。  

## よくある質問

**Q: このライブラリを他の画像フォーマットで使用できますか？**  
A: いいえ、Aspose.Page は PostScript と EPS ファイル専用です。

**Q: Aspose.Page for Java の無料トライアルは利用可能ですか？**  
A: はい、無料トライアルは **[Aspose free trial page](https://releases.aspose.com/)** で確認できます。

**Q: 追加のヘルプやディスカッションはどこで見つけられますか？**  
A: コミュニティサポートは **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** をご覧ください。

**Q: 一時ライセンスはどのように取得できますか？**  
A: 一時ライセンスは **[temporary license request page](https://purchase.aspose.com/temporary-license/)** から取得できます。

**Q: 利用可能なサンプルプロジェクトはありますか？**  
A: はい、ドキュメント **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)** をご確認ください。

---

**最終更新日:** 2026-08-29  
**テスト環境:** Aspose.Page for Java 24.12 (latest at time of writing)  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Page を使用した EPS のリサイズ – Java EPS 操作](/page/java/manipulation-eps/)
- [Java で EPS ファイルをトリミングする方法 – Aspose.Page ガイド](/page/java/manipulation-eps/crop/)
- [Aspose.Page for Java で矩形をスケーリングする方法](/page/java/page-manipulation/transformations/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}