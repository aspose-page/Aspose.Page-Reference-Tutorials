---
date: 2026-03-05
description: Tìm hiểu cách thêm các mục mảng dc:title vào siêu dữ liệu XMP của tệp
  EPS bằng Aspose.Page cho Java. Hãy làm theo hướng dẫn từng bước này để có kết quả
  nhanh chóng.
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Cách Thêm Các Mục Mảng dc:title vào Siêu Dữ Liệu XMP bằng Java
url: /vi/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm các mục mảng vào siêu dữ liệu XMP bằng Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ khám phá **cách thêm dc:title** (và các mục mảng khác) vào siêu dữ liệu XMP trong tệp EPS bằng Aspose.Page for Java. Cập nhật siêu dữ liệu XMP hữu ích khi bạn cần nhúng thông tin có thể tìm kiếm—như tiêu đề, người tạo hoặc từ khóa—trực tiếp vào các tệp đồ họa của mình. Chúng tôi sẽ hướng dẫn từng bước, giải thích lý do mỗi dòng quan trọng và chỉ cho bạn cách xác minh các thay đổi.

## Câu trả lời nhanh
- **dc:title đại diện cho gì?** Đó là thuộc tính tiêu đề Dublin Core được lưu dưới dạng mảng XMP.  
- **Tại sao phải chỉnh sửa siêu dữ liệu XMP?** Nó cho phép quản lý tài sản tốt hơn, khả năng tìm kiếm và tuân thủ các tiêu chuẩn.  
- **Có cần một khối XMP hiện có không?** Không—Aspose.Page sẽ tạo một khối từ các chú thích PS nếu thiếu.  
- **Phiên bản thư viện nào được yêu cầu?** Bất kỳ bản phát hành gần đây nào của Aspose.Page for Java (đã kiểm tra với bản 2026 mới nhất).  
- **Tôi có thể thêm các thuộc tính mảng khác không?** Có—sử dụng cùng phương thức `addArrayItem` cho các thuộc tính như `dc:creator`.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- Thư viện Aspose.Page for Java đã được cài đặt (thêm JAR vào classpath của dự án).  
- Kinh nghiệm phát triển Java cơ bản (khuyến nghị JDK 8+).  
- Một tệp EPS đã chứa siêu dữ liệu XMP hoặc ít nhất các chú thích siêu dữ liệu PS (ví dụ, `%%Title`, `%%Creator`).  

## Nhập các gói
Để bắt đầu, nhập các lớp cần thiết để đọc, thao tác và lưu các tệp EPS:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Bước 1: Tải tài liệu EPS và truy xuất siêu dữ liệu XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Ở đây chúng ta mở tệp EPS và yêu cầu Aspose.Page cung cấp khối XMP của nó. Nếu tệp thiếu XMP, thư viện sẽ tự động tạo một khối mới bằng cách sử dụng các chú thích PS hiện có, đảm bảo bạn luôn có một container siêu dữ liệu để làm việc.

## Bước 2: Thêm một mục mảng **dc:title** mới  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

Dòng này minh họa **cách thêm dc:title**. Thay `"NewTitle"` bằng tiêu đề thực tế bạn muốn nhúng. Phương thức sẽ thêm giá trị vào mảng tiêu đề hiện có, giữ lại bất kỳ tiêu đề nào đã có trước đó.

## Bước 3: Thêm một mục mảng **dc:creator** mới  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

Tương tự, bạn có thể làm phong phú thuộc tính `dc:creator`. Nhiều người tạo có thể được lưu; mỗi lần gọi sẽ thêm một mục mới.

## Bước 4: Chuẩn bị luồng đầu ra  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

Chúng tôi tạo một luồng cho tệp EPS đã chỉnh sửa. Sử dụng tên tệp khác (`xmp3_changed.eps`) giúp giữ nguyên tệp gốc.

## Bước 5: Lưu tài liệu với siêu dữ liệu XMP đã cập nhật  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

Lệnh `save` ghi dữ liệu EPS cùng với khối XMP đã cập nhật. Khối `finally` đảm bảo tay cầm tệp được giải phóng ngay cả khi xảy ra ngoại lệ.

## Tại sao điều này quan trọng
Nhúng các giá trị `dc:title` và `dc:creator` chính xác giúp cải thiện:

- **Khả năng tìm kiếm** trong các hệ thống quản lý tài sản kỹ thuật số (DAM).  
- **Tuân thủ** các tiêu chuẩn xuất bản yêu cầu siêu dữ liệu.  
- **Hợp tác**, vì các đồng nghiệp có thể nhanh chóng xác định nội dung tệp mà không cần mở EPS.

## Những cạm bẫy thường gặp & Mẹo
- **Cạm bẫy:** Ghi đè các mục mảng hiện có một cách không cố ý.  
  **Mẹo:** Sử dụng `xmp.getArrayItems("dc:title")` để kiểm tra các giá trị hiện tại trước khi thêm mới.  
- **Cạm bẫy:** Quên đóng luồng, gây khóa tệp.  
  **Mẹo:** Luôn bao bọc I/O trong try‑with‑resources hoặc khối `finally` như đã minh họa.  
- **Mẹo:** Bạn có thể nối chuỗi nhiều lời gọi `addArrayItem` để thêm nhiều tiêu đề hoặc người tạo trong một lần.

## Câu hỏi thường gặp

### Tôi có thể sử dụng Aspose.Page for Java với các định dạng tài liệu khác không?
Có, Aspose.Page hỗ trợ nhiều định dạng tài liệu, bao gồm EPS, PDF và XPS.

### Có bản dùng thử miễn phí cho Aspose.Page for Java không?
Có, bạn có thể truy cập bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

### Tôi có thể tìm tài liệu cho Aspose.Page for Java ở đâu?
Tài liệu có sẵn [tại đây](https://reference.aspose.com/page/java/).

### Làm sao để mua Aspose.Page for Java?
Bạn có thể mua sản phẩm [tại đây](https://purchase.aspose.com/buy).

### Có giấy phép tạm thời cho Aspose.Page for Java không?
Có, bạn có thể nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

---

**Cập nhật lần cuối:** 2026-03-05  
**Đã kiểm tra với:** Aspose.Page for Java (bản phát hành 2026 mới nhất)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}