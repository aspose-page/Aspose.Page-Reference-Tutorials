---
title: ปรับขนาดภาพ EPS ด้วย Aspose.Page สำหรับ .NET
linktitle: ปรับขนาดภาพ EPS
second_title: Aspose.Page .NET API
description: สำรวจกระบวนการปรับขนาดอิมเมจ EPS ใน .NET ได้อย่างราบรื่นโดยใช้ Aspose.Page ให้ความแม่นยำในระดับจุด นิ้ว มิลลิเมตร และเปอร์เซ็นต์ได้อย่างง่ายดาย
weight: 11
url: /th/net/image-manipulation/resize-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ปรับขนาดภาพ EPS ด้วย Aspose.Page สำหรับ .NET

## การแนะนำ

คุณต้องการปรับขนาดภาพ EPS ได้อย่างราบรื่นโดยใช้ Aspose.Page สำหรับ .NET หรือไม่? บทช่วยสอนนี้เป็นคำแนะนำที่ครอบคลุมของคุณในการจัดการขนาดรูปภาพ EPS ในหน่วยต่างๆ เช่น จุด นิ้ว มิลลิเมตร และเปอร์เซ็นต์ได้อย่างง่ายดาย Aspose.Page สำหรับ .NET มีชุดเครื่องมือที่มีประสิทธิภาพ และในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะดำดิ่งลงสู่ความมหัศจรรย์ในการปรับขนาด ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Page สำหรับ .NET Library: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Page สำหรับ .NET Library แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/page/net/).

- ไดเร็กทอรีเอกสาร: สร้างไดเร็กทอรีที่คุณจะจัดเก็บไฟล์ EPS อินพุตและไฟล์ปรับขนาดเอาต์พุต

เมื่อคุณได้ตั้งค่าทุกอย่างเรียบร้อยแล้ว เรามาดำเนินการนำเข้าเนมสเปซที่จำเป็นและเจาะลึกคำแนะนำทีละขั้นตอนกัน

## นำเข้าเนมสเปซ

ในโปรเจ็กต์ .NET ของคุณ ให้เริ่มด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Page เพิ่มรหัสต่อไปนี้ที่จุดเริ่มต้นของไฟล์ของคุณ:

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

## ขั้นตอนที่ 1: การปรับขนาดเป็นคะแนน

เริ่มต้นด้วยการปรับขนาดภาพ EPS เป็นพอยต์ คะแนนเป็นหน่วยวัดมาตรฐานในอุตสาหกรรมการพิมพ์

```csharp
public static void ResizeInPoints()
{
    // ไดเร็กทอรีเอกสารของคุณ
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

## ขั้นตอนที่ 2: การปรับขนาดเป็นนิ้ว

ตอนนี้ เรามาปรับขนาดรูปภาพ EPS เป็นนิ้ว ซึ่งเป็นหน่วยทั่วไปที่ใช้ในการออกแบบกราฟิก

```csharp
public static void ResizeInInches()
{
    // ไดเร็กทอรีเอกสารของคุณ
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

## ขั้นตอนที่ 3: การปรับขนาดเป็นมิลลิเมตร

ตอนนี้ เรามาปรับขนาดรูปภาพ EPS เป็นหน่วยมิลลิเมตร ซึ่งเป็นหน่วยที่ใช้กันอย่างแพร่หลายในการออกแบบและการพิมพ์

```csharp
public static void ResizeInMillimeters()
{
    // ไดเร็กทอรีเอกสารของคุณ
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

## ขั้นตอนที่ 4: การปรับขนาดเป็นเปอร์เซ็นต์

สุดท้าย เรามาปรับขนาดรูปภาพ EPS โดยใช้เปอร์เซ็นต์ ซึ่งเป็นแนวทางที่ยืดหยุ่นในการปรับขนาดรูปภาพ

```csharp
public static void ResizeInPercents()
{
    // ไดเร็กทอรีเอกสารของคุณ
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

อย่าลังเลที่จะรวมวิธีการเหล่านี้เข้ากับโปรเจ็กต์ของคุณ และคุณจะปรับขนาดภาพ EPS ได้อย่างง่ายดาย ทดลองกับหน่วยต่างๆ เพื่อให้ได้มิติที่ต้องการ

## บทสรุป

ยินดีด้วย! คุณเชี่ยวชาญศิลปะการปรับขนาดภาพ EPS ด้วย Aspose.Page สำหรับ .NET แล้ว ไลบรารีอันทรงพลังนี้เปิดโลกแห่งความเป็นไปได้ในการจัดการกราฟิกแบบเวกเตอร์ ไม่ว่าคุณจะออกแบบสำหรับสิ่งพิมพ์หรือสื่อดิจิทัล Aspose.Page ช่วยให้คุณได้รับผลลัพธ์ที่แม่นยำและปรับแต่งได้

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถปรับขนาดภาพ EPS หลายภาพพร้อมกันได้หรือไม่

A1: ได้ คุณสามารถวนซ้ำคอลเลกชั่นของไฟล์ EPS ได้ โดยใช้วิธีการปรับขนาดตามนั้น

### คำถามที่ 2: Aspose.Page เข้ากันได้กับรูปแบบรูปภาพอื่นหรือไม่

A2: Aspose.Page เน้นที่รูปแบบ PostScript และ EPS เป็นหลัก สำหรับรูปแบบรูปภาพอื่นๆ ให้พิจารณาใช้ Aspose.Imaging

### คำถามที่ 3: มีข้อควรพิจารณาในการออกใบอนุญาตสำหรับโครงการเชิงพาณิชย์หรือไม่

 A3: ใช่ ตรวจสอบให้แน่ใจว่าคุณมีใบอนุญาตที่ถูกต้อง เยี่ยม[ที่นี่](https://purchase.aspose.com/buy) สำหรับรายละเอียดใบอนุญาต

### คำถามที่ 4: ฉันสามารถลองใช้ Aspose.Page ก่อนซื้อได้หรือไม่

 A4: แน่นอน! คุณสามารถทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 5: ฉันจะขอความช่วยเหลือเพิ่มเติมหรือหารือเกี่ยวกับปัญหาได้ที่ไหน

 A5: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อเชื่อมต่อกับชุมชนและรับความช่วยเหลือ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
