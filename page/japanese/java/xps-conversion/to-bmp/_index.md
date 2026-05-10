---
date: 2026-03-08
description: JavaでXPSをBMPに変換し、Aspose.Page Java画像変換ライブラリを使用してBMPの解像度を設定する方法を学びます。このガイドでは、高品質な出力とメモリに優しいヒントを紹介します。
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: JavaでXPSをBMPに変換 – 高品質出力のために解像度を設定
url: /ja/java/xps-conversion/to-bmp/
weight: 10
---

 items: The code block placeholders are fine.

Make sure to preserve markdown formatting.

Let's craft final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# JavaでXPSをBMPに変換する

## はじめに
このステップバイステップガイドへようこそ。Javaで**XPSをBMPに変換**し、Aspose.Pageを使用して最適な画像品質のために解像度を設定する方法をご紹介します。印刷パイプラインの構築、サムネイルの生成、または高解像度グラフィックが必要な場合でも、DPI を制御することであらゆる要件に柔軟に対応できます。

## クイック回答
- **どのライブラリを使用すべきですか？** Aspose.Page for Java は XPS → BMP 用の最も完全な **java image conversion library** です。  
- **画像品質を制御できますか？** はい – `BmpSaveOptions` を使用して **set BMP resolution** とスムージングモードを設定します。  
- **大きな XPS ファイルを処理するときに Java の OutOfMemoryError を回避するには？** ページを分割してレンダリングするか、JVM ヒープ (`-Xmx`) を増やします。  
- **特定のページだけを変換する必要がありますか？** もちろん、`options.setPageNumbers()` を使用すれば正確なページを選択できます。  
- **サポートされている Java バージョンは？** すべての最新 Java バージョン（8 以上）でシームレスに動作します。

## 解像度を設定する目的は何ですか？
解像度は生成された BMP 画像の 1 インチあたりのドット数 (DPI) を決定します。DPI が高いほど画像は鮮明になり、印刷や詳細なグラフィック作業に不可欠です。解像度を調整することで、**convert xps to bmp** ワークフローの出力品質を完全にコントロールできます。

## XPS → BMP 変換に Aspose.Page を使用する理由は？
- **高忠実度** – 元の XPS のベクター品質を保持します。  
- **細かい制御** – DPI、スムージング、さらには変換する特定のページを選択できます。  
- **外部依存なし** – 純粋な Java で、ネイティブライブラリは不要です。  
- **スケーラブル** – 単一ページのドキュメントから大規模なマルチページ XPS ファイルまで対応します。  

## 前提条件
変換プロセスに入る前に、以下の前提条件が揃っていることを確認してください。

- **Java 開発環境** – マシンに Java 8 以上がインストールされていること。  
- **Aspose.Page for Java ライブラリ** – Aspose.Page for Java ライブラリをダウンロードし、プロジェクトに組み込んでください。ライブラリは[こちら](https://releases.aspose.com/page/java/)で入手できます。  
- **サンプル XPS ファイル** – BMP に変換したいサンプル XPS ドキュメントを用意してください。

## パッケージのインポート
Java コードに必要な Aspose.Page パッケージをインクルードします。

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## XPS を BMP に変換する際の解像度設定方法
以下は、解像度の設定場所と方法、さらに **特定のページを変換** する方法を示す簡潔な番号付き手順です。

### ステップ 1: XPS ドキュメントのロード
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### ステップ 2: オプションの初期化（解像度とページ選択）
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### ステップ 3: レンダリングデバイスの作成
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### ステップ 4: オプションを使用してドキュメントを保存
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### ステップ 5: レンダリングされた画像を反復処理し、ファイルを書き込む
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

変換プロセスで必要な追加のカスタマイズや変更がある場合は、これらの手順を繰り返してください。

## 大きな XPS ファイルを変換するときに Java の OutOfMemoryError を回避する方法
- **パーティションで処理** – この例ではすでにドキュメントをパーティション (`device.getResult()`) に分割してレンダリングしており、メモリ負荷が軽減されます。  
- **JVM ヒープを増やす** – `-Xmx` フラグ（例: `-Xmx2g`）を使用して、大きなドキュメント用にメモリを割り当てます。  
- **リソースを解放** – 終了時に `document.close()` を呼び出してネイティブリソースを解放します。

## 一般的な問題と解決策
| 問題 | 解決策 |
|-------|----------|
| **低品質 BMP 出力** | `options.setResolution()` が 300 DPI 以上に設定されていることを確認してください。 |
| **ドキュメントの一部しか変換されない** | `options.setPageNumbers()` に必要なすべてのページインデックスが含まれていることを確認してください。 |
| **大きな XPS ファイルで OutOfMemoryError が発生** | ドキュメントを小さなパーティションに分割して処理するか、JVM ヒープサイズ (`-Xmx`) を増やしてください。 |
| **ファイルが見つかりません** | `dataDir` パスと入力 XPS ファイルが存在するかを再確認してください。 |

## よくある質問
### Q: BMP 画像の解像度をカスタマイズできますか？
A: はい、コード内の `options.setResolution()` パラメータを変更することで解像度を調整できます。

### Q: Aspose.Page はさまざまな Java バージョンと互換性がありますか？
A: はい、Aspose.Page は幅広い Java バージョンをサポートしています。互換性のあるバージョンがインストールされていることを確認してください。

### Q: 特定のページ範囲の XPS ファイルを変換するには？
A: `options.setPageNumbers()` メソッドを使用して、変換したいページ番号を指定してください。

### Q: Aspose.Page がサポートする他の出力形式はありますか？
A: はい、Aspose.Page はさまざまな出力形式をサポートしています。包括的な一覧はドキュメントをご参照ください。

### Q: 追加のヘルプやサポートはどこで得られますか？
A: コミュニティサポートやディスカッションは [Aspose.Page Forum](https://forum.aspose.com/c/page/39) をご覧ください。

---

**最終更新日:** 2026-03-08  
**テスト環境:** Aspose.Page for Java 24.12  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}