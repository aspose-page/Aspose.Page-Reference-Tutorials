---
date: 2026-02-13
description: Tìm hiểu cách tô hình dạng bằng gradient và vẽ vòng tròn bằng gradient
  trong Java PostScript sử dụng Aspose.Page. Hướng dẫn từng bước kèm mã và mẹo.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Đổ hình dạng bằng gradient: Ví dụ Radial Java PostScript'
url: /vi/java/postscript-gradient-addition/radial2/
weight: 13
---

". We'll choose "với".

Introduction translation.

Quick Answers bullet translations.

How to Fill Shape with Gradient in PostScript translation.

What Is a Radial Gradient? translation.

Why Use Aspose.Page for Radial Gradients? bullet translations.

Prerequisites translation.

Import Packages translation.

Step headings translation.

How to Draw Circle with Gradient translation.

Step 6 etc.

Step 10 translation.

Congratulations translation.

Common Issues table translation.

FAQ translation.

Conclusion translation.

Now produce final markdown.

Be careful not to translate code block placeholders.

Let's craft.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đổ Hình với Gradient: Ví dụ Radial Java PostScript

## Introduction
Trong hướng dẫn này, bạn sẽ học cách **đổ hình bằng gradient** bằng cách xây dựng một ví dụ gradient radial cho tài liệu PostScript sử dụng Aspose.Page cho Java. Chúng tôi sẽ hướng dẫn từng bước—từ việc thiết lập dự án đến việc vẽ một vòng tròn được đổ bằng gradient radial mượt mà—để bạn có thể ngay lập tức thêm các đồ họa bắt mắt vào ứng dụng Java của mình.

## Quick Answers
- **What does this tutorial create?** Một tệp PostScript (`.ps`) chứa một vòng tròn được đổ bằng gradient radial.  
- **Which library is required?** Aspose.Page cho Java (phiên bản mới nhất).  
- **How long does implementation take?** Khoảng 10‑15 phút để có một ví dụ hoạt động.  
- **Do I need a license?** Cần có giấy phép tạm thời hoặc đầy đủ cho việc sử dụng trong môi trường sản xuất; bản dùng thử miễn phí đủ cho phát triển.  
- **Can I reuse the code for PDF or SVG?** Có—Aspose.Page hỗ trợ nhiều định dạng đầu ra với ít thay đổi.

## How to Fill Shape with Gradient in PostScript
Trước khi đi vào mã, hãy làm rõ tại sao “đổ hình bằng gradient” lại quan trọng. Sử dụng gradient giúp đồ họa của bạn có cảm giác chuyên nghiệp, ba‑chiều mà không cần đến ảnh raster. Với Aspose.Page, bạn có thể áp dụng cùng một logic gradient cho bất kỳ hình vector nào—vòng tròn, hình chữ nhật, hoặc đường dẫn tùy chỉnh—trên tất cả các định dạng đầu ra được hỗ trợ (PostScript, PDF, SVG).

## What Is a Radial Gradient?
Gradient radial chuyển đổi màu từ một điểm trung tâm ra phía ngoài, tạo ra một sự pha trộn tròn mượt mà. Nó lý tưởng cho các điểm nhấn, nền nút bấm, hoặc bất kỳ hình ảnh nào cần hiệu ứng “ánh sáng” tự nhiên.

## Why Use Aspose.Page for Radial Gradients?
- **Device‑independent rendering** – hoạt động giống nhau trên PostScript, PDF, SVG và các định dạng khác.  
- **Full Java integration** – không cần mã gốc, chỉ sử dụng các API Java thuần.  
- **High‑quality output** – hỗ trợ khử răng cưa và kiểm soát không gian màu.

## Prerequisites
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

