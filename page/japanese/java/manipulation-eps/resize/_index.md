---
date: 2026-02-07
description: JavaでEPSファイルのサイズを変更し、Aspose.Pageを使用してEPSの寸法を調整する方法を学びましょう。このステップバイステップガイドでは、ポイント、インチ、ミリメートル、またはパーセンテージでEPSをリサイズする方法を示します。
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: JavaでAspose.Pageを使用してEPSファイルのサイズを変更する方法
url: /ja/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java で Aspose.Page を使用して EPS ファイルのサイズを変更する方法

## Introduction
プログラムで **EPS のサイズ変更方法** を探しているなら、ここが最適です。このチュートリアルでは Aspose.Page ライブラリを使って Java で EPS 画像のサイズを変更する手順を解説します。サイズを倍にしたり、特定の寸法に縮小したり、パーセンテージで調整したりする方法を示すので、出力サイズを完全にコントロールできます。**EPS のサイズ変更方法** を理解することは、異なる印刷レイアウトや画面解像度に合わせてグラフィックを調整する際に重要です。

## Quick Answers
- **必要なライブラリは？** Aspose.Page for Java  
- **ポイント、インチ、ミリメートルでサイズ変更できますか？** はい – API はこれら3つの単位とパーセンテージをサポートしています。  
- **開発にライセンスは必要ですか？** テスト用の無料トライアルで動作しますが、本番環境ではライセンスが必要です。  
- **必要な Java バージョンは？** Java 8 以降。  
- **コードはスレッドセーフですか？** 各 `PsDocument` インスタンスは独立しているため、ファイルを並列処理できます。  

## What is EPS and Why Resize It?
Encapsulated PostScript (EPS) は出版・印刷で広く使われるベクターグラフィック形式です。元の EPS ファイルが目的の出力サイズと合わないことがあります。例えば、ロゴが 72 pts で作成されていて、より大きなパンフレット用に 144 pts が必要な場合です。**EPS のサイズ変更方法** を知っておくと、ベクター品質を保ったまま任意のワークフローに合わせて寸法を調整できます。

## Why Use Aspose.Page for Resizing EPS?
- **単位のフルコントロール** – ポイント、インチ、ミリメートル、またはパーセンテージ。  
- **外部依存なし** – 純粋な Java API、ネイティブライブラリ不要。  
- **高性能** – サーバー上でのバッチ処理に最適。  
- **ベクターフィデリティを保持** – ラスタライズせずにスケーラブルな出力を維持。  

## Prerequisites
コードに入る前に、以下を用意してください。

- マシンにインストールされた Java Development Kit (JDK)。  
- Aspose.Page for Java ライブラリ。**[こちら](https://releases.aspose.com/page/java/)** からダウンロードできます。  
- Java プログラミングの基本的な理解。  

## Import Packages
Java プロジェクトに必要なインポートを追加し、Aspose.Page オブジェクトと標準 I/O ストリームを使用できるようにします。

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## How to Change EPS Dimensions with Different Units
ライブラリを使うと、適切な `Units` 列挙型を選択するだけで **EPS の寸法変更** が簡単にできます。以下ではポイント、インチ、ミリメートル、パーセンテージの 4 つの単位で同じ 5 ステップパターンを示します。唯一変わるのは `resizeEps` に渡す単位だけです。

## How to Resize EPS Using Points
ポイントを測定単位として使用し、EPS ファイルのサイズを倍にする完全なステップバイステップ例です。

### Step 1: Set up the input stream
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Step 2: Initialize the `PsDocument` object
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Step 3: Extract the current size of the EPS image
```java
Dimension oldSize = doc.extractEpsSize();
```

### Step 4: Create an output stream for the resized file
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Step 5: Resize and save the EPS using points
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## How to Resize EPS Using Inches
同じ 5 ステップパターンを使用し、`Units.Points` を `Units.Inches` に置き換えて、目的のインチ値に合わせてスケーリングファクターを調整します。

## How to Resize EPS Using Millimeters
同様に手順を踏み、単位を `Units.Millimeters` に変更します。印刷ワークフローでメートル法の寸法が必要なときに便利です。

## How to Resize EPS Using Percentages
パーセンテージベースのスケーリングの場合は、単位を `Units.Percent` のままにします。元の幅と高さに希望のパーセンテージ（例: 50 % 縮小なら `0.5`）を掛けます。

## Common Pitfalls & Tips
- **必ずストリームを閉じる** – 本番コードでは try‑with‑resources を使ってストリームを自動的にクローズし、ファイルロックを防止します。  
- **アスペクト比を保持** – 故意に歪める場合を除き、幅と高さは同じ係数で掛けます。  
- **DPI を確認** – サイズ変更だけでは DPI は変わりません。別途 DPI を変更したい場合は、リサイズ後に調整してください。  
- **スレッドセーフ** – スレッドごとに新しい `PsDocument` を作成してください。同一インスタンスを共有すると予期しない結果になる可能性があります。  

## Frequently Asked Questions

**Q: このライブラリは他の画像形式にも使えますか？**  
A: いいえ、Aspose.Page は PostScript と EPS ファイル専用です。

**Q: Aspose.Page for Java の無料トライアルはありますか？**  
A: はい、無料トライアルは **[こちら](https://releases.aspose.com/)** から利用できます。

**Q: 追加のヘルプやディスカッションはどこで見つけられますか？**  
A: コミュニティサポートは **[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)** をご覧ください。

**Q: 一時ライセンスはどこで取得できますか？**  
A: 一時ライセンスは **[こちら](https://purchase.aspose.com/temporary-license/)** から取得できます。

**Q: サンプルプロジェクトはありますか？**  
A: はい、ドキュメントは **[こちら](https://reference.aspose.com/page/java/)** にあります。

---

**最終更新日:** 2026-02-07  
**テスト環境:** Aspose.Page for Java 24.12（執筆時点での最新バージョン）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}