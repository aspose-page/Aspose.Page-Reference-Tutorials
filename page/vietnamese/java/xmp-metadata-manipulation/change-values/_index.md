---
title: Thay đổi giá trị trong XMP bằng Java
linktitle: Thay đổi giá trị trong XMP bằng Java
second_title: API Java Aspose.Page
description: Nâng cao tài liệu EPS với Aspose.Page cho Java. Dễ dàng sửa đổi siêu dữ liệu XMP để có nội dung phù hợp và chuyên nghiệp. #Java Development
weight: 17
url: /vi/java/xmp-metadata-manipulation/change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thay đổi giá trị trong XMP bằng Java

## Giới thiệu
Trong lĩnh vực xử lý và thao tác tài liệu, Aspose.Page dành cho Java nổi bật như một công cụ mạnh mẽ. Hướng dẫn này đi sâu vào quá trình thay đổi giá trị XMP (Nền tảng siêu dữ liệu mở rộng) trong tài liệu EPS (Encapsulated PostScript) bằng Java với thư viện Aspose.Page. Bằng cách làm theo hướng dẫn từng bước được cung cấp, bạn sẽ học cách sửa đổi siêu dữ liệu một cách dễ dàng, đảm bảo tài liệu của bạn được điều chỉnh theo yêu cầu cụ thể của bạn.
## Điều kiện tiên quyết
Trước khi chúng ta bắt tay vào hướng dẫn này, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1. Môi trường phát triển Java: Đảm bảo bạn có môi trường phát triển Java hoạt động trên máy của mình.
2.  Aspose.Page for Java Library: Tải xuống và cài đặt thư viện Aspose.Page cho Java. Bạn có thể tìm thấy gói cần thiết[đây](https://releases.aspose.com/page/java/).
## Gói nhập khẩu
Bắt đầu bằng cách nhập các gói cần thiết vào dự án Java của bạn. Các gói này rất quan trọng để tương tác và thao tác với các tài liệu EPS.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## Bước 1: Nhận siêu dữ liệu XMP
Truy xuất siêu dữ liệu XMP từ tài liệu EPS. Nếu tệp EPS không chứa siêu dữ liệu XMP thì một tệp mới sẽ được tạo với các giá trị từ nhận xét siêu dữ liệu PS như %%Creator, %%CreatDate và %%Title.
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Khởi tạo luồng tệp EPS đầu vào
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Nhận siêu dữ liệu XMP. Nếu tệp EPS không chứa siêu dữ liệu XMP thì một tệp mới sẽ được tạo với các giá trị từ nhận xét siêu dữ liệu PS
XmpMetadata xmp = document.getXmpMetadata();
```
## Bước 2: Thay đổi giá trị "ModifyDate"
Sửa đổi giá trị "ModifyDate" trong siêu dữ liệu XMP để phản ánh ngày mong muốn.
```java
// Thay đổi giá trị "ModifyDate"
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## Bước 3: Thay đổi giá trị "Người tạo"
Cập nhật giá trị "Người tạo" trong siêu dữ liệu XMP để chỉ định người tạo tài liệu.
```java
// Thay đổi giá trị "người tạo"
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## Bước 4: Thay đổi giá trị "Tiêu đề"
Sửa đổi giá trị "Tiêu đề" trong siêu dữ liệu XMP để đặt tiêu đề phù hợp cho tài liệu.
```java
//Thay đổi giá trị "tiêu đề"
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## Bước 5: Lưu tài liệu với siêu dữ liệu XMP đã thay đổi
Lưu tài liệu có siêu dữ liệu XMP đã cập nhật vào tệp EPS mới.
```java
// Khởi tạo luồng tệp EPS đầu ra
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//Lưu tài liệu với siêu dữ liệu XMP đã thay đổi
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Phần kết luận
Chúc mừng! Bạn đã điều hướng thành công quá trình thay đổi giá trị XMP trong tài liệu EPS bằng Aspose.Page cho Java. Hướng dẫn này đã trang bị cho bạn kiến thức để sửa đổi siêu dữ liệu, đảm bảo tài liệu của bạn phù hợp với các yêu cầu cụ thể một cách liền mạch.
## Câu hỏi thường gặp
### Câu hỏi: Làm cách nào tôi có thể xử lý các cân nhắc về múi giờ khi sửa đổi giá trị XMP?
 Sử dụng`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` để đảm bảo tính nhất quán trong cài đặt múi giờ.
### Câu hỏi: Tôi có thể thay đổi nhiều giá trị XMP trong một thao tác không?
 Có, bằng cách sử dụng`put` cho từng giá trị mong muốn, bạn có thể sửa đổi đồng thời nhiều giá trị XMP.
### Câu hỏi: Tôi có thể tìm tài liệu bổ sung về Aspose.Page cho Java ở đâu?
 Khám phá tài liệu toàn diện[đây](https://reference.aspose.com/page/java/).
### Câu hỏi: Aspose.Page có bản dùng thử miễn phí dành cho Java không?
 Có, bạn có thể truy cập bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Câu hỏi: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Page cho Java?
 Nhận giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
