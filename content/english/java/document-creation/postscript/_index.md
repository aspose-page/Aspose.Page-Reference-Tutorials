---
title: Create Document in Java with PostScript
linktitle: Create Document in Java with PostScript
second_title: Aspose.Page Java API
description: Effortlessly create PostScript documents in Java using Aspose.Page. Customize page size, margins, and fonts. Try the free trial now!
type: docs
weight: 10
url: /java/document-creation/postscript/
---
## Introduction
In the realm of Java development, creating and managing documents is a crucial aspect. With the advent of Aspose.Page for Java, the process becomes not only efficient but also flexible. This tutorial aims to guide you through the steps of creating a document in Java with PostScript using Aspose.Page, ensuring that you harness the full power of this tool.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites:
- A working knowledge of Java programming.
- Aspose.Page for Java installed. You can download it [here](https://releases.aspose.com/page/java/).
- Necessary fonts stored in a designated folder. For instance, create a 'necessary_fonts' directory in your document directory.
## Import Packages
In your Java project, import the required Aspose.Page packages:
```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
Now, let's break down the example into multiple steps for a seamless understanding.
## Step 1: Set Document Directory
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
Replace "Your Document Directory" with the actual path where you want to save your documents.
## Step 2: Define Fonts Folder
```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```
Ensure you have the necessary fonts stored in this folder.
## Step 3: Create Output Stream for PostScript Document
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```
This step establishes the output stream for the PostScript document, setting the file name accordingly.
## Step 4: Create Save Options with A4 Size
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```
Customize the save options based on your document requirements, specifying page size and orientation.
## Step 5: Set Page Margins and Additional Fonts Folders
```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```
Adjust page margins and include additional font folders if fonts are stored outside the system folders.
## Step 6: Create a Multipaged or Single Paged PS Document
```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```
Determine whether your resulting PostScript document will be multipaged or single paged and create the document accordingly.
## Step 7: Close Current Page and Save Document
```java
document.closePage();
document.save();
```
Complete the document creation process by closing the current page and saving the document.
This step-by-step guide ensures you can seamlessly create a document in Java with PostScript using Aspose.Page, unlocking the potential of this powerful tool.
## Conclusion
Mastering document creation in Java becomes effortless with Aspose.Page. This tutorial provides a comprehensive guide to navigate through the process, enabling you to harness the full capabilities of this library.
## FAQs
### Can I use custom fonts in my PostScript document?
Yes, you can. Ensure to set the additional fonts folder in the save options.
### Is there a trial version available for Aspose.Page for Java?
Yes, you can get a free trial [here](https://releases.aspose.com/).
### How can I access the documentation for Aspose.Page for Java?
Refer to the official documentation [here](https://reference.aspose.com/page/java/).
### Where can I purchase a license for Aspose.Page for Java?
You can buy a license [here](https://purchase.aspose.com/buy).
### Is there a forum for Aspose.Page discussions?
Yes, you can join the community [forum](https://forum.aspose.com/c/page/39) for discussions and support.
