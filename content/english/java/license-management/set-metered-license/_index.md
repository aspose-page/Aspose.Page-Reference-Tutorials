---
title: Effortless Metered License Integration with Aspose.Page Java
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
description: Explore the seamless integration of Aspose.Page with Java. Set up metered licenses effortlessly and enhance your document processing capabilities.
type: docs
weight: 10
url: /java/license-management/set-metered-license/
---
## Introduction
Welcome to our comprehensive guide on setting up a metered license in Java using Aspose.Page. If you're looking to enhance your document processing capabilities and ensure seamless integration with Aspose.Page, you're in the right place. In this tutorial, we'll walk you through the process, breaking down each step into easily digestible chunks.
## Prerequisites
Before diving into the tutorial, make sure you have the following prerequisites in place:
- Basic knowledge of Java programming.
- Aspose.Page library installed. You can download it from [here](https://releases.aspose.com/page/java/).
- Metered public and private keys, which you can obtain through your Aspose account.
## Import Packages
Let's start by importing the necessary packages for our Java program. Ensure you have the Aspose.Page library integrated into your project.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## Step 1: Initialize Document and Image Format
The first step is to set up the document and define the desired image format.
```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## Step 2: Initialize PostScript Input Stream
In this step, we initialize the PostScript input stream for processing.
```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## Step 3: Check Document License
Before proceeding, it's crucial to verify if the document is properly licensed.
```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## Step 4: Initialize Options and Image Device
Now, let's initialize options and the image device with default parameters.
```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## Step 5: Save EPS File as Image
Save the EPS file as an image using the defined options and device.
```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## Step 6: Get and Save Image Bytes
Retrieve image bytes and save them to a file.
```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## Conclusion
Congratulations! You've successfully set up a metered license in Java using Aspose.Page. This tutorial provided a step-by-step guide to ensure a smooth integration process.
## FAQs
### Q: How do I obtain metered public and private keys?
You can obtain these keys through your Aspose account.
### Q: Is the Aspose.Page library free?
Aspose.Page offers both free trial and paid versions. Visit [here](https://releases.aspose.com/) for a free trial.
### Q: Can I use Aspose.Page for commercial projects?
Yes, Aspose.Page offers commercial licenses. You can purchase them [here](https://purchase.aspose.com/buy).
### Q: Where can I find additional documentation?
Refer to the official documentation [here](https://reference.aspose.com/page/java/).
### Q: How can I get temporary licenses?
Temporary licenses can be obtained [here](https://purchase.aspose.com/temporary-license/).
