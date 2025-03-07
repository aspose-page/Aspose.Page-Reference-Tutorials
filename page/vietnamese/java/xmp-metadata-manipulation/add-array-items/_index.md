---
title: Thêm các mục mảng trong siêu dữ liệu XMP bằng Java
linktitle: Thêm các mục mảng trong siêu dữ liệu XMP bằng Java
second_title: API Java Aspose.Page
description: Nâng cao các tệp EPS với Aspose.Page cho Java. Tìm hiểu cách thêm các mục mảng vào siêu dữ liệu XMP một cách dễ dàng. Hãy làm theo hướng dẫn từng bước của chúng tôi ngay bây giờ!
weight: 10
url: /vi/java/xmp-metadata-manipulation/add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm các mục mảng trong siêu dữ liệu XMP bằng Java

## Giới thiệu
Chào mừng bạn đến với hướng dẫn từng bước của chúng tôi về cách sử dụng Aspose.Page cho Java để thêm các mục mảng trong siêu dữ liệu XMP. Aspose.Page là một thư viện Java mạnh mẽ cho phép bạn thao tác và làm việc với nhiều định dạng tài liệu khác nhau, bao gồm cả tệp EPS. Trong hướng dẫn này, chúng ta sẽ tập trung vào nhiệm vụ cụ thể là thêm các mục mảng trong siêu dữ liệu XMP bằng Java.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
- Aspose.Page cho thư viện Java đã được cài đặt.
- Hiểu biết cơ bản về lập trình Java.
- Tệp EPS hợp lệ có siêu dữ liệu XMP hoặc nhận xét siêu dữ liệu PS hiện có.
## Gói nhập khẩu
Để bắt đầu, bạn cần nhập các gói cần thiết để làm việc với Aspose.Page. Bao gồm các dòng sau vào đầu tệp Java của bạn:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Bước 1: Nhận siêu dữ liệu XMP
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Khởi tạo luồng tệp EPS đầu vào
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Nhận siêu dữ liệu XMP. Nếu tệp EPS không chứa siêu dữ liệu XMP, chúng tôi sẽ nhận được một tệp mới chứa đầy các giá trị từ nhận xét siêu dữ liệu PS (%%Creator, %%CreatDate, %%Title, v.v.)
XmpMetadata xmp = document.getXmpMetadata();
```
Trong bước này, chúng tôi truy xuất siêu dữ liệu XMP hiện có từ tệp EPS. Nếu tệp EPS chưa chứa siêu dữ liệu XMP, Aspose.Page sẽ tạo một tệp mới và điền vào đó các giá trị từ nhận xét siêu dữ liệu PS.
## Bước 2: Thêm mục mảng "dc:title"
```java
// Thêm một mục mảng "dc:title" nữa
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Bây giờ, chúng tôi thêm một mục mảng mới vào thuộc tính "dc:title" trong siêu dữ liệu XMP. Thay thế "NewTitle" bằng tiêu đề mong muốn.
## Bước 3: Thêm mục mảng "dc:creator"
```java
// Thêm một mục mảng "dc:creator" nữa
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Tương tự, chúng tôi thêm một mục mảng mới vào thuộc tính "dc:creator" trong siêu dữ liệu XMP. Thay thế "NewCreator" bằng thông tin người tạo mong muốn.
## Bước 4: Khởi tạo luồng tệp EPS đầu ra
```java
// Khởi tạo luồng tệp EPS đầu ra
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Chuẩn bị luồng tệp EPS đầu ra nơi tài liệu đã sửa đổi với siêu dữ liệu XMP cập nhật sẽ được lưu.
## Bước 5: Lưu tài liệu với siêu dữ liệu XMP đã thay đổi
```java
//Lưu tài liệu với siêu dữ liệu XMP đã thay đổi
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Lưu tài liệu có siêu dữ liệu XMP được cập nhật vào tệp EPS đầu ra.
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách thêm các mục mảng trong siêu dữ liệu XMP bằng Aspose.Page cho Java. Thư viện mạnh mẽ này đơn giản hóa quá trình thao tác với tệp EPS và cung cấp chức năng mở rộng để xử lý tài liệu.
## Các câu hỏi thường gặp

### Tôi có thể sử dụng Aspose.Page cho Java với các định dạng tài liệu khác không?
Có, Aspose.Page hỗ trợ nhiều định dạng tài liệu khác nhau, bao gồm EPS, PDF và XPS.
### Có bản dùng thử miễn phí cho Aspose.Page cho Java không?
 Có, bạn có thể truy cập bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Tôi có thể tìm tài liệu về Aspose.Page cho Java ở đâu?
 Tài liệu có sẵn[đây](https://reference.aspose.com/page/java/).
### Làm cách nào tôi có thể mua Aspose.Page cho Java?
 Bạn có thể mua sản phẩm[đây](https://purchase.aspose.com/buy).
### Giấy phép tạm thời có sẵn cho Aspose.Page cho Java không?
 Có, bạn có thể có được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
