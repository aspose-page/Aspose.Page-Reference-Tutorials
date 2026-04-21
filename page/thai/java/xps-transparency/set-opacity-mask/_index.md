---
date: 2026-01-02
description: เรียนรู้วิธีเพิ่มมาสก์ความทึบแสงให้กับเอกสาร XPS ด้วย Aspose.Page Java
  คู่มือแบบขั้นตอนต่อขั้นตอนในการสร้างสี่เหลี่ยมมาสก์ความทึบแสงและเพิ่มคุณภาพภาพ
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: ตั้งค่า Opacity Mask ใน Java XPS โดยใช้ Aspose.Page Java
url: /th/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่า Opacity Mask ใน Java XPS โดยใช้ Aspose.Page Java

## บทนำ
Welcome to our comprehensive guide on **aspose page java** opacity masks. In this tutorial you’ll learn how to create an XPS document, add a canvas, and apply an opacity mask to a rectangle—all with the powerful Aspose.Page Java API. By the end you’ll be able to add opacity mask rectangles that give your XPS files a polished, semi‑transparent look.

## คำตอบอย่างรวดเร็ว
- **Opacity mask ทำหน้าที่อะไร?** It defines varying transparency levels for a shape, letting underlying content show through.
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for Java (aspose page java).
- **ต้องการไลเซนส์หรือไม่?** A temporary license works for testing; a full license is required for production.
- **ต้องเขียนโค้ดกี่บรรทัด?** About 20 lines of Java plus a few setup statements.
- **สามารถใช้ mask ซ้ำกับหลายรูปทรงได้หรือไม่?** Yes, you can assign the same ImageBrush to several paths.

## Opacity Mask คืออะไรใน XPS?
An opacity mask is a bitmap or vector that controls the alpha (transparency) of each pixel in a shape. When applied to a rectangle, parts of the rectangle become fully opaque, partially transparent, or fully transparent, creating sophisticated visual effects.

## ทำไมต้องใช้ Aspose.Page Java สำหรับ Opacity Masks?
- **Full .NET‑style API in Java** – intuitive object model.
- **ไม่มีการพึ่งพาภายนอก** – works with pure Java.
- **การเรนเดอร์คุณภาพสูง** – masks render exactly as in the XPS specification.
- **ข้ามแพลตฟอร์ม** – run on Windows, Linux, or macOS without changes.

## ข้อกำหนดเบื้องต้น
- ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java.  
- Aspose.Page for Java library installed. You can download it **[here](https://releases.aspose.com/page/java/)**.  
- ไลเซนส์ที่ใช้งานได้สำหรับ Aspose.Page. If you don’t have one, obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.  
- สภาพแวดล้อมการพัฒนาที่สามารถคอมไพล์และรันแอปพลิเคชัน Java (เช่น IntelliJ IDEA, Eclipse, or VS Code).

## นำเข้าแพ็กเกจ
Start by importing the necessary classes from the Aspose.Page library. This ensures the API is available to your project.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: สร้างเอกสาร XPS ใหม่
First, instantiate a fresh XPS document that will hold all of our graphics.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### ขั้นตอนที่ 2: เพิ่ม Canvas
A canvas acts as a drawing surface inside the XPS page.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### ขั้นตอนที่ 3: เพิ่มสี่เหลี่ยมและใช้การเติมสีทึบ
Here we create a rectangle path and give it a solid red fill. This rectangle will later receive the opacity mask.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### ขั้นตอนที่ 4: เพิ่ม Opacity Mask ด้วย ImageBrush
We load a TIFF image, define source and destination rectangles, and set the brush to tile mode so the mask repeats if needed.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### ขั้นตอนที่ 5: บันทึกเอกสาร XPS ที่ได้
Finally, persist the document to disk. The output file will contain the rectangle with the applied opacity mask.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Follow these steps carefully to incorporate **add opacity mask** functionality into your Java XPS document using Aspose.Page.

## ปัญหาทั่วไปและการแก้ไข
- **ไม่พบภาพ** – Verify that `dataDir` points to the correct folder and that `R08SY_NN.tif` exists.
- **Mask ปรากฏเป็นสีทึบ** – Ensure the source image actually contains varying alpha values; a fully opaque image will not show transparency.
- **โหมด tile ไม่ทำงาน** – The destination rectangle must be smaller than the source rectangle for tiling to be noticeable.

## คำถามที่พบบ่อย

**Q: Aspose.Page รองรับสภาพแวดล้อมการพัฒนา Java ทั้งหมดหรือไม่?**  
A: Yes, Aspose.Page is designed to work seamlessly with various Java IDEs and build tools.

**Q: สามารถใช้ Aspose.Page โดยไม่มีไลเซนส์ได้หรือไม่?**  
A: While you can evaluate the library with a temporary license, a full license is required for production use.

**Q: มีข้อจำกัดใดในเวอร์ชันทดลองหรือไม่?**  
A: The trial may impose size or feature restrictions; consult the official documentation for details.

**Q: จะขอรับการสนับสนุนสำหรับ Aspose.Page อย่างไร?**  
A: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** for community help or purchase a license for premium assistance.

**Q: มีการรับประกันคืนเงินสำหรับ Aspose.Page หรือไม่?**  
A: Refer to the **[purchase page](https://purchase.aspose.com/buy)** for information on refund policies.

---

**อัปเดตล่าสุด:** 2026-01-02  
**ทดสอบด้วย:** Aspose.Page Java 24.11 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}