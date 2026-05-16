---
date: 2026-02-15
description: Tìm hiểu cách thêm mẫu vạch chéo vào các tệp PostScript Java bằng Aspose.Page
  Java. Hướng dẫn chi tiết này cung cấp mã hoàn chỉnh và các mẹo.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: Cách Thêm Mẫu Đánh Gạch trong Java PostScript bằng Aspose.Page
url: /vi/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Hatch Pattern trong Java PostScript

## Introduction
Nếu bạn đang làm việc với **Aspose.Page Java** và tự hỏi **cách thêm hatch pattern** vào đầu ra PostScript của mình, hatch pattern là một giải pháp nhanh và linh hoạt. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn **cách thêm hatch** thiết kế vào tài liệu PostScript, giải thích tại sao chúng hữu ích, và cung cấp cho bạn một ví dụ mã hoàn chỉnh, sẵn sàng chạy. Khi kết thúc, bạn sẽ có thể tạo các hình dạng và văn bản được tô đầy hatch một cách hấp dẫn chỉ với vài dòng Java.

## Quick Answers
- **Thư viện tôi cần là gì?** Aspose.Page for Java (SDK “aspose page java”).  
- **Hiệu ứng hình ảnh chúng ta đang thêm là gì?** Hatch pattern (ví dụ: đường chéo, chéo chéo).  
- **Tôi có cần giấy phép để chạy mẫu không?** Bản dùng thử miễn phí hoạt động cho phát triển; cần giấy phép cho môi trường sản xuất.  
- **Có bao nhiêu dòng mã?** Khoảng 70 dòng, chia thành các bước rõ ràng.  
- **Tôi có thể dùng cùng cách cho PDF không?** Có—Aspose.Page hỗ trợ nhiều định dạng đầu ra, bao gồm PDF.

## How to Add Hatch Pattern – Overview
Hatch pattern là các kết cấu dựa trên vector mà hiển thị sạch sẽ ở bất kỳ độ phân giải nào và hoạt động tốt trên máy in monochrome. Sử dụng Aspose.Page Java, bạn có thể áp dụng các mẫu này cho hình dạng, đường dẫn và thậm chí văn bản mà không cần xử lý các lệnh PostScript cấp thấp.

