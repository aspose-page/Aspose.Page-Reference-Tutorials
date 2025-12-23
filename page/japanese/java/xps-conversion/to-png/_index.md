---
date: 2025-12-23
description: Aspose.Page を使用して Java で XPS を **PNG に変換** できます。このガイドでは、信頼性が高く開発者に優しいソリューションで
  XPS を画像ファイルにレンダリングする方法を示します。
linktitle: Convert XPS to PNG in Java
second_title: Aspose.Page Java API
title: JavaでXPSをPNGに変換
url: /ja/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java で XPS を PNG に変換

## はじめに
ソフトウェア開発のダイナミックな世界では、**XPS を PNG に変換**（XML Paper Specification から Portable Network Graphics への変換）の必要性が頻繁に生じます。このタスクを Java でシームレスに実行するために、Aspose.Page が強力なソリューションを提供します。本チュートリアルでは、Aspose.Page for Java を使用して XPS を PNG に変換する手順を解説します。

## クイック回答
- **変換を処理するライブラリは何ですか？** Aspose.Page for Java  
- **対象となるフォーマットは何ですか？** XPS（ソース） → PNG（出力）  
- **本番環境でライセンスは必要ですか？** はい、商用ライセンスが必要です  
- **画像解像度を設定できますか？** はい、`PngSaveOptions.setResolution()` を使用します  
- **特定のページだけを選択できますか？** もちろんです – オプションオブジェクトでページ番号を指定します  

## なぜ XPS を PNG に変換するのか？
XPS を画像ファイルにレンダリングすると、Web 上で文書を表示したり、レポートに埋め込んだり、プレビュー用のサムネイルを生成したりする際に便利です。PNG はロスレス圧縮と広範なブラウザサポートを提供し、XPS コンテンツの高品質なビジュアル表現に最適です。

## 前提条件
チュートリアルに入る前に、以下の環境が整っていることを確認してください：
1. **Java Development Kit (JDK)**: システムに JDK がインストールされていること。  
2. **Aspose.Page for Java**: Aspose.Page ライブラリをダウンロードしてインストールします。ダウンロードリンクは[こちら](https://releases.aspose.com/page/java/)です。  
3. **統合開発環境 (IDE)**: IntelliJ IDEA や Eclipse など、Java に対応した IDE を選択してください。  

## Java で XPS を PNG に変換する方法
以下は、**XPS 文書を PNG 画像に変換**する手順をステップバイステップで示したガイドです。コードスニペットはそのままプロジェクトにコピーして使用できます。

### パッケージのインポート
Java プロジェクトで Aspose.Page の機能を利用するために、必要なパッケージをインポートします。Java ファイルの先頭に次のインポート文を追加してください。

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

### ステップ 1: ドキュメントディレクトリの設定
ソース XPS ファイルが格納されているフォルダと、PNG ファイルを保存するフォルダを定義します。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### ステップ 2: XPS ドキュメントの読み込み
`XpsDocument` インスタンスを作成し、ソース XPS ファイルを読み込みます。

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### ステップ 3: オプションの初期化
PNG 出力オプションを構成します。ここでスムージング、解像度、レンダリングするページを指定できます。

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### ステップ 4: レンダリングデバイスの作成
レンダリングされた画像データを保持する `ImageDevice` を作成します。

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

### ステップ 5: 保存とイテレーション
XPS ドキュメントをレンダリングし、生成された PNG バイト配列をディスク上のファイルに書き込みます。

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

これらの手順に従うことで、Aspose.Page for Java を使用して XPS を PNG 形式の画像ファイルに簡単に **レンダリング** できます。

## 結論
まとめると、Aspose.Page for Java は XPS から PNG への変換プロセスを簡素化し、開発者に信頼性と効率性を提供します。このライブラリを Java プロジェクトに組み込むことで、文書操作タスクをスムーズに行えます。

## よくある質問

### 商用プロジェクトで Aspose.Page for Java を使用できますか？
はい、Aspose.Page は商用製品です。ライセンス情報は[こちら](https://purchase.aspose.com/buy)で確認できます。

### 無料トライアルは利用可能ですか？
はい、無料トライアルは[こちら](https://releases.aspose.com/)から入手できます。

### Aspose.Page for Java のドキュメントはどこで見つけられますか？
包括的なドキュメントは[こちら](https://reference.aspose.com/page/java/)にあります。

### テスト目的の一時ライセンスはどのように取得しますか？
一時ライセンスは[こちら](https://purchase.aspose.com/temporary-license/)から取得できます。

### Aspose.Page のディスカッション用コミュニティフォーラムはありますか？
はい、コミュニティフォーラムは[こちら](https://forum.aspose.com/c/page/39)です。

## 追加のよくある質問

**Q: XPS ファイルの特定のページだけを変換できますか？**  
**A:** もちろんです。`PngSaveOptions` の `setPageNumbers` メソッドを使用して、レンダリングしたいページを指定してください。

**Q: 高品質な PNG の推奨画像解像度はどれくらいですか？**  
**A:** 300 dpi が品質とファイルサイズのバランスとして一般的に推奨されますが、`options.setResolution()` で自由に調整できます。

**Q: 大規模文書のマルチスレッド変換はサポートされていますか？**  
**A:** はい、各スレッドで異なるページまたは文書のパーティションを処理する形で、変換ロジックを並列実行できます。

**Q: 非常に大きな XPS ファイルを変換する際のメモリ使用量はどう管理すればよいですか？**  
**A:** ページを順次処理し、各書き込み後に `FileOutputStream` を解放することでメモリ消費を抑えられます（サンプルコード参照）。

**Q: 生成された PNG ファイルにカスタムメタデータを追加する方法はありますか？**  
**A:** `PngSaveOptions` では直接メタデータフィールドを公開していませんが、標準の画像ライブラリを使用して PNG を後処理し、メタデータを埋め込むことが可能です。

---

**最終更新日:** 2025-12-23  
**テスト環境:** Aspose.Page for Java 24.12（最新）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}