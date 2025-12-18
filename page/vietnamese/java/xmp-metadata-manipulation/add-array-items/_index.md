---
date: 2025-12-18
description: Tìm hiểu cách thêm siêu dữ liệu bằng cách chèn các mục mảng vào siêu
  dữ liệu XMP của tệp EPS bằng Aspose.Page cho Java. Thực hiện theo hướng dẫn từng
  bước của chúng tôi.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Cách Thêm Siêu Dữ Liệu – Thêm Các Mục Mảng trong XMP (Java)
url: /vi/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm Mục Mảng vào Siêu dữ liệu XMP bằng Java

## Cách Thêm Siêu dữ liệu
Chào mừng bạn đến với hướng dẫn **cách thêm siêu dữ liệu** vào tệp EPS bằng Aspose.Page for Java. Trong tutorial này, chúng tôi sẽ hướng dẫn bạn cách thêm các mục mảng vào siêu dữ liệu XMP — một yêu cầu phổ biến khi bạn cần làm phong phú thông tin tài liệu như tiêu đề hoặc người tạo. Khi hoàn thành, bạn sẽ hiểu tại sao XMP có giá trị, cách thao tác nó bằng mã, và cách lưu tệp EPS đã cập nhật.

## Trả Lời Nhanh
- **Thư viện nào được sử dụng?** Aspose.Page for Java  
- **Định dạng tệp mục tiêu là gì?** EPS (Encapsulated PostScript)  
- **Có thể thêm nhiều tiêu đề không?** Có, sử dụng `xmp.addArrayItem("dc:title", ...)` nhiều lần  
- **Cần giấy phép cho môi trường production không?** Có, cần giấy phép Aspose.Page hợp lệ  
- **Mã có tương thích với Java 8+ không?** Hoàn toàn, hoạt động trên mọi phiên bản Java hiện đại  

## Yêu Cầu Trước
Trước khi bắt đầu tutorial, hãy chắc chắn bạn đã chuẩn bị:
- Thư viện Aspose.Page for Java đã được cài đặt.  
- Kiến thức cơ bản về lập trình Java.  
- Một tệp EPS hợp lệ có sẵn siêu dữ liệu XMP hoặc các chú thích siêu dữ liệu PS.

## Nhập Gói
Để bắt đầu, bạn cần nhập các gói cần thiết để làm việc với Aspose.Page. Thêm các dòng sau vào đầu tệp Java của bạn:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Bước 1: Lấy Siêu dữ liệu XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
Trong bước này, chúng ta truy xuất siêu dữ liệu XMP hiện có từ tệp EPS. Nếu tệp EPS chưa chứa siêu dữ liệu XMP, Aspose.Page sẽ tạo mới và điền các giá trị từ các chú thích siêu dữ liệu PS.

## Bước 2: Thêm Mục Mảng "dc:title"
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Bây giờ, chúng ta thêm một mục mảng mới vào thuộc tính **dc:title** trong siêu dữ liệu XMP. Thay `"NewTitle"` bằng tiêu đề mong muốn.

## Bước 3: Thêm Mục Mảng "dc:creator"
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Tương tự, chúng ta thêm một mục mảng mới vào thuộc tính **dc:creator** trong siêu dữ liệu XMP. Thay `"NewCreator"` bằng thông tin người tạo mong muốn.

## Bước 4: Khởi Tạo Luồng Tệp EPS Đầu Ra
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Chuẩn bị luồng tệp EPS đầu ra, nơi tài liệu đã được chỉnh sửa với siêu dữ liệu XMP mới sẽ được lưu.

## Bước 5: Lưu Tài Liệu với Siêu dữ liệu XMP Đã Thay Đổi
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Lưu tài liệu cùng siêu dữ liệu XMP đã cập nhật vào tệp EPS đầu ra.

## Kết Luận
Chúc mừng! Bạn đã học **cách thêm siêu dữ liệu** bằng cách chèn các mục mảng vào siêu dữ liệu XMP sử dụng Aspose.Page for Java. Thư viện mạnh mẽ này giúp đơn giản hoá quá trình thao tác tệp EPS và cung cấp chức năng phong phú cho việc xử lý tài liệu.

## Câu Hỏi Thường Gặp

### Tôi có thể dùng Aspose.Page for Java với các định dạng tài liệu khác không?
Có, Aspose.Page hỗ trợ nhiều định dạng tài liệu, bao gồm EPS, PDF và XPS.

### Có bản dùng thử miễn phí cho Aspose.Page for Java không?
Có, bạn có thể truy cập bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

### Tôi có thể tìm tài liệu cho Aspose.Page for Java ở đâu?
Tài liệu có sẵn [tại đây](https://reference.aspose.com/page/java/).

### Làm sao để mua Aspose.Page for Java?
Bạn có thể mua sản phẩm [tại đây](https://purchase.aspose.com/buy).

### Có giấy phép tạm thời cho Aspose.Page for Java không?
Có, bạn có thể nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

## Các Câu Hỏi Thường Gặp Bổ Sung

**H: Tôi có thể thêm hơn một mục mảng vào cùng một thuộc tính không?**  
Đ: Hoàn toàn có thể. Gọi `xmp.addArrayItem` nhiều lần cho cùng một thuộc tính để tạo danh sách các giá trị.

**H: Cách tiếp cận này có hoạt động với các schema XMP hiện có khác Dublin Core không?**  
Đ: Có, bạn có thể thêm mục mảng vào bất kỳ thuộc tính XMP nào miễn là không gian tên được tham chiếu đúng.

**H: Làm sao kiểm tra xem siêu dữ liệu đã được thêm đúng chưa?**  
Đ: Mở tệp EPS kết quả trong một trình xem hỗ trợ XMP (ví dụ: Adobe Bridge) hoặc trích xuất siêu dữ liệu bằng chương trình sử dụng các phương thức của `XmpMetadata`.

---

**Cập nhật lần cuối:** 2025-12-18  
**Đã kiểm tra với:** Aspose.Page for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}