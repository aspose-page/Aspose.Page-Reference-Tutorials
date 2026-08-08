---
date: 2026-03-29
description: เรียนรู้วิธีเพิ่มวัตถุโปร่งใสลงในเอกสาร XPS แล้วส่งออก XPS เป็น PDF ด้วย
  Aspose.Page สำหรับ .NET คู่มือแบบขั้นตอนพร้อมเคล็ดลับปฏิบัติ
linktitle: Add Transparent Object to XPS Document
second_title: Aspose.Page .NET API
title: ส่งออก XPS เป็น PDF – เพิ่มวัตถุโปร่งแสงด้วย Aspose.Page
url: /th/net/transparency-effects/add-transparent-object-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ส่งออก XPS เป็น PDF – เพิ่มวัตถุโปร่งแสงด้วย Aspose.Page

## บทนำ

ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีเพิ่มวัตถุโปร่งแสงลงในเอกสาร XPS แล้ว **export XPS to PDF** ด้วย Aspose.Page สำหรับ .NET ความโปร่งแสงสามารถทำให้เอกสารของคุณดูทันสมัยยิ่งขึ้นและช่วยเน้นข้อมูลสำคัญ เราจะเดินผ่านแต่ละขั้นตอน อธิบายเหตุผลเบื้องหลังโค้ด และแสดงวิธีทำงานให้เสร็จโดยการแปลงไฟล์ XPS เป็น PDF เพื่อการแชร์ที่ง่าย

## คำตอบด่วน
- **What does “export XPS to PDF” mean?** การแปลงไฟล์ XPS เป็นไฟล์ PDF พร้อมคงรูปแบบ สี และความโปร่งแสงไว้  
- **Why add transparency first?** วัตถุโปร่งแสงช่วยให้คุณสร้างกราฟิกหลายชั้นที่ดูดีใน PDF สุดท้าย  
- **Do I need a license?** ใช่ จำเป็นต้องมีใบอนุญาต Aspose.Page ที่ถูกต้องสำหรับการใช้งานในผลิตภัณฑ์  
- **Can this run on .NET Core?** แน่นอน – Aspose.Page รองรับ .NET Core, .NET 5/6 และ .NET Framework เต็มรูปแบบ  
- **Where can I find more examples?** ตรวจสอบเอกสาร Aspose.Page และฟอรั่มชุมชนที่ลิงก์ด้านล่าง

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มบทแนะนำ โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

- Aspose.Page for .NET: ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.Page สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

## นำเข้า Namespaces

เพื่อเริ่มต้น ให้เพิ่ม Namespaces ที่จำเป็นในโปรเจกต์ของคุณ:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

ต่อไปเราจะดำเนินการตามคำแนะนำแบบขั้นตอนต่อขั้นตอน.

## ขั้นตอนที่ 1: สร้างเอกสาร XPS ใหม่

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

โค้ดนี้จะเริ่มต้นเอกสาร XPS ใหม่โดยใช้ Aspose.Page สำหรับ .NET.

## ขั้นตอนที่ 2: แสดงความโปร่งแสง

