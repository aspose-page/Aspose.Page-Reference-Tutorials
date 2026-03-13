---
date: 2026-03-13
description: Aspose.Page Java を使用して Java で XPS を JPEG に変換する方法を学びましょう。このステップバイステップガイドでは、Aspose.Page
  Java ライブラリを使って XPS を JPEG に効率的に変換する方法を示します。
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: Aspose.Page Java を使用して Java で XPS を JPEG に変換する方法
url: /ja/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# JavaでAspose.Page Javaを使用してXPSをJPEGに変換する方法

## Aspose.Page Java の紹介
このチュートリアルでは **Aspose.Page Java** ライブラリを使って **XPS を JPEG に変換する方法** を学びます。XPS ファイルを JPEG 画像に変換することは、Web ポータルやデスクトップビューア、メール添付などで文書ページをラスタ画像として表示する必要がある場合に頻繁に求められます。コードの各行を詳しく解説し、設定の意味を説明し、実践的なヒントを共有するので、自信を持ってこの変換パイプラインを自分の Java アプリケーションに組み込むことができます。

## Quick Answers
- **どのライブラリが変換を担当しますか？** Aspose.Page Java  
- **特定のページだけを選択できますか？** はい – `JpegSaveOptions` の `setPageNumbers` を使用します  
- **どの画像品質を制御できますか？** スムージングモード、解像度、JPEG 品質設定  
- **本番環境でライセンスは必要ですか？** はい、商用ライセンスが必要です（無料トライアルあり）  
- **コードは Java 8 と互換性がありますか？** 完全に対応 – API は Java 8 以降で動作します  

## XPS とは何か、なぜ XPS を JPEG に変換するのか
XPS（XML Paper Specification）は PDF に似た固定レイアウト文書形式です。XPS を JPEG に変換すると、サムネイルやメール添付、画像ファイルしか受け付けないシステムとの統合に便利です。JPEG は視覚品質とファイルサイズのバランスが良く、Web ベースのプレビューに最適です。

## 前提条件
以下を事前に用意してください。

- **Java 開発環境** – JDK 8 以上がインストールされ、設定されていること。  
- **Aspose.Page for Java** – 公式サイトから最新ライブラリをダウンロードしてください [here](https://releases.aspose.com/page/java/)。  
- **サンプル XPS ドキュメント** – JPEG 画像に変換したい XPS ファイル。  

## パッケージのインポート
Java ソースファイルに必要なクラスをインポートします。

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## 手順 1: パスを初期化し XPS ドキュメントをロードする
ソース XPS ファイルが格納されているディレクトリを設定し、`XpsDocument` インスタンスを作成します。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **プロのコツ:** `java.nio.file` の `Paths.get()` を使用すると、プラットフォームに依存しないパス処理ができます。

## 手順 2: JPEG 保存オプションを設定する
解像度、スムージング、エクスポートするページなど、JPEG 画像の描画方法を定義します。

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` は印刷に適した高解像度出力を生成します。  
- `setPageNumbers` を使うと、必要なページだけを選択でき、時間とメモリを節約できます。

## 手順 3: レンダリングデバイスを作成する
`ImageDevice` はレンダリングされたページをバイト配列として取得します。

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## 手順 4: XPS ドキュメントを JPEG にレンダリングする
設定したデバイスとオプションを渡して `save` メソッドを呼び出します。

```java
document.save(device, options);
```

この時点で `device` は二次元配列を保持しており、各要素が JPEG エンコードされたページを表します。

## 手順 5: 結果をイテレートしてファイルに書き出す
レンダリングされたページをループし、各バイト配列を個別の JPEG ファイルとして保存します。

```java
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //close the stream
        imageStream.close();
    }
}
```

各ファイルは `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg` という名前になるため、元のドキュメントとページ番号が簡単に判別できます。

## 主な利用ケース
- ドキュメント管理システム向けの **サムネイル生成**。  
- 画像形式しかサポートしない Web アプリケーションへの **ページプレビュー埋め込み**。  
- 大量の XPS アーカイブを **バッチ処理で JPEG に変換**し、アーカイブやレポート用途に利用。  

## よくある問題とトラブルシューティング
| 症状 | 主な原因 | 対策 |
|------|----------|------|
| **空の JPEG ファイル** | 出力ストリームが適切にフラッシュまたはクローズされていない | 内部ループ内で `imageStream.close()` が呼び出されていることを確認してください（例参照）。 |
| **大きな XPS ファイルでメモリ不足** | すべてのページを同時にレンダリングしているため RAM を過剰に消費 | ページを小さなバッチで処理するか、JVM ヒープを増やす（`-Xmx` オプション）。 |
| **ページが欠落** | `setPageNumbers` に目的のページが含まれていない | ページ番号配列が実際の XPS ページインデックス（1 ベース）と一致しているか確認してください。 |

## Frequently Asked Questions

### Q: Aspose.Page は商用プロジェクトで使用できますか？
A: はい、Aspose.Page は商用製品で、ライセンスオプションが用意されています。詳細は [here](https://purchase.aspose.com/buy) をご覧ください。

### Q: 購入前に Aspose.Page を試すことはできますか？
A: はい、無料トライアルを取得できます [here](https://releases.aspose.com/)。

### Q: Aspose.Page のドキュメントはどこで見られますか？
A: ドキュメントは [here](https://reference.aspose.com/page/java/) にあります。

### Q: Aspose.Page のサポートはどこで受けられますか？
A: コミュニティベースのサポートは [Aspose.Page Forum](https://forum.aspose.com/c/page/39) で提供されています。

### Q: テスト用に一時ライセンスは必要ですか？
A: はい、一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

## 結論
これで **Aspose.Page Java** を使った **XPS から JPEG への変換方法** を習得しました。ステップバイステップのガイドに従えば、デスクトップツール、Web サービス、バッチ処理ユーティリティなど、あらゆる Java アプリケーションにこの変換パイプラインを組み込むことができます。プロジェクトの要件に合わせて解像度、ページ選択、画像形式などを自由に試してみてください。

---

**最終更新日:** 2026-03-13  
**テスト環境:** Aspose.Page 24.11 for Java（執筆時点での最新バージョン）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}