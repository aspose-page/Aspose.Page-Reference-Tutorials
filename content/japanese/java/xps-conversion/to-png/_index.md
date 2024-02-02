---
title: Java で XPS を PNG に変換する
linktitle: Java で XPS を PNG に変換する
second_title: Aspose.Page Java API
description: Aspose.Page を使用して Java で XPS を PNG に簡単に変換します。この信頼性が高く開発者にとって使いやすいソリューションを使用して、ドキュメント タスクを合理化します。
type: docs
weight: 13
url: /ja/java/xps-conversion/to-png/
---
## 導入
ソフトウェア開発のダイナミックな世界では、XPS (XML Paper Specific) ドキュメントを PNG (Portable Network Graphics) 画像に変換する必要性が頻繁に発生します。 Java でこのタスクをシームレスに実行するために、Aspose.Page は強力なソリューションを提供します。このチュートリアルでは、Aspose.Page for Java を使用して XPS を PNG に変換するプロセスを説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が設定されていることを確認してください。
1. Java Development Kit (JDK): システムに JDK がインストールされていることを確認してください。
2.  Aspose.Page for Java: Aspose.Page ライブラリをダウンロードしてインストールします。ダウンロードリンクが見つかります[ここ](https://releases.aspose.com/page/java/).
3. 統合開発環境 (IDE): IntelliJ IDEA や Eclipse などの Java 互換 IDE を選択します。
## パッケージのインポート
Java プロジェクトで、Aspose.Page 機能を利用するために必要なパッケージをインポートします。 Java ファイルの先頭に次の import ステートメントを追加します。
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## ステップ 1: ドキュメント ディレクトリを設定する
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
```
## ステップ 2: XPS ドキュメントをロードする
```java
//XPSドキュメントをロードする
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## ステップ 3: オプションを初期化する
```java
//必要なパラメータを使用してオプション オブジェクトを初期化します。
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## ステップ 4: レンダリング デバイスを作成する
```java
//PDF 形式用のレンダリング デバイスを作成する
ImageDevice device = new ImageDevice();
```
## ステップ 5: 保存して反復する
```java
//オプションとデバイスを使用して XPS ドキュメントを PNG に保存
document.save(device, options);
//ドキュメント パーティション (XPS 用語では固定ドキュメント) を反復処理します。
for (int i = 0; i < device.getResult().length; i++) {
    //パーティションページを反復処理する
    for (int j = 0; j < device.getResult()[i].length; j++) {
        //画像出力ストリームを初期化する
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        //画像の書き込み
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //ストリームを閉じる
        imageStream.close();
    }
}
```
これらの手順に従うと、Aspose.Page for Java を使用して XPS ドキュメントを PNG イメージに簡単に変換できます。
## 結論
結論として、Aspose.Page for Java は XPS から PNG への変換プロセスを簡素化し、開発者に信頼性の高い効率的なツールを提供します。このライブラリを Java プロジェクトに組み込んで、ドキュメント操作タスクを効率化します。
## よくある質問
### Aspose.Page for Java を商用プロジェクトで使用できますか?
はい、Aspose.Page は商用製品です。ライセンス情報を見つけることができます[ここ](https://purchase.aspose.com/buy).
### 無料トライアルはありますか?
はい、無料トライアルを試すことができます[ここ](https://releases.aspose.com/).
### Aspose.Page for Java のドキュメントはどこで見つけられますか?
包括的なドキュメントが利用可能です[ここ](https://reference.aspose.com/page/java/).
### テスト目的で一時ライセンスを取得するにはどうすればよいですか?
仮免許が取得できる[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Page ディスカッションのためのコミュニティ フォーラムはありますか?
はい、コミュニティ フォーラムにアクセスしてください[ここ](https://forum.aspose.com/c/page/39).