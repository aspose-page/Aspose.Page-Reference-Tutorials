---
date: 2025-12-08
description: Tìm hiểu cách thêm các mẫu vân vào tài liệu Java PostScript bằng Aspose.Page
  Java. Hướng dẫn từng bước này cho bạn thấy cách thêm đồ họa mẫu vân một cách hiệu
  quả.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: Thêm mẫu vạch chéo trong PostScript Java'
url: /vi/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm Mẫu Hatch trong PostScript Java

## Giới thiệu
Nếu bạn đang làm việc với **Aspose.Page Java** và cần làm phong phú đầu ra PostScript của mình bằng các đồ họa có kết cấu, các mẫu hatch là giải pháp nhanh chóng và linh hoạt. Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn **cách thêm hatch** vào tài liệu PostScript, giải thích tại sao chúng hữu ích, và cung cấp một ví dụ mã hoàn chỉnh, sẵn sàng chạy. Khi kết thúc, bạn sẽ có thể tạo các hình dạng và văn bản được tô đầy hatch một cách trực quan chỉ với vài dòng Java.

## Câu trả lời nhanh
- **Thư viện tôi cần là gì?** Aspose.Page for Java (SDK “aspose page java”).  
- **Hiệu ứng hình ảnh chúng ta đang thêm là gì?** Các mẫu hatch (ví dụ: đường chéo, crosshatch).  
- **Có cần giấy phép để chạy mẫu không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép cần thiết cho môi trường sản xuất.  
- **Có bao nhiêu dòng mã?** Khoảng 70 dòng, chia thành các bước rõ ràng.  
- **Tôi có thể dùng cùng cách tiếp cận cho PDF không?** Có — Aspose.Page hỗ trợ nhiều định dạng đầu ra, bao gồm PDF.

## Yêu cầu trước
- **Môi trường phát triển Java** – JDK 8 trở lên và một IDE bạn thích.  
- **Thư viện Aspose.Page for Java** – Tải JAR mới nhất từ trang chính thức [here](https://releases.aspose.com/page/java/).  
- **Quyền ghi** vào thư mục nơi file PostScript sẽ được lưu.

## Nhập gói
Đầu tiên, đưa các lớp cần thiết vào dự án của bạn. Các import này cho phép bạn truy cập các primitive vẽ, xử lý màu và API Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Bước 1: Thiết lập các tham số ban đầu
Tạo luồng xuất, cấu hình kích thước trang (A4), và định nghĩa một vài biến bố cục sẽ được tái sử dụng khi vẽ mỗi ô hình vuông được tô hatch.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Bước 2: Lưu trạng thái đồ họa và dịch chuyển
Lưu trạng thái đồ họa cho phép chúng ta quay lại hệ tọa độ gốc sau này, trong khi `translate` di chuyển gốc tới một điểm bắt đầu thuận tiện.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Bước 3: Tạo hình vuông cho mỗi mẫu
Định nghĩa một hình chữ nhật có thể tái sử dụng để đại diện cho mỗi ô được tô hatch.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Bước 4: Thiết lập bút cho viền hình vuông mẫu
Một `BasicStroke` độ dày 2 point tạo ra viền sắc nét quanh mỗi hình vuông.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Bước 5: Lặp qua các mẫu Hatch
Duyệt qua mọi giá trị trong enum `HatchStyle`, tô mỗi ô bằng kết cấu tương ứng, và sau đó vẽ viền của nó. Đây là phần cốt lõi của chức năng **thêm mẫu hatch**.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Bước 6: Khôi phục trạng thái đồ họa
Quay lại hệ tọa độ gốc sau khi hoàn thành việc vẽ lưới các hình vuông.

```java
document.writeGraphicsRestore();
```

## Bước 7: Đổ màu văn bản bằng mẫu Hatch
Ở đây chúng tôi minh họa cách tô màu văn bản bằng kết cấu hatch. Ví dụ sẽ tô từ “ABC” bằng mẫu chéo‑giao nhau.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Bước 8: Vẽ viền văn bản bằng mẫu Hatch
Bây giờ chúng tôi vẽ viền cho cùng một đoạn văn bản, nhưng lần này sử dụng mẫu hatch 70 % và một nét dày hơn.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Bước 9: Đóng và lưu tài liệu
Hoàn thiện trang, ghi file ra đĩa và giải phóng tài nguyên.

```java
document.closePage();
document.save();
```

Thực hiện các bước này, và bạn sẽ có một file PostScript hiển thị đầy đủ các mẫu hatch được áp dụng cho cả hình dạng và văn bản — tất cả được hỗ trợ bởi **aspose page java**.

## Tại sao nên dùng Hatch Patterns với Aspose.Page Java?
- **Phân biệt trực quan** – Các tô hatch vẫn hoạt động ngay cả khi máy in chỉ hỗ trợ đầu ra đen trắng.  
- **Hiệu năng** – Kết cấu được tạo ra ngay tại thời điểm chạy, giúp tránh các file ảnh lớn.  
- **Hỗ trợ đa định dạng** – Cùng một đoạn mã có thể hướng tới PDF, EPS hoặc SVG với ít thay đổi.

## Những lỗi thường gặp & Mẹo
- **Lỗi đường dẫn file** – Đảm bảo `dataDir` kết thúc bằng dấu phân cách thích hợp (`/` hoặc `\`).  
- **Màu không được hỗ trợ** – Một số trình thông dịch PostScript cũ có thể không xử lý được một số không gian màu; hãy dùng RGB cơ bản để tối đa tương thích.  
- **Cảnh báo giấy phép** – Chạy mẫu mà không có giấy phép hợp lệ sẽ chèn watermark vào đầu ra.

## Kết luận
Áp dụng các mẫu hatch có thể cải thiện đáng kể khả năng đọc và thẩm mỹ của bản vẽ kỹ thuật, bản đồ, hoặc bất kỳ đồ họa nào được tạo bằng Java. Với **Aspose.Page Java**, bạn có một API ngắn gọn trừu tượng các lệnh PostScript mức thấp, cho phép bạn tập trung vào thiết kế thay vì những rắc rối của định dạng file.

## Câu hỏi thường gặp

**Q: Tôi có thể dùng Aspose.Page Java với các framework Java khác không?**  
A: Có, thư viện không phụ thuộc vào framework và hoạt động với Spring, Jakarta EE, Android (giới hạn), và Java SE thuần.

**Q: Có phiên bản dùng thử cho Aspose.Page Java không?**  
A: Chắc chắn. Tải bản dùng thử miễn phí 30 ngày [here](https://releases.aspose.com/).

**Q: Làm sao để lấy giấy phép tạm thời cho phát triển?**  
A: Yêu cầu giấy phép tạm thời [here](https://purchase.aspose.com/temporary-license/). Nó sẽ loại bỏ watermark đánh giá.

**Q: Tôi có thể tìm thêm tutorial và hỗ trợ cộng đồng ở đâu?**  
A: Truy cập diễn đàn chính thức [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) để xem thêm ví dụ và Q&A.

**Q: Có tài liệu đầy đủ cho tất cả các lớp và phương thức không?**  
A: Có, tham khảo đầy đủ API có sẵn [here](https://reference.aspose.com/page/java/).

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