- Kiến thức cơ bản về lập trình Java.  
- JDK 8 hoặc mới hơn được cài đặt trên máy tính.  
- Thư viện Aspose.Page cho Java (tải xuống từ [tài liệu Aspose.Page Java](https://reference.aspose.com/page/java/)).  

## Import Packages
Đầu tiên, nhập các lớp mà chúng ta sẽ cần. Những lớp này bao gồm các kiểu đồ họa AWT tiêu chuẩn và API của Aspose.Page.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Set Up Document Directory
Xác định thư mục nơi tệp PostScript được tạo sẽ được lưu. Thay thế phần giữ chỗ bằng một đường dẫn thực tế trên hệ thống của bạn.

```java
String dataDir = "Your Document Directory";
```

## Step 2: Create Output Stream
Mở một `FileOutputStream` trỏ tới tệp `.ps` mục tiêu. Luồng này sẽ truyền dữ liệu nhị phân do Aspose.Page tạo ra.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Step 3: Create Save Options
Khởi tạo `PsSaveOptions`. Bạn có thể tùy chỉnh kích thước trang, nén, v.v., nhưng các giá trị mặc định đã đủ cho ví dụ này.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Step 4: Create PS Document
Tạo đối tượng `PsDocument`, truyền luồng xuất và các tùy chọn lưu. Tham số `false` thông báo cho Aspose.Page không tự động mở một trang (chúng ta sẽ làm thủ công).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 5: Create a Circle
Chúng ta sẽ vẽ một vòng tròn bằng `Ellipse2D.Float`. Các tham số là `(x, y, width, height)`. Đặt `width = height` tạo ra một vòng tròn hoàn hảo.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## How to Draw Circle with Gradient
Bây giờ chúng ta đã có hình, bước tiếp theo là **vẽ vòng tròn bằng gradient**. Bằng cách áp dụng một `RadialGradientPaint` cho vòng tròn, thao tác đổ sẽ tự động sử dụng gradient mà chúng ta định nghĩa.

## Step 6: Define Gradient Colors
Chuẩn bị hai mảng: một cho các màu sẽ xuất hiện trong gradient và một cho các vị trí phân đoạn tương ứng (0 = trung tâm, 1 = cạnh).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Step 7: Create AffineTransform
`AffineTransform` sẽ thu phóng và dịch chuyển gradient để vừa với vòng tròn của chúng ta. Ma trận `(scaleX, 0, 0, scaleY, translateX, translateY)` thực hiện công việc này.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Step 8: Create Radial Gradient Paint
Bây giờ chúng ta xây dựng đối tượng `RadialGradientPaint`. Nó nhận các tham số: điểm trung tâm, bán kính, điểm tiêu điểm, các phân đoạn màu, mảng màu, phương pháp lặp, không gian màu và phép biến đổi chúng ta vừa định nghĩa.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Step 9: Set Paint and Fill Circle
Áp dụng gradient paint cho tài liệu và đổ vòng tròn đã định nghĩa trước đó. Đây là phần cốt lõi của **ví dụ gradient radial** và minh họa cách **đổ hình bằng gradient**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Step 10: Close Page and Save Document
Hoàn thiện trang, ghi nội dung ra đĩa và đóng luồng. Tệp PostScript của bạn đã sẵn sàng để xem bằng bất kỳ trình xem PS nào.

```java
document.closePage();
document.save();
```

Congratulations! You have successfully created a radial gradient example in Java PostScript using Aspose.Page. You now have a reusable pattern for **fill shape with gradient** that can be adapted to other shapes and output formats.

## Common Issues and Solutions
| Problem | Solution |
|---------|----------|
| **FileNotFoundException** when opening the output stream | Xác minh rằng `dataDir` trỏ tới một thư mục tồn tại và bạn có quyền ghi. |
| Gradient looks flat or missing | Đảm bảo mảng `fractions` có độ dài bằng mảng `colors` và `AffineTransform` được thu phóng đúng. |
| Colors appear inverted | Đổi thứ tự các màu trong mảng `colors` hoặc điều chỉnh tọa độ của điểm `focus`. |

## Frequently Asked Questions

**Q: Where can I find the documentation for Aspose.Page for Java?**  
A: The full API reference is available [here](https://reference.aspose.com/page/java/).

**Q: How can I download Aspose.Page for Java?**  
A: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).

**Q: Is there a free trial available?**  
A: Yes—download a trial version [here](https://releases.aspose.com/).

**Q: Can I obtain a temporary license for testing?**  
A: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Where can I get community support?**  
A: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

## Conclusion
Trong hướng dẫn này, chúng ta đã xây dựng một **ví dụ gradient radial** hoàn chỉnh cho tài liệu PostScript sử dụng Aspose.Page cho Java. Bằng cách thực hiện các bước, bạn giờ đã có một mẫu có thể tái sử dụng cho **đổ hình bằng gradient**, có thể áp dụng cho PDF, SVG hoặc bất kỳ định dạng nào khác được Aspose.Page hỗ trợ. Hãy thử nghiệm với các màu sắc, bán kính và hình dạng khác nhau để làm phong phú dự án đồ họa Java của bạn.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}