```csharp
// Just to demonstrate transparency
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

บรรทัดเหล่านี้สร้างเส้นทางสีเทาสองเส้นที่จะทำหน้าที่เป็นพื้นหลังสำหรับรูปทรงโปร่งแสงที่เราจะเพิ่มในภายหลัง.

## ขั้นตอนที่ 3: สร้าง Path ด้วยเรขาคณิตสี่เหลี่ยมปิด

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

ที่นี่เราสร้างสี่เหลี่ยมสีน้ำเงิน เนื่องจากเราจะเปลี่ยนความทึบในภายหลัง สี่เหลี่ยมนี้จะแสดงเป็นกึ่งโปร่งแสงใน PDF สุดท้าย.

## ขั้นตอนที่ 4: จัดการ Paths และ Colors

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

เราคลอนสี่เหลี่ยมแรก เพิ่มลงในหน้า และเปลี่ยนสีเติมเป็นสีเขียว สิ่งนี้แสดงให้เห็นว่าการใช้เรขาคณิตที่มีอยู่ซ้ำง่ายแค่ไหน.

## ขั้นตอนที่ 5: คัดลอกและแปลง Paths

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

Path ที่คัดลอกจะถูกเลื่อนลง 300 หน่วยและทาด้วยสีแดง ทำให้ได้เอฟเฟกต์ชั้นซ้อนกัน.

## ขั้นตอนที่ 6: ทำซ้ำและแก้ไข Paths

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

เราใช้ข้อมูลเรขาคณิตจาก `path2` อีกครั้ง ย้ายไปทางขวา และเติมสีสีน้ำเงินอีกครั้ง.

## ขั้นตอนที่ 7: จัดการ Opacity

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

การตั้งค่า `Opacity` เป็น 0.8 ทำให้สี่เหลี่ยมนี้มีความทึบ 80 % แสดงให้เห็นว่าคุณสามารถปรับความโปร่งแสงของแต่ละองค์ประกอบได้อย่างละเอียด.

## ขั้นตอนที่ 8: บันทึกเอกสาร XPS

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

ไฟล์ XPS ตอนนี้ถูกบันทึกพร้อมกับวัตถุโปร่งแสงทั้งหมดที่ได้เพิ่มไว้.  
**Export to PDF:** เพื่อ **export XPS to PDF** เพียงเรียก `doc.Save` อีกครั้งโดยใช้ส่วนขยาย `.pdf` เช่น `doc.Save(dataDir + "TransparentDocument.pdf");`. ความคมชัดของภาพรวม รวมถึงการตั้งค่า opacity จะถูกเก็บไว้ใน PDF ที่ได้.

## ทำไมต้อง export XPS to PDF หลังจากเพิ่มความโปร่งแสง?

- **Universal compatibility:** PDF รองรับอย่างกว้างขวางบนหลายแพลตฟอร์ม ในขณะที่ XPS มีการใช้งานจำกัด  
- **Preserved visual effects:** Aspose.Page รักษาความโปร่งแสง, การไล่สี, และการแปลงเมทริกซ์ให้คงเดิมระหว่างการแปลง  
- **Easy sharing:** PDF สามารถเปิดได้ในเบราว์เซอร์, อุปกรณ์มือถือ, และโปรแกรมอ่านของบุคคลที่สามหลายตัวโดยไม่ต้องใช้ปลั๊กอินเพิ่มเติม

## กรณีการใช้งานทั่วไป

- **Marketing brochures** ที่กราฟิกหลายชั้นให้ความรู้สึกระดับพรีเมี่ยม  
- **Technical diagrams** ที่ต้องการส่วนที่ไฮไลท์โดยไม่ทำให้เลย์เอาต์รก  
- **Report generation** ที่ต้องการวางลายน้ำหรือโลโก้ด้วยความทึบบางส่วน

## เคล็ดลับ & สิ่งที่ควรระวัง

- **Pro tip:** ควรตั้งค่า `Opacity` ระหว่าง 0 และ 1 เสมอ ค่าที่อยู่นอกช่วงนี้จะถูกจำกัดและอาจทำให้ผลลัพธ์ไม่คาดคิด  
- **Performance tip:** การใช้เรขาคณิตซ้ำ (`path2.Data`) ลดการใช้หน่วยความจำเมื่อคุณต้องการรูปทรงที่คล้ายกันหลายรูป  
- **Pitfall:** การบันทึกโดยตรงเป็น PDF หลังจากเพิ่มความโปร่งแสงทำงานได้ทันที แต่หากคุณแก้ไข PDF ด้วยเครื่องมืออื่นในภายหลัง ตัวอ่านเก่าอาจไม่แสดงความทึบอย่างถูกต้อง

## สรุป

การเพิ่มวัตถุโปร่งแสงลงในเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET ให้วิธีที่หลากหลายในการปรับปรุงการนำเสนอภาพ เมื่อไฟล์ XPS ของคุณดูตามที่ต้องการแล้ว คุณสามารถ **export XPS to PDF** ด้วยบรรทัดโค้ดเดียวเดียวกัน โดยคงเอฟเฟกต์ความโปร่งแสงทั้งหมดไว้สำหรับการเผยแพร่อย่างกว้างขวาง.

## คำถามที่พบบ่อย

### Q1: ฉันสามารถใช้ความโปร่งแสงกับวัตถุใดก็ได้ในเอกสาร XPS?
A1: ใช่, ความโปร่งแสงสามารถใช้กับวัตถุต่าง ๆ เช่น paths, shapes, และ images ในเอกสาร XPS.

### Q2: ฉันจะปรับความทึบขององค์ประกอบเฉพาะได้อย่างไร?
A2: คุณสามารถตั้งค่าคุณสมบัติ opacity ของ Fill หรือ Stroke เพื่อปรับความโปร่งแสงขององค์ประกอบเฉพาะได้.

### Q3: Aspose.Page รองรับ .NET Core หรือไม่?
A3: ใช่, Aspose.Page รองรับ .NET Core ทำให้สามารถพัฒนาแบบข้ามแพลตฟอร์มได้.

### Q4: ฉันสามารถ export เอกสาร XPS ไปยังรูปแบบอื่น ๆ ด้วย Aspose.Page ได้หรือไม่?
A4: Aspose.Page มีฟังก์ชันการทำงานเพื่อ export เอกสาร XPS ไปยังรูปแบบต่าง ๆ รวมถึง PDF และรูปภาพ.

### Q5: ฉันจะหาแหล่งสนับสนุนเพิ่มเติมและการสนทนาชุมชนได้จากที่ไหน?
A5: สำหรับการสนับสนุนเพิ่มเติมและการสนทนาชุมชน โปรดเยี่ยมชม [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

### Q6: การแปลงเป็น PDF จะคงการตั้งค่าความโปร่งแสงของฉันไว้หรือไม่?
A6: แน่นอน เมื่อคุณ export XPS to PDF ด้วย Aspose.Page การตั้งค่า opacity และ blend ทั้งหมดจะถูกเก็บไว้.

### Q7: ฉันสามารถประมวลผลหลายไฟล์ XPS เป็น PDF เป็นชุดได้หรือไม่?
A7: ใช่, คุณสามารถวนลูปผ่านคอลเลกชันของไฟล์ XPS และเรียก `doc.Save(...".pdf")` สำหรับแต่ละไฟล์ เพื่อทำการแปลงเป็นชุดได้.

**อัปเดตล่าสุด:** 2026-03-29  
**ทดสอบด้วย:** Aspose.Page 24.12 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}