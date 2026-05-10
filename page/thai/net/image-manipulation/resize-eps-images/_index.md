---
date: 2026-03-03
description: เรียนรู้วิธีปรับขนาดภาพ EPS ใน .NET ด้วย Aspose.Page – คู่มือขั้นตอนต่อขั้นตอนเกี่ยวกับวิธีปรับขนาด
  EPS โดยใช้หน่วยจุด, นิ้ว, มิลลิเมตร หรือเปอร์เซ็นต์
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: วิธีปรับขนาดภาพ EPS ด้วย Aspose.Page สำหรับ .NET
url: /th/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีปรับขนาดภาพ EPS ด้วย Aspose.Page สำหรับ .NET

## บทนำ

คุณกำลังมองหา **วิธีปรับขนาด EPS** อย่างราบรื่นโดยใช้ Aspose.Page สำหรับ .NET หรือไม่? บทเรียนนี้เป็นคู่มือครบวงจรของคุณสำหรับการจัดการขนาดของภาพ EPS อย่างง่ายดายในหน่วยต่าง ๆ เช่น จุด, นิ้ว, มิลลิเมตร, และเปอร์เซ็นต์. Aspose.Page สำหรับ .NET มีชุดเครื่องมือที่ทรงพลัง, และในบทเรียนนี้เราจะพาคุณผ่านขั้นตอนอย่างละเอียด.

## คำตอบสั้น
- **ไลบรารีที่จัดการการปรับขนาด EPS คืออะไร?** Aspose.Page for .NET  
- **หน่วยที่รองรับมีอะไรบ้าง?** Points, Inches, Millimeters, and Percents  
- **ฉันต้องมีใบอนุญาตสำหรับการผลิตหรือไม่?** ใช่ – จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์  
- **ฉันสามารถปรับขนาดหลายไฟล์พร้อมกันได้หรือไม่?** ได้แน่นอน – เพียงวนลูปผ่านไฟล์  
- **รองรับ .NET Core หรือไม่?** ใช่, API ทำงานกับ .NET Framework และ .NET Core  

## การปรับขนาด EPS คืออะไร?
Encapsulated PostScript (EPS) เป็นรูปแบบกราฟิกแบบเวกเตอร์ที่ใช้กันทั่วไปในกระบวนการพิมพ์และการออกแบบ. การปรับขนาดไฟล์ EPS จะเปลี่ยนกล่องขอบโดยไม่ทำให้ภาพเป็น raster, ทำให้คมชัดที่ขนาดใด ๆ

## ทำไมต้องปรับขนาดภาพ EPS?
- **รักษาคุณภาพการพิมพ์:** การสเกลแบบเวกเตอร์ทำให้ขอบคมชัด.  
- **ตอบสนองความต้องการของเลย์เอาต์:** ปรับขนาดให้ตรงกับหน้า หรือขนาดแคนวาส.  
- **อัตโนมัติงานแบช:** ปรับขนาดไฟล์หลายสิบไฟล์โดยอัตโนมัติในไม่กี่วินาที.  

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะลงลึกในเทคนิคการปรับขนาด, ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

- Aspose.Page for .NET Library: ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.Page for .NET แล้ว. คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/page/net/).

- Document Directory: สร้างไดเรกทอรีที่คุณจะเก็บไฟล์ EPS อินพุตและไฟล์ที่ปรับขนาดแล้ว.

เมื่อคุณตั้งค่าทุกอย่างเรียบร้อยแล้ว, ไปที่การนำเข้า namespace ที่จำเป็นและลึกเข้าสู่คู่มือขั้นตอนต่อขั้นตอน.

## นำเข้า Namespaces

ในโครงการ .NET ของคุณ, เริ่มต้นด้วยการนำเข้า namespace ที่จำเป็นสำหรับทำงานกับ Aspose.Page. เพิ่มโค้ดต่อไปนี้ที่ส่วนต้นของไฟล์ของคุณ:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## วิธีปรับขนาด EPS เป็นจุด

จุด (Points) เป็นหน่วยวัดมาตรฐานในอุตสาหกรรมการพิมพ์. ตัวอย่างด้านล่างจะเพิ่มความกว้างและความสูงของต้นฉบับเป็นสองเท่า.

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## วิธีปรับขนาด EPS เป็นนิ้ว

นิ้ว (Inches) ถูกใช้บ่อยโดยนักออกแบบกราฟิกเมื่อเตรียมทรัพยากรสำหรับการพิมพ์.

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## วิธีปรับขนาด EPS เป็นมิลลิเมตร

มิลลิเมตร (Millimeters) เป็นหน่วยที่พบทั่วไปในภูมิภาคที่ใช้ระบบเมตริก.

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## วิธีปรับขนาด EPS ด้วยเปอร์เซ็นต์

