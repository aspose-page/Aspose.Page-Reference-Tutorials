---
date: 2025-12-20
description: Tìm hiểu cách tạo siêu dữ liệu XMP EPS trong các tệp EPS bằng Aspose.Page
  cho Java. Hướng dẫn từng bước để thêm các thuộc tính XMP đơn giản một cách lập trình.
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: Cách tạo siêu dữ liệu XMP EPS bằng Java
url: /vi/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm Thuộc Tính Đơn Giản vào XMP bằng Java

## Giới thiệu
Trong các quy trình làm việc với tài liệu hiện đại, khả năng **tạo tệp EPS có siêu dữ liệu XMP** một cách lập trình cho phép bạn kiểm soát hoàn toàn cách đồ họa của mình được mô tả, tìm kiếm và lưu trữ. Với Aspose.Page for Java, bạn có thể đọc, chỉnh sửa và ghi các gói XMP bên trong tài liệu EPS mà không rời khỏi môi trường Java. Trong hướng dẫn này, chúng tôi sẽ dẫn bạn qua các bước chính xác để thêm các thuộc tính XMP đơn giản vào tệp EPS, giúp bạn làm giàu đồ họa với siêu dữ liệu tùy chỉnh một cách nhanh chóng và đáng tin cậy.

## Câu trả lời nhanh
- **“tạo xmp metadata eps” có nghĩa là gì?** Thêm một gói XMP (siêu dữ liệu dựa trên XML) vào tệp EPS.  
- **Thư viện nào cần thiết?** Aspose.Page for Java (có thể tải xuống từ trang Aspose).  
- **Có cần giấy phép để thử nghiệm không?** Bản dùng thử miễn phí hoạt động cho việc phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Có bao nhiêu dòng mã?** Ít hơn 30 dòng Java cộng với một vài câu lệnh import.  
- **Có thể thêm các kiểu dữ liệu khác không?** Có – ngày, số nguyên, số thực, chuỗi và thậm chí mảng đều được hỗ trợ.

## “tạo xmp metadata eps” là gì?
XMP (Extensible Metadata Platform) là tiêu chuẩn để nhúng siêu dữ liệu phong phú vào trong các tệp. Khi bạn **tạo XMP metadata EPS**, bạn nhúng một gói XML vào trong tài liệu EPS (Encapsulated PostScript), cho phép các ứng dụng downstream đọc thông tin tác giả, ngày tạo, thẻ tùy chỉnh và nhiều hơn nữa.

## Tại sao nên thêm siêu dữ liệu XMP vào tệp EPS?
- **Khả năng tìm kiếm:** Cho phép hệ thống DAM tự động lập chỉ mục.  
- **Tuân thủ:** Lưu trữ thông tin pháp lý hoặc giấy phép trực tiếp trong tệp.  
- **Tự động hoá:** Giúp các pipeline downstream đưa ra quyết định dựa trên dữ liệu nhúng.  
- **Di động:** Siêu dữ liệu đi cùng EPS, đảm bảo tính nhất quán trên mọi nền tảng.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- Kiến thức cơ bản về lập trình Java.  
- Thư viện Aspose.Page for Java đã được cài đặt. Bạn có thể tải **[tại đây](https://releases.aspose.com/page/java/)**.  
- Một tệp EPS mẫu có chứa siêu dữ liệu. Nếu chưa có, bạn có thể sử dụng tệp **`xmp3.eps`** được cung cấp.

## Nhập các gói
Đầu tiên, nhập các lớp cần thiết. Các câu lệnh import giữ nguyên như trong ví dụ gốc:

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

## Bước 1: Tải tài liệu EPS và lấy siêu dữ liệu XMP
Chúng ta mở tệp EPS, tạo một thể hiện `PsDocument`, và truy xuất (hoặc tạo) gói XMP.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Bước 2: Thêm thuộc tính Ngày
Thêm ngày chỉ cần tạo một đối tượng `Date` và đưa nó vào bản đồ XMP.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Bước 3: Thêm thuộc tính Số nguyên
Bạn có thể lưu các định danh số hoặc số phiên bản bằng giá trị nguyên.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Bước 4: Thêm thuộc tính Số thực
Các số dấu phẩy động hữu ích cho các phép đo hoặc đánh giá.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Bước 5: Thêm thuộc tính Chuỗi
Các thẻ văn bản tùy chỉnh (ví dụ: mã dự án) được lưu dưới dạng chuỗi.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Bước 6: Lưu tệp EPS đã cập nhật
Sau khi đã thêm tất cả các thuộc tính, ghi lại tài liệu về đĩa.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Bước 7: Dọn dẹp tài nguyên
Luôn đóng luồng nhập để tránh rò rỉ handle tệp.

```java
// Close input EPS stream
psStream.close();
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Lý do | Cách khắc phục |
|-------|--------|----------------|
| **Null XMP metadata** | Tệp EPS không có gói XMP và thư viện không thể suy ra các comment PS. | Đảm bảo EPS nguồn chứa ít nhất một comment PS (ví dụ: `%%Creator`). Thư viện sẽ tự động tạo một gói XMP tối thiểu. |
| **Time zone mismatch** | Ngày tháng bị lệch khi mở trong ứng dụng khác. | Đặt `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` trước khi tạo đối tượng `Date`, như trong Bước 2. |
| **License exception** | Runtime ném `LicenseException`. | Áp dụng giấy phép Aspose.Page hợp lệ trước khi sử dụng API, hoặc chạy ở chế độ dùng thử để đánh giá. |

## Kết luận
Sau khi thực hiện các bước trên, bạn đã biết cách **tạo XMP metadata EPS** bằng Aspose.Page for Java. Việc thêm các thuộc tính đơn giản như ngày, số nguyên, số thực và chuỗi là rất dễ dàng, và các tệp EPS kết quả sẽ mang siêu dữ liệu phong phú, có thể tìm kiếm, mang lại lợi ích cho bất kỳ quy trình downstream nào.

## Câu hỏi thường gặp
### Tôi có thể dùng Aspose.Page for Java với các ngôn ngữ lập trình khác không?
Aspose.Page chủ yếu hỗ trợ Java, nhưng cũng có các phiên bản cho các ngôn ngữ khác như .NET.

### Có bản dùng thử miễn phí cho Aspose.Page for Java không?
Có, bạn có thể khám phá các tính năng của Aspose.Page bằng cách lấy bản dùng thử [tại đây](https://releases.aspose.com/).

### Tôi có thể tìm tài liệu chi tiết cho Aspose.Page for Java ở đâu?
Tài liệu có sẵn [tại đây](https://reference.aspose.com/page/java/).

### Làm sao để lấy giấy phép tạm thời cho Aspose.Page for Java?
Bạn có thể nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

### Tôi có thể mua Aspose.Page for Java ở đâu?
Bạn có thể mua sản phẩm [tại đây](https://purchase.aspose.com/buy).

---

**Cập nhật lần cuối:** 2025-12-20  
**Đã kiểm tra với:** Aspose.Page for Java 24.11 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}