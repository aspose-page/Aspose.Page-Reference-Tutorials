---
date: 2025-12-08
description: Tìm hiểu cách tạo ví dụ gradient dạng tròn trong Java PostScript bằng
  Aspose.Page. Hướng dẫn từng bước với mã đầy đủ và khắc phục sự cố.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Ví dụ Gradient dạng tròn: Java PostScript với Aspose.Page'
url: /vi/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ví dụ Gradient Hướng Tia: Java PostScript với Aspose.Page

## Giới thiệu
Trong hướng dẫn này, bạn sẽ xây dựng một **ví dụ gradient hướng tia** cho tài liệu PostScript bằng cách sử dụng Aspose.Page cho Java. Chúng tôi sẽ hướng dẫn từng bước—từ việc thiết lập dự án đến việc vẽ một vòng tròn được tô đầy gradient hướng tia mượt mà—để bạn có thể ngay lập tức thêm các đồ họa bắt mắt vào ứng dụng Java của mình.

## Câu trả lời nhanh
- **Tutorial này tạo gì?** Một tệp PostScript (`.ps`) chứa một vòng tròn được tô đầy gradient hướng tia.  
- **Thư viện nào cần thiết?** Aspose.Page cho Java (phiên bản mới nhất).  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút để có một ví dụ hoạt động.  
- **Có cần giấy phép không?** Cần một giấy phép tạm thời hoặc đầy đủ cho việc sử dụng trong môi trường sản xuất; bản dùng thử miễn phí đủ cho phát triển.  
- **Có thể tái sử dụng mã cho PDF hoặc SVG không?** Có—Aspose.Page hỗ trợ nhiều định dạng đầu ra với ít thay đổi.

## Gradient hướng tia là gì?
Gradient hướng tia chuyển đổi màu từ một điểm trung tâm ra phía ngoài, tạo ra một sự pha trộn tròn trịa, mượt mà. Nó lý tưởng cho các điểm nhấn, nền nút bấm, hoặc bất kỳ hình ảnh nào cần hiệu ứng “ánh sáng” tự nhiên.

## Tại sao nên dùng Aspose.Page cho Gradient hướng tia?
- **Kết xuất độc lập thiết bị** – hoạt động giống nhau trên PostScript, PDF, SVG và các định dạng khác.  
- **Tích hợp đầy đủ Java** – không có mã gốc, chỉ các API Java thuần.  
- **Đầu ra chất lượng cao** – hỗ trợ khử răng cưa và kiểm soát không gian màu.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- Kiến thức cơ bản về lập trình Java.  
- JDK 8 hoặc mới hơn đã được cài đặt trên máy của bạn.  
- Thư viện Aspose.Page cho Java (tải xuống từ [tài liệu Aspose.Page Java](https://reference.aspose.com/page/java/)).  

## Nhập các gói
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

## Bước 1: Thiết lập thư mục tài liệu
Xác định thư mục nơi tệp PostScript được tạo sẽ được lưu. Thay thế phần giữ chỗ bằng một đường dẫn thực tế trên hệ thống của bạn.

```java
String dataDir = "Your Document Directory";
```

## Bước 2: Tạo luồng đầu ra
Mở một `FileOutputStream` trỏ tới tệp `.ps` mục tiêu. Luồng này sẽ nhận dữ liệu nhị phân do Aspose.Page tạo ra.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Bước 3: Tạo tùy chọn lưu
Khởi tạo `PsSaveOptions`. Bạn có thể tùy chỉnh kích thước trang, nén, v.v., nhưng các giá trị mặc định đã đủ cho ví dụ này.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Bước 4: Tạo tài liệu PS
Tạo đối tượng `PsDocument`, truyền luồng đầu ra và tùy chọn lưu. Tham số `false` cho biết Aspose.Page không tự động mở một trang (chúng ta sẽ làm điều đó thủ công).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Bước 5: Tạo một vòng tròn
Chúng ta sẽ vẽ một vòng tròn bằng `Ellipse2D.Float`. Các tham số là `(x, y, width, height)`. Đặt `width = height` sẽ tạo ra một vòng tròn hoàn hảo.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Bước 6: Xác định màu gradient
Chuẩn bị hai mảng: một cho các màu sẽ xuất hiện trong gradient và một cho các vị trí phân số tương ứng (0 = trung tâm, 1 = cạnh).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Bước 7: Tạo AffineTransform
`AffineTransform` sẽ thu phóng và dịch chuyển gradient để vừa với vòng tròn của chúng ta. Ma trận `(scaleX, 0, 0, scaleY, translateX, translateY)` thực hiện công việc này.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Bước 8: Tạo Radial Gradient Paint
Bây giờ chúng ta xây dựng đối tượng `RadialGradientPaint`. Nó nhận điểm trung tâm, bán kính, điểm tiêu điểm, các phân số màu, mảng màu, phương pháp lặp, không gian màu và biến đổi chúng ta vừa định nghĩa.

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

## Bước 9: Đặt Paint và tô vòng tròn
Áp dụng gradient paint cho tài liệu và tô vòng tròn đã định nghĩa trước đó. Đây là phần cốt lõi của **ví dụ gradient hướng tia** của chúng ta.

```java
document.setPaint(paint);
document.fill(circle);
```

## Bước 10: Đóng trang và lưu tài liệu
Hoàn thiện trang, ghi nội dung ra đĩa và đóng luồng. Tệp PostScript của bạn đã sẵn sàng để xem bằng bất kỳ trình xem PS nào.

```java
document.closePage();
document.save();
```

Chúc mừng! Bạn đã tạo thành công một ví dụ gradient hướng tia trong Java PostScript bằng Aspose.Page.

## Vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|---------|----------|
| **FileNotFoundException** khi mở luồng đầu ra | Kiểm tra `dataDir` trỏ tới một thư mục tồn tại và bạn có quyền ghi. |
| Gradient trông phẳng hoặc thiếu | Đảm bảo mảng `fractions` có độ dài bằng mảng `colors` và `AffineTransform` được thu phóng đúng. |
| Màu sắc bị đảo ngược | Đổi thứ tự các màu trong mảng `colors` hoặc điều chỉnh tọa độ của điểm `focus`. |

## Câu hỏi thường gặp

**Q: Tôi có thể tìm tài liệu cho Aspose.Page cho Java ở đâu?**  
A: Tham khảo đầy đủ API tại [đây](https://reference.aspose.com/page/java/).

**Q: Làm sao để tải Aspose.Page cho Java?**  
A: Tải JAR mới nhất từ [trang phát hành](https://releases.aspose.com/page/java/).

**Q: Có bản dùng thử miễn phí không?**  
A: Có—tải phiên bản dùng thử [tại đây](https://releases.aspose.com/).

**Q: Tôi có thể lấy giấy phép tạm thời để thử nghiệm không?**  
A: Chắc chắn, yêu cầu một giấy phép tạm thời từ [trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể nhận hỗ trợ cộng đồng ở đâu?**  
A: Tham gia thảo luận trên [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39).

## Kết luận
Trong hướng dẫn này, chúng ta đã xây dựng một **ví dụ gradient hướng tia** hoàn chỉnh cho tài liệu PostScript bằng Aspose.Page cho Java. Bằng cách làm theo các bước, bạn giờ đã có một mẫu có thể tái sử dụng để tạo các gradient tinh vi, có thể áp dụng cho PDF, SVG hoặc các định dạng hỗ trợ khác. Hãy thử nghiệm với các màu sắc, bán kính và hình dạng khác nhau để làm phong phú dự án đồ họa Java của bạn.

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}