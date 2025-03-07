---
title: Java で画像を EPS として保存
linktitle: Java で画像を EPS として保存
second_title: Aspose.Page Java API
description: 画像を EPS として簡単に保存できる Aspose.Page for Java の機能を試してください。この多用途 Java ライブラリを使用して、グラフィックスと印刷機能を強化します。
weight: 12
url: /ja/java/postscript-conversion/save-image-as-eps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java で画像を EPS として保存

## 導入
Java プログラミングの世界では、Aspose.Page for Java は、画像をさまざまな形式で操作および保存するための強力なツールとして浮上しています。その多用途な機能の中には、プロのグラフィックスや印刷で広く使用されている形式である Encapsulated PostScript (EPS) ファイルとして画像を保存する機能があります。
このチュートリアルでは、Aspose.Page for Java を使用して画像を EPS として保存するプロセスについて説明します。前提条件、必要なパッケージのインポートについて説明し、各ステップを詳細に説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
1.  Java 開発キット (JDK): Aspose.Page for Java には、動作する JDK がシステムにインストールされている必要があります。最新のJDKをダウンロードできます[ここ](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Page for Java ライブラリ: Aspose.Page for Java ライブラリがあることを確認してください。そうでない場合は、リリースからダウンロードしてください[ページ](https://releases.aspose.com/page/java/).
## パッケージのインポート
前提条件を設定したら、必要なパッケージを Java プロジェクトにインポートします。コードに次の行を追加します。
```java
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//デフォルトのオプションを作成する
PsSaveOptions options = new PsSaveOptions();
```
これらの行はドキュメント ディレクトリを設定し、画像を EPS として保存するためのデフォルト オプションを作成します。
ここで、チュートリアルの導入部で提供されているコード スニペットを、明確かつ簡潔なガイドとして複数のステップに分割してみましょう。
## ステップ 1: ドキュメント ディレクトリを設定する
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
```
「Your Document Directory」を、出力 EPS ファイルを保存する実際のパスに置き換えます。
## ステップ 2: 保存オプションを作成する
```java
//デフォルトのオプションを作成する
PsSaveOptions options = new PsSaveOptions();
```
このステップでは、画像を EPS として保存するためのデフォルトのオプションを初期化します。これらのオプションは要件に基づいてカスタマイズできます。
## ステップ 3: 画像を EPS として保存する
```java
//JPEG画像をEPSファイルに保存
PsDocument.saveImageAsEps(dataDir + "input1.jpg", dataDir + "output1.eps", options);
```
この最後のステップでは、コードは Aspose.Page ライブラリを利用して、入力画像 (この場合は「input1.jpg」) を「output1.eps」という名前の EPS ファイルとして指定されたディレクトリに保存します。
独自のイメージ ファイル パスとディレクトリ情報を使用して、これらの手順を繰り返します。
## 結論
おめでとう！ Aspose.Page を使用して Java で画像を EPS として保存する方法を学習しました。この強力な機能により、Java アプリケーション内で高度なグラフィックス機能と印刷機能への扉が開かれます。
 Aspose.Page for Java のその他の機能については、以下を参照して自由に探索してください。[ドキュメンテーション](https://reference.aspose.com/page/java/).
## よくある質問
### Aspose.Page for Java はすべての画像形式と互換性がありますか?
はい、Aspose.Page for Java は幅広い画像形式をサポートしているため、さまざまなアプリケーションに多用途に使用できます。
### EPS 保存オプションをカスタマイズできますか?
絶対に！このチュートリアルではデフォルトのオプションを紹介しますが、特定のニーズに基づいてそれらを変更できます。
### Aspose.Page for Java に関する追加のサポートやディスカッションはどこで見つけられますか?
訪問[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティと関わり、支援を求めます。
### Aspose.Page for Java に利用できる無料トライアルはありますか?
はい、無料トライアルを試すことができます[ここ](https://releases.aspose.com/).
### Aspose.Page for Java の一時ライセンスを取得するにはどうすればよいですか?
仮免許を取得する[ここ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