## Prerequisites
- **Môi trường phát triển Java** – JDK 8 trở lên và IDE bạn chọn.  
- **Thư viện Aspose.Page for Java** – Tải JAR mới nhất từ trang chính thức [here](https://releases.aspose.com/page/java/).  
- **Quyền ghi** vào thư mục nơi tệp PostScript được tạo sẽ được lưu.

## Import Packages
Đầu tiên, đưa các lớp cần thiết vào dự án của bạn. Các import này cho phép bạn truy cập vào các primitive vẽ, xử lý màu và API Aspose.Page.

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

## Step 1: Set Up Initial Parameters
Tạo luồng đầu ra, cấu hình kích thước trang (A4), và định nghĩa một vài biến bố cục sẽ được tái sử dụng khi vẽ mỗi ô vuông được tô hatch.

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

## Step 2: Save Graphics State and Translate
Lưu trạng thái đồ họa cho phép chúng ta quay lại hệ tọa độ gốc sau, trong khi `translate` di chuyển gốc tới một điểm bắt đầu thuận tiện.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Step 3: Create Square for Each Pattern
Định nghĩa một hình chữ nhật có thể tái sử dụng để đại diện cho mỗi ô được tô hatch.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Step 4: Set Up Pen for Pattern Square Outline
Một `BasicStroke` 2 point tạo đường viền sắc nét quanh mỗi ô vuông.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Step 5: Iterate Through Hatch Patterns
Lặp qua mọi giá trị trong enum `HatchStyle`, tô mỗi ô vuông bằng kết cấu tương ứng, sau đó vẽ đường viền của nó. Đây là phần cốt lõi của chức năng **thêm hatch pattern**.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Step 6: Restore Graphics State
Quay lại hệ tọa độ gốc sau khi chúng ta hoàn thành việc vẽ lưới các ô vuông.

```java
document.writeGraphicsRestore();
```

## Step 7: Fill Text with Hatch Pattern
Ở đây chúng tôi minh họa cách tô màu văn bản bằng kết cấu hatch. Ví dụ này tô từ “ABC” bằng mẫu chéo‑cắt.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Step 8: Outline Text with Hatch Pattern
Bây giờ chúng tôi vẽ đường viền cho cùng một văn bản, nhưng lần này sử dụng kiểu hatch 70 % và nét dày hơn.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Step 9: Close and Save Document
Hoàn thiện trang, ghi tệp ra đĩa và giải phóng tài nguyên.

```java
document.closePage();
document.save();
```

Thực hiện các bước này, bạn sẽ có một tệp PostScript hiển thị đầy đủ các hatch pattern được áp dụng cho cả hình dạng và văn bản—tất cả đều được hỗ trợ bởi **aspose page java**.

## Why Use Hatch Patterns with Aspose.Page Java?
- **Khác biệt về hình ảnh** – Hatch fill hoạt động ngay cả khi máy in chỉ hỗ trợ đầu ra monochrome.  
- **Hiệu suất** – Kết cấu được tạo ra ngay lập tức, vì vậy bạn tránh các tệp ảnh lớn.  
- **Hỗ trợ đa định dạng** – cùng một đoạn mã có thể tạo PDF, EPS hoặc SVG với ít thay đổi.

## Common Pitfalls & Tips
- **Lỗi đường dẫn tệp** – Đảm bảo `dataDir` kết thúc bằng ký tự phân tách tệp thích hợp (`/` hoặc `\`).  
- **Màu không được hỗ trợ** – Một số trình thông dịch PostScript cũ có thể không xử lý một số không gian màu; hãy dùng RGB cơ bản để tương thích tối đa.  
- **Cảnh báo giấy phép** – Chạy mẫu mà không có giấy phép hợp lệ sẽ chèn watermark vào đầu ra.

## Conclusion
Việc tích hợp hatch pattern có thể cải thiện đáng kể khả năng đọc và thẩm mỹ của bản vẽ kỹ thuật, bản đồ, hoặc bất kỳ đồ họa nào được tạo bằng Java. Với **Aspose.Page Java**, bạn có một API ngắn gọn trừu tượng các lệnh PostScript cấp thấp, cho phép bạn tập trung vào thiết kế thay vì các chi tiết định dạng tệp. Bây giờ bạn đã biết **cách thêm hatch pattern** vào tài liệu PostScript—hãy thử nghiệm các giá trị `HatchStyle` khác nhau để tạo ra giao diện chính xác bạn cần.

## Frequently Asked Questions

**H: Tôi có thể sử dụng Aspose.Page Java với các framework Java khác không?**  
Đ: Có, thư viện không phụ thuộc vào framework và hoạt động với Spring, Jakarta EE, Android (giới hạn), và Java SE thuần.

**H: Có phiên bản dùng thử cho Aspose.Page Java không?**  
Đ: Chắc chắn. Tải bản dùng thử miễn phí 30 ngày [here](https://releases.aspose.com/).

**H: Làm sao để tôi có được giấy phép tạm thời cho phát triển?**  
Đ: Yêu cầu giấy phép tạm thời [here](https://purchase.aspose.com/temporary-license/). Nó sẽ loại bỏ watermark đánh giá.

**H: Tôi có thể tìm thêm hướng dẫn và hỗ trợ cộng đồng ở đâu?**  
Đ: Truy cập diễn đàn chính thức [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) để có thêm ví dụ và Q&A.

**H: Có tài liệu đầy đủ cho tất cả các lớp và phương thức không?**  
Đ: Có, tham chiếu API đầy đủ có sẵn [here](https://reference.aspose.com/page/java/).

**H: Tôi có thể render cùng hatch pattern sang PDF thay vì PostScript không?**  
Đ: Chắc chắn. Thay đổi `PsSaveOptions` thành `PdfSaveOptions` (hoặc tương đương) và phần còn lại của mã không thay đổi.

**H: Tôi nên làm gì nếu tệp tạo ra rỗng?**  
Đ: Kiểm tra luồng đầu ra trỏ tới thư mục có quyền ghi và `document.save()` được gọi sau tất cả các thao tác vẽ.

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}