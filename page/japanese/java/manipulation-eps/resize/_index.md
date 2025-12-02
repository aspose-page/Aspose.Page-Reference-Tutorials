---
date: 2025-12-02
description: Aspose.Page を使用して、Java で EPS ファイルを簡単にリサイズする方法を学びましょう。このステップバイステップガイドでは、ポイント、インチ、ミリメートル、またはパーセンテージを使って
  EPS をリサイズする方法を示します。
language: ja
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Aspose.Page を使用した Java での EPS ファイルのリサイズ方法
url: /java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java と Aspose.Page を使用した EPS ファイルのサイズ変更方法

## はじめに
プログラムで **EPS のサイズ変更方法** を信頼できる手段で探しているなら、ここが最適です。このチュートリアルでは、Aspose.Page ライブラリを使用して Java で EPS 画像のサイズを変更する手順を解説します。サイズを倍にしたい、特定の寸法に縮小したい、またはパーセンテージで調整したい場合でも、以下の手順で出力サイズを完全にコントロールできます。

## クイック回答
- **必要なライブラリは？** Aspose.Page for Java  
- **ポイント、インチ、ミリメートルのいずれかでサイズ変更できますか？** はい – API はこれら3つの単位とパーセンテージをサポートしています。  
- **開発にライセンスは必要ですか？** テストには無料トライアルで動作しますが、本番環境ではライセンスが必要です。  
- **必要な Java バージョンは？** Java 8 以降。  
- **コードはスレッドセーフですか？** 各 `PsDocument` インスタンスは独立しているため、ファイルを並列に処理できます。

## 前提条件
以下を事前に用意してください。

- マシンに Java Development Kit (JDK) がインストールされていること。  
- Aspose.Page for Java ライブラリ。**[here](https://releases.aspose.com/page/java/)** からダウンロードできます。  
- Java プログラミングの基本的な理解があること。  

## パッケージのインポート
Java プロジェクトに必要なインポートを追加し、Aspose.Page のオブジェクトと標準 I/O ストリームを使用できるようにします。

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## ポイント単位で EPS をサイズ変更する方法
以下は、ポイントを測定単位として使用し、EPS ファイルのサイズを倍にする完全なステップバイステップの例です。

### 手順 1: 入力ストリームの設定
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### 手順 2: `PsDocument` オブジェクトの初期化
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### 手順 3: EPS 画像の現在サイズを取得
```java
Dimension oldSize = doc.extractEpsSize();
```

### 手順 4: リサイズ後のファイル用出力ストリームの作成
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### 手順 5: ポイント単位で EPS をリサイズして保存
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## インチ単位で EPS をサイズ変更する方法
同じ5ステップのパターンが適用されます。`Units.Points` を `Units.Inches` に置き換え、必要に応じてスケーリング係数を調整してください。

## ミリメートル単位で EPS をサイズ変更する方法
同様に手順を踏み、単位を `Units.Millimeters` に置き換えます。印刷ワークフローでメートル法の寸法が必要な場合に便利です。

## パーセンテージ単位で EPS をサイズ変更する方法
パーセンテージベースのスケーリングの場合は、単位を `Units.Percent` のままにします。元の幅と高さに希望のパーセンテージ（例: 50 % 減少なら `0.5`）を掛けます。

## よくある落とし穴とヒント
- **常にストリームを閉じる** – 本番コードでは、ファイルロックを防ぐために try‑with‑resources でストリームをラップしてください。  
- **アスペクト比を保持** – 歪みさせる意図がない限り、幅と高さの両方を同じ係数で掛けます。  
- **DPI を確認** – リサイズしても DPI は変わりません。別の DPI が必要な場合は、リサイズ後に個別に調整してください。  

## 結論
これで、ポイント、インチ、ミリメートル、またはパーセンテージのいずれを使用しても、Java と Aspose.Page を使った **EPS のサイズ変更方法** が分かりました。この柔軟性により、EPS の操作を自動化パイプライン、デスクトップユーティリティ、またはサーバーサイドサービスに組み込むことができます。

## よくある質問

**Q: このライブラリを他の画像形式に使用できますか？**  
A: いいえ、Aspose.Page は PostScript と EPS ファイル専用に特化しています。

**Q: Aspose.Page for Java の無料トライアルはありますか？**  
A: はい、無料トライアルは **[here](https://releases.aspose.com/)** で確認できます。

**Q: 追加のヘルプやディスカッションはどこで見つけられますか？**  
A: コミュニティサポートは **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** をご利用ください。

**Q: 一時ライセンスはどのように取得できますか？**  
A: 一時ライセンスは **[here](https://purchase.aspose.com/temporary-license/)** から取得できます。

**Q: サンプルプロジェクトはありますか？**  
A: はい、ドキュメントは **[here](https://reference.aspose.com/page/java/)** で確認できます。

---

**最終更新日:** 2025-12-02  
**テスト環境:** Aspose.Page for Java 24.12 (執筆時点での最新バージョン)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}