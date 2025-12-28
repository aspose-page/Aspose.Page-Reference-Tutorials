---
date: 2025-12-28
description: Aspose.Page を使用して Java で XPS ドキュメントに画像を追加する方法を学びましょう。このステップバイステップガイドでは、画像を簡単に追加し、ドキュメント処理を強化する方法を示します。
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: Java XPSドキュメントに画像を追加する方法 – Aspose.Pageによるシンプルガイド
url: /ja/java/xps-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page を使用した Java XPS ドキュメントへの画像追加方法

XPS ファイルに画像を追加することは、レポートや請求書、その他のビジュアルドキュメントを充実させる必要がある Java 開発者にとって一般的な要件です。このチュートリアルでは、強力な Aspose.Page for Java ライブラリを使用して **画像を追加する方法** を学びます。各手順を順に解説し、各行の意味を説明し、典型的な落とし穴を回避するためのヒントを提供します。

## Quick Answers
- **What library is needed?** Aspose.Page for Java  
- **Can I add multiple images?** Yes – repeat the image‑adding steps for each picture  
- **Supported image formats?** TIFF, JPEG, PNG, GIF (and others supported by .NET)  
- **Do I need a license?** A free trial works for evaluation; a commercial license is required for production  
- **Typical implementation time?** About 10‑15 minutes for a basic image insertion

## Introduction
画像を XPS ドキュメントに追加することは、多くの Java アプリケーションで一般的な要件です。レポート生成からドキュメント処理まで、さまざまなシナリオで利用されます。Aspose.Page for Java はこの作業を簡素化し、画像を XPS ファイルにシームレスに統合するための効率的なメソッドを提供します。本チュートリアルでは、Aspose.Page for Java を使用して XPS ドキュメントに画像を追加する手順を示します。

## Prerequisites
チュートリアルに入る前に、以下の前提条件が整っていることを確認してください。
1. **Aspose.Page for Java Library** – Download and install the Aspose.Page for Java library from the [website](https://releases.aspose.com/page/java/).  
2. **Java Development Environment** – Ensure that you have a Java development environment set up on your machine.

Now, let's move on to the next steps.

## Import Packages
In your Java project, import the necessary Aspose.Page for Java packages to access the required classes and methods.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```

## Step 1: Set Up Document Directory
Define the path to your document directory where the XPS document and image files will be stored.

```java
String dataDir = "Your Document Directory";
```

## Step 2: Create a New XPS Document
Initialize a new XPS document using the following code snippet:

```java
XpsDocument doc = new XpsDocument();
```

## Step 3: Add Image to XPS Document
To add an image, create a path in the XPS document, and set the image brush using the provided image file and coordinates.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```

## Step 4: Save Resultant XPS Document
Save the modified XPS document to your specified directory.

```java
doc.save(dataDir + "AddImage_out.xps");
```

Repeat these steps to add more images or customize the existing ones according to your project requirements.

## Conclusion
Congratulations! You've successfully learned **how to add image** to an XPS document using Aspose.Page for Java. This skill is invaluable for enhancing the visual appeal of your Java applications and documents.

### Frequently Asked Questions
### Can I add multiple images to the same XPS document using Aspose.Page for Java?
Yes, you can add multiple images by repeating the steps outlined in this tutorial for each image.

### What image formats are supported by Aspose.Page for Java?
Aspose.Page for Java supports various image formats, including TIFF, JPEG, PNG, and GIF.

### Is there a trial version of Aspose.Page for Java available?
Yes, you can obtain a free trial of Aspose.Page for Java from [this link](https://releases.aspose.com/).

### How can I get a temporary license for Aspose.Page for Java?
You can obtain a temporary license from [this link](https://purchase.aspose.com/temporary-license/).

### Where can I find additional support or discuss issues related to Aspose.Page for Java?
Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to seek help, share experiences, and connect with the Aspose.Page community.

## Additional Tips & Common Pitfalls
- **Path Geometry Accuracy** – Ensure the SVG‑style path string matches the dimensions of your image; otherwise the image may appear stretched or clipped.  
- **Image Brush Scaling** – The `createImageBrush` method takes source and destination rectangles; tweaking these values lets you control positioning and scaling precisely.  
- **License Activation** – If you run the code without a valid license, Aspose will add a watermark to the generated XPS file.

---

**Last Updated:** 2025-12-28  
**Tested With:** Aspose.Page for Java 23.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}