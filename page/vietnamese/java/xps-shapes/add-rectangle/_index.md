---
date: 2025-12-30
description: Tìm hiểu cách tạo tài liệu XPS trong Java bằng cách thêm các hình chữ
  nhật sử dụng Aspose.Page. Hãy làm theo hướng dẫn từng bước này để thao tác tài liệu
  XPS một cách liền mạch.
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: Tạo tài liệu XPS bằng Java – Thêm hình chữ nhật với Aspose.Page
url: /vi/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Tài liệu XPS Java – Thêm Hình Chữ Nhật

## Introduction
Trong hướng dẫn toàn diện này, bạn sẽ **tạo tài liệu XPS Java** và học cách thêm các hình chữ nhật bằng thư viện Aspose.Page. Cho dù bạn đang xây dựng báo cáo, hoá đơn, hay đồ họa tùy chỉnh, việc thành thạo tạo hình chữ nhật sẽ cho bạn kiểm soát chính xác bố cục XPS. Chúng tôi sẽ hướng dẫn từng bước, giải thích lý do đằng sau mỗi dòng mã, và cho bạn thấy cách tùy chỉnh màu sắc và nét viền để đạt kết quả chuyên nghiệp.

## Quick Answers
- **What library is recommended?** Aspose.Page for Java  
- **How long does the implementation take?** Khoảng 10 phút cho một hình chữ nhật cơ bản  
- **Do I need a license?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất  
- **Which Java version is supported?** Java 8 trở lên  
- **Can I add multiple shapes?** Có – lặp lại các bước cho mỗi hình  

## Prerequisites
- Kiến thức cơ bản về ngôn ngữ lập trình Java.  
- Thư viện Aspose.Page đã được cài đặt. Nếu chưa, bạn có thể tải xuống từ [tài liệu Aspose.Page Java](https://reference.aspose.com/page/java/).  
- Môi trường phát triển Java hoạt động (IDE, JDK, và Maven/Gradle nếu bạn muốn).  

## Import Packages
Để bắt đầu, nhập các gói cần thiết vào dự án Java của bạn. Đảm bảo rằng thư viện Aspose.Page đã được thêm đúng vào classpath. Dưới đây là một ví dụ cơ bản:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Bây giờ, chúng ta sẽ phân tích ví dụ đã cung cấp thành nhiều bước để thêm một hình chữ nhật trong Java XPS.

## Step 1: Set the Document Directory
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

Thay thế `"Your Document Directory"` bằng đường dẫn tới thư mục nơi bạn muốn lưu các tệp XPS.

## Step 2: Create a New XPS Document
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Dòng này **tạo** một tài liệu XPS mới mà bạn có thể sau này điền các hình dạng, văn bản hoặc hình ảnh.

## Step 3: Add a CMYK Solid Color Stroked Rectangle
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

Bước này thêm một hình chữ nhật có viền màu CMYK đặc. Bạn có thể thay đổi chuỗi hình học (`"M 20,10 L 220,10 220,100 20,100 Z"`) để chỉnh kích thước hoặc vị trí, và điều chỉnh các giá trị màu trong `createColor` cho phù hợp với thiết kế của bạn.

## Step 4: Save the Resultant XPS Document
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

Cuối cùng, lưu tài liệu XPS đã chỉnh sửa cùng với hình chữ nhật đã thêm vào thư mục bạn đã chỉ định trước đó.

## Common Use Cases
- **Tiêu đề báo cáo** – Sử dụng hình chữ nhật làm khối nền cho tiêu đề.  
- **Bảng hoá đơn** – Làm nổi bật các ô hoặc phần bằng viền màu.  
- **Đồ họa tùy chỉnh** – Kết hợp nhiều hình chữ nhật để tạo các hình dạng phức tạp.  

## Troubleshooting Tips
- **File not found error:** Kiểm tra `dataDir` trỏ tới thư mục tồn tại và hồ sơ ICC (`uswebuncoated.icc`) có sẵn.  
- **Incorrect colors:** Đảm bảo hồ sơ ICC phù hợp với không gian màu bạn muốn sử dụng (CMYK so với RGB).  
- **Unexpected dimensions:** Điều chỉnh chuỗi hình học để phản ánh tọa độ đúng.  

## Conclusion
Chúc mừng! Bạn đã học cách **tạo tài liệu XPS Java** và thêm các hình chữ nhật bằng Aspose.Page. Nền tảng này cho phép bạn xây dựng tài liệu XPS phong phú hơn, tùy chỉnh đồ họa và tích hợp các hình dạng vào quy trình làm việc lớn hơn.

## FAQs
### Can I add multiple rectangles in a single XPS document?
Có, bạn có thể thêm bao nhiêu hình chữ nhật tùy ý bằng cách lặp lại các bước trong hướng dẫn.

### How can I change the color of the rectangle?
Thay đổi các giá trị màu trong phương thức `createColor` để đạt màu mong muốn.

### Is Aspose.Page suitable for handling complex XPS document manipulations?
Chắc chắn! Aspose.Page cung cấp bộ tính năng mạnh mẽ để xử lý các nhiệm vụ tài liệu XPS đa dạng.

### Where can I find additional examples and support?
Khám phá [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để xem thêm ví dụ và tìm sự hỗ trợ từ cộng đồng.

### Can I try Aspose.Page before purchasing?
Có, bạn có thể thử một [bản dùng thử miễn phí](https://releases.aspose.com/) để trải nghiệm khả năng của Aspose.Page.

## Frequently Asked Questions

**Q: Does this approach work with Java 11 or newer?**  
A: Có, thư viện Aspose.Page tương thích với Java 8 trở lên, bao gồm Java 11, 17 và các phiên bản sau.  

**Q: Can I embed images inside the rectangle area?**  
A: Bạn có thể thêm một phần tử `XpsImage` và đặt nó lên hoặc bên trong hình chữ nhật bằng cách sử dụng cùng các tọa độ hình học.  

**Q: How do I set a fill color instead of just a stroke?**  
A: Gọi `path.setFill(...)` với một brush màu đặc được tạo bằng `doc.createSolidColorBrush(...)`.  

**Q: Is it possible to rotate the rectangle?**  
A: Áp dụng ma trận biến đổi cho đường dẫn bằng `path.setTransform(...)` để thực hiện xoay hoặc phóng đại.  

**Q: What licensing is required for production use?**  
A: Cần giấy phép thương mại Aspose.Page cho triển khai; bản dùng thử miễn phí chỉ giới hạn cho đánh giá và phát triển.  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-30  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

---