การปรับขนาดแบบเปอร์เซ็นต์ทำให้คุณสามารถสเกลภาพตามขนาดต้นฉบับได้.

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

คุณสามารถนำวิธีเหล่านี้ไปใช้ในโครงการของคุณได้อย่างอิสระ, และคุณจะปรับขนาดภาพ EPS ได้อย่างง่ายดาย. ทดลองใช้หน่วยต่าง ๆ เพื่อให้ได้มิติที่ต้องการ.

## ปัญหาที่พบบ่อยและวิธีแก้
- **ไฟล์ไม่พบ:** ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่ถูกต้องและว่า `input.eps` มีอยู่.  
- **ขนาดไม่คาดคิด:** จำไว้ว่า `Units.Percents` ต้องการค่าตัวเลขเช่น 150 สำหรับ 150 % ของขนาดต้นฉบับ.  
- **ข้อยกเว้นใบอนุญาต:** หากคุณเห็นข้อผิดพลาดเกี่ยวกับใบอนุญาต, ตรวจสอบให้แน่ใจว่าไฟล์ใบอนุญาต Aspose.Page ที่ถูกต้องถูกโหลดก่อนสร้าง `PsDocument`.

## สรุป

ขอแสดงความยินดี! คุณได้เชี่ยวชาญ **วิธีปรับขนาด EPS** ด้วย Aspose.Page สำหรับ .NET แล้ว. ไลบรารีที่ทรงพลังนี้เปิดโลกของความเป็นไปได้ในการจัดการกราฟิกเวกเตอร์. ไม่ว่าคุณจะออกแบบเพื่อการพิมพ์หรือสื่อดิจิทัล, Aspose.Page จะช่วยให้คุณได้ผลลัพธ์ที่แม่นยำและปรับแต่งได้ตามต้องการ.

## คำถามที่พบบ่อย

### Q1: ฉันสามารถปรับขนาดหลายภาพ EPS พร้อมกันได้หรือไม่?

A1: ได้, คุณสามารถวนลูปผ่านคอลเลกชันของไฟล์ EPS, แล้วใช้วิธีการปรับขนาดตามที่ต้องการ.

### Q2: Aspose.Page เข้ากันได้กับรูปแบบภาพอื่นหรือไม่?

A2: Aspose.Page มุ่งเน้นที่รูปแบบ PostScript และ EPS เป็นหลัก. สำหรับรูปแบบภาพอื่น, พิจารณาใช้ Aspose.Imaging.

### Q3: มีข้อพิจารณาเรื่องใบอนุญาตสำหรับโครงการเชิงพาณิชย์หรือไม่?

A3: มี, ตรวจสอบให้แน่ใจว่าคุณมีใบอนุญาตที่ถูกต้อง. เยี่ยมชม [here](https://purchase.aspose.com/buy) เพื่อดูรายละเอียดการออกใบอนุญาต.

### Q4: ฉันสามารถทดลองใช้ Aspose.Page ก่อนซื้อได้หรือไม่?

A4: แน่นอน! คุณสามารถรับการทดลองใช้ฟรีได้ที่ [here](https://releases.aspose.com/).

### Q5: ฉันจะหาแนวทางช่วยเหลือเพิ่มเติมหรือหารือเกี่ยวกับปัญหาได้จากที่ไหน?

A5: เยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อเชื่อมต่อกับชุมชนและขอความช่วยเหลือ.

## คำถามที่พบบ่อย

**Q: โค้ดนี้ทำงานกับ .NET Core 6 หรือไม่?**  
A: ใช่. API รองรับ .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, และ .NET 6+.

**Q: ฉันจะรักษาโปรไฟล์สีเดิมได้อย่างไร?**  
A: เมธอด `ResizeEps` ไม่เปลี่ยนแปลงข้อมูลสี; มันเพียงเปลี่ยนกล่องขอบ.

**Q: สามารถปรับขนาด EPS ได้โดยไม่โหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำหรือไม่?**  
A: การใช้สตรีมตามที่แสดงทำให้การใช้หน่วยความจำน้อย; เอกสารถูกประมวลผลแบบ on‑the‑fly.

**Q: ฉันสามารถเชื่อมต่อการดำเนินการปรับขนาดหลายครั้งต่อเนื่องได้หรือไม่?**  
A: แน่นอน. เรียก `ResizeEps` อย่างต่อเนื่องบนอินสแตนซ์ `PsDocument` เดียวกัน.

**Q: สิ่งที่เกิดขึ้นกับภาพที่ฝังอยู่ใน EPS คืออะไร?**  
A: พวกมันจะถูกสเกลอย่างสัดส่วนกับเนื้อหาเวกเตอร์, รักษาคุณภาพ.

---

**อัปเดตล่าสุด:** 2026-03-03  
**ทดสอบด้วย:** Aspose.Page 24.12 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}