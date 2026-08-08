---
date: 2026-05-15
description: เรียนรู้วิธีแก้ไขเมตาดาต้า XMP และวิธีเปลี่ยนค่า XMP ในไฟล์ EPS ด้วย
  Aspose.Page for Java – คู่มือขั้นตอนที่ชัดเจน
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: เปลี่ยน Named Value ใน XMP ด้วย Java
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: วิธีแก้ไข XMP – การเปลี่ยน Named Value ใน XMP ด้วย Java
url: /th/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแก้ไข xmp – เปลี่ยนค่าที่ตั้งชื่อใน XMP ด้วย Java

ในกระบวนการทำงานเอกสารสมัยใหม่, **Aspose.Page for Java** ทำให้การอ่าน, แก้ไข, และเขียนเมตาดาต้า XMP ภายในไฟล์ EPS เป็นเรื่องง่าย. **บทแนะนำนี้แสดงวิธีแก้ไข xmp** เมตาดาต้าในเอกสาร EPS ด้วย Aspose.Page API, เพื่อให้ข้อมูลเอกสารของคุณแม่นยำ, ค้นหาได้, และสอดคล้องกับมาตรฐานอุตสาหกรรม. ไม่ว่าคุณจะอัปเดตขนาดหน้า, ข้อมูลผู้เขียน, หรือแท็กที่กำหนดเอง, ขั้นตอนต่อไปนี้จะพาคุณผ่านกระบวนการใน Java.

## คำตอบอย่างรวดเร็ว
- **บทแนะนำนี้ครอบคลุมอะไร?** การเปลี่ยนค่าที่ตั้งชื่อใน XMP ภายในไฟล์ EPS ด้วย Aspose.Page for Java.  
- **ต้องการเวอร์ชันของไลบรารีใด?** เวอร์ชันล่าสุดของ Aspose.Page for Java (API มีความเสถียรมาหลายปี).  
- **ต้องการใบอนุญาตหรือไม่?** จำเป็นต้องมีใบอนุญาตชั่วคราวหรือเต็มสำหรับการใช้งานจริง; การทดลองใช้ฟรีสามารถใช้สำหรับการทดสอบ.  
- **การดำเนินการใช้เวลานานเท่าไหร่?** ประมาณ 10‑15 นาทีสำหรับนักพัฒนาที่คุ้นเคยกับ Java I/O.  
- **ฉันสามารถใช้กับรูปแบบไฟล์อื่นได้หรือไม่?** API ของ XMP ยังพร้อมใช้งานสำหรับ PDF, SVG, และรูปแบบไฟล์อื่นที่สนับสนุนโดย Aspose.Page.

## XMP metadata คืออะไร?
XMP (Extensible Metadata Platform) คือรูปแบบมาตรฐานที่ใช้ XML สำหรับฝังเมตาดาต้าที่มีความละเอียดสูง—เช่น ผู้สร้าง, ชื่อเรื่อง, และคุณสมบัติกำหนดเอง—โดยตรงในไฟล์. ในเอกสาร EPS, XMP อยู่ร่วมกับคอมเมนต์ PostScript แบบดั้งเดิม, ทำให้แอปพลิเคชันสามารถอ่านและแก้ไขเมตาดาต้าโดยไม่กระทบเนื้อหาภาพ.

## ทำไมต้องใช้ Aspose.Page for Java เพื่อแก้ไข XMP?
Aspose.Page ให้คุณ **การควบคุมเต็มรูปแบบเหนือกว่า 150 คุณสมบัติของสกีม่า XMP** และทำงานอย่างสม่ำเสมอบนรูปแบบ EPS, PDF, และ SVG. มันประมวลผลไฟล์ขนาดสูงสุด **500 MB** โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ, และรวมการตรวจสอบความถูกต้องในตัวที่รับประกันว่า EPS ที่ได้จะสอดคล้องกับมาตรฐาน. ไม่จำเป็นต้องใช้ตัวแยกวิเคราะห์ XML ภายนอกหรือไลบรารีเนทีฟ.

## บทนำ
Aspose.Page for Java เป็นไลบรารีที่แข็งแกร่งซึ่งช่วยอำนวยการจัดการและประมวลผลไฟล์ EPS. เมื่อพูดถึงการจัดการเมตาดาต้า XMP ภายในไฟล์เหล่านี้, Aspose.Page มอบพลังให้กับนักพัฒนาด้วยชุดคุณสมบัติที่ครบถ้วน. ในบทแนะนำนี้, เราจะเน้นการเปลี่ยนค่าที่ตั้งชื่อใน XMP, ให้คำแนะนำที่ชัดเจนและกระชับสำหรับนักพัฒนาที่ต้องการเพิ่มศักยภาพการประมวลผลเอกสารของตน.

## ข้อกำหนดเบื้องต้น
Before diving into the tutorial, ensure you have the following prerequisites in place:
1. **Java Development Environment** – JDK (8 หรือสูงกว่า) และ IDE หรือเครื่องมือสร้าง (Maven/Gradle).  
2. **Aspose.Page for Java Library** – ดาวน์โหลดและรวมไลบรารี Aspose.Page for Java เข้ากับโปรเจกต์ของคุณ. คุณสามารถค้นหาไลบรารีและเอกสารรายละเอียดได้ที่ [here](https://reference.aspose.com/page/java/).  
3. **Sample EPS File** – เตรียมไฟล์ EPS ตัวอย่างสำหรับการทดลอง. หากคุณไม่มีไฟล์, ใช้ไฟล์ตัวอย่างที่ให้มาชื่อ **"xmp4.eps."**

## นำเข้าแพ็กเกจ
The `import` statements bring the essential Aspose.Page classes into scope.

คลาส `PsDocument` เป็นอ็อบเจกต์หลักของ Aspose.Page ที่แทนเอกสาร EPS ในหน่วยความจำ.  
คลาส `XmpMetadata` ให้การเข้าถึงแพ็กเกจ XMP ที่ฝังอยู่ในไฟล์ EPS.  

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## วิธีแก้ไขเมตาดาต้า XMP?
โหลดไฟล์ EPS, ดึงแพ็กเกจ XMP ของมัน, แก้ไขคุณสมบัติที่ต้องการ, และบันทึกเอกสาร—ทั้งหมดในไม่กี่บรรทัดที่ง่าย. วิธีนี้ทำงานกับค่าที่ตั้งชื่อใน XMP ใด ๆ ไม่ว่าจะเป็นฟิลด์มาตรฐานของ Dublin Core หรือเนมสเปซที่กำหนดเองของคุณ.

## ขั้นตอนที่ 1: เริ่มต้นสตรีมไฟล์ EPS อินพุต
`FileInputStream` เปิดสตรีมแบบอ่านอย่างเดียวไปยังไฟล์ EPS ต้นทาง, ทำให้ Aspose.Page สามารถดึงข้อมูลเอกสารได้โดยไม่ล็อกระบบไฟล์.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## ขั้นตอนที่ 2: เริ่มต้น PsDocument
`PsDocument` เป็นอ็อบเจกต์หลักที่บรรจุเนื้อหา EPS และให้การเข้าถึงเมตาดาต้า, หน้า, และทรัพยากรของมัน.

```java
PsDocument document = new PsDocument(psStream);
```

## ขั้นตอนที่ 3: ดึงเมตาดาต้า XMP
`XmpMetadata` แทนแพ็กเกจ XMP ภายในไฟล์ EPS และมีเมธอดสำหรับอ่าน, แก้ไข, หรือ ลบคุณสมบัติเฉพาะ.

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## ขั้นตอนที่ 4: ตั้งค่ใหม่ใน XMP
`setProperty` ตั้งค่าของคุณสมบัติ XMP ที่ระบุในแพ็กเกจเมตาดาต้า.

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## ขั้นตอนที่ 5: เริ่มต้นสตรีมไฟล์ EPS เอาต์พุต
`FileOutputStream` สร้างสตรีมที่สามารถเขียนได้สำหรับบันทึกไฟล์ EPS ที่แก้ไข.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## ขั้นตอนที่ 6: บันทึกเอกสารพร้อมเมตาดาต้า XMP ที่เปลี่ยนแปลง
`save` เขียน PsDocument ที่อยู่ในหน่วยความจำ, รวมถึง XMP ที่อัปเดต, ไปยังสตรีมเอาต์พุต.

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## ขั้นตอนที่ 7: ปิดสตรีมไฟล์ EPS อินพุต
`close` ปล่อยแฮนด์เดิลไฟล์และคืนทรัพยากรที่เกี่ยวข้องกับสตรีมอินพุต.

```java
// Close input EPS stream
psStream.close();
```

## ปัญหาทั่วไปและวิธีแก้
- **FileNotFoundException** – ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่ถูกต้องและว่า `xmp4.eps` มีอยู่.  
- **LicenseException** – หากพบข้อผิดพลาดเกี่ยวกับใบอนุญาต, ตรวจสอบให้แน่ใจว่าไฟล์ใบอนุญาต Aspose.Page ที่ถูกต้องได้ถูกโหลดก่อนสร้าง `PsDocument`.  
- **Metadata Not Updated** – หลังจากบันทึก, เปิดไฟล์ EPS ที่ได้ในโปรแกรมดูเมตาดาต้า (เช่น Adobe Bridge) เพื่อยืนยันว่าค่าที่ใหม่ปรากฏ.

## คำถามที่พบบ่อย
**Q: ฉันสามารถใช้ Aspose.Page for Java กับภาษาโปรแกรมอื่นได้หรือไม่?**  
A: Aspose.Page รองรับ Java เป็นหลัก, แต่ Aspose มีไลบรารีที่เทียบเท่าสำหรับ .NET, C++, และ Python ที่ให้ความสามารถการจัดการ XMP ที่คล้ายกัน.

**Q: มีการทดลองใช้ฟรีสำหรับ Aspose.Page for Java หรือไม่?**  
A: มี, คุณสามารถสำรวจการทดลองใช้ฟรีของ Aspose.Page for Java ได้ที่ [here](https://releases.aspose.com/).

**Q: ฉันจะหาแหล่งสนับสนุนและการสนทนาเพิ่มเติมเกี่ยวกับ Aspose.Page for Java ได้จากที่ไหน?**  
A: เยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชนและการสนทนา.

**Q: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?**  
A: คุณสามารถรับใบอนุญาตชั่วคราวได้ที่ [here](https://purchase.aspose.com/temporary-license/).

**Q: ฉันสามารถซื้อ Aspose.Page for Java ได้จากที่ไหน?**  
A: เพื่อซื้อ Aspose.Page for Java, เยี่ยมชม [purchase page](https://purchase.aspose.com/buy).

---

**อัปเดตล่าสุด:** 2026-05-15  
**ทดสอบด้วย:** Aspose.Page for Java (latest release)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีอ่านเมตาดาต้า XMP ด้วย Java – คู่มือ Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [บทแนะนำ Aspose Page Java – เพิ่มเมตาดาต้า XMP ไปยังไฟล์ EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page modify xmp – เปลี่ยนค่าใน XMP ด้วย Java](/page/java/xmp-metadata-manipulation/change-values/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}