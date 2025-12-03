---
date: 2025-12-03
description: Tìm hiểu cách lưu EPS thành PNG bằng Aspose.Page cho Java trong khi cấu
  hình giấy phép đo lường. Hướng dẫn từng bước kèm ví dụ mã đầy đủ.
language: vi
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Lưu EPS dưới dạng PNG với Aspose.Page Java (Giấy phép tính theo mức)
url: /java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lưu EPS dưới dạng PNG với Aspose.Page Java (Giấy phép Định mức)

## Giới thiệu
Nếu bạn cần **lưu EPS dưới dạng PNG** trong một ứng dụng Java và muốn có cách quản lý giấy phép không rắc rối, bạn đang ở đúng chỗ. Hướng dẫn này sẽ chỉ cho bạn cách cấu hình giấy phép định mức cho Aspose.Page, tải một tệp PostScript (EPS) và chuyển đổi nó thành ảnh PNG — tất cả với các bước ngắn gọn, dễ hiểu mà bạn có thể thực hiện ngay.

## Câu trả lời nhanh
- **“lưu EPS dưới dạng PNG” có nghĩa là gì?** Nó chuyển đổi tệp EPS vector thành ảnh raster PNG.  
- **Tại sao lại dùng giấy phép định mức?** Bạn chỉ trả tiền cho số trang bạn xử lý, rất phù hợp cho khối lượng công việc thay đổi.  
- **Có cần kết nối internet không?** Không, các khóa định mức được xác thực cục bộ.  
- **Yêu cầu phiên bản Java nào?** Java 8 trở lên.  
- **Thiết lập mất bao lâu?** Khoảng 10 phút cho một triển khai cơ bản.

## “Lưu EPS dưới dạng PNG” là gì?
Lưu EPS dưới dạng PNG chuyển đổi tài liệu Encapsulated PostScript có khả năng mở rộng thành định dạng bitmap được hỗ trợ rộng rãi. PNG giữ được độ trong suốt và cung cấp nén không mất dữ liệu, rất thích hợp cho đồ họa web, ảnh thu nhỏ và bản xem trước in.

## Tại sao nên dùng Aspose.Page cho nhiệm vụ này?
- **Pure Java API** – không phụ thuộc vào native.  
- **Độ chính xác cao** – đồ họa vector được render một cách chính xác.  
- **Giấy phép định mức** – bạn chỉ trả tiền cho những gì bạn chuyển đổi.  
- **Hỗ trợ nhiều định dạng đầu ra** – PNG, JPEG, TIFF, v.v.

## Yêu cầu trước
Trước khi bắt đầu, hãy đảm bảo bạn có:

- Kiến thức cơ bản về lập trình Java.  
- Thư viện Aspose.Page đã được cài đặt – tải về từ [here](https://releases.aspose.com/page/java/).  
- Các khóa công khai và riêng tư định mức, có thể lấy qua tài khoản Aspose của bạn.

## Nhập gói
Đầu tiên, nhập các lớp cần thiết. Giữ nguyên khối import như sau để mã biên dịch mà không cần thay đổi.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Bước 1: Khởi tạo Document và Định dạng Ảnh
Ở đây chúng ta thiết lập các khóa định mức và xác định định dạng đầu ra (PNG). Đây là nền tảng cho hoạt động **lưu EPS dưới dạng PNG**.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

## Bước 2: Khởi tạo Luồng Đầu vào PostScript
Mở tệp EPS bạn muốn chuyển đổi. Luồng này sẽ đưa tài liệu vào Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## Bước 3: Kiểm tra Giấy phép Document
Luôn luôn xác minh rằng giấy phép định mức đã được áp dụng đúng trước khi xử lý.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## Bước 4: Khởi tạo Options và Image Device
Tạo đối tượng options để điều khiển các cài đặt chuyển đổi và thiết bị sẽ nhận ảnh đã render.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## Bước 5: Lưu Tệp EPS dưới dạng Ảnh
Đây là lời gọi **lưu EPS dưới dạng PNG** cốt lõi. Tài liệu được render vào thiết bị ảnh bằng các options đã cấu hình.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## Bước 6: Lấy và Lưu Dữ liệu Ảnh
Trích xuất dữ liệu PNG từ thiết bị và ghi chúng vào tệp trên đĩa.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|-----------|
| **Giấy phép không được công nhận** | Khóa không đúng hoặc đặt sai thứ tự. | Kiểm tra lại chuỗi khóa công khai/riêng tư và đảm bảo `setMeteredKey` được gọi trước bất kỳ xử lý tài liệu nào. |
| **Tệp đầu ra rỗng** | `device.getImagesBytes()` trả về `null`. | Xác minh tệp EPS hợp lệ và `ImageSaveOptions` không được đặt kích thước canvas bằng 0. |
| **OutOfMemoryError khi EPS lớn** | Render các tệp vector lớn tiêu tốn nhiều bộ nhớ. | Xử lý từng trang một hoặc tăng heap JVM (`-Xmx2g`). |

## Câu hỏi thường gặp

**H: Làm sao để lấy khóa công khai và riêng tư định mức?**  
Đ: Bạn có thể lấy các khóa này qua tài khoản Aspose của mình.

**H: Thư viện Aspose.Page có miễn phí không?**  
Đ: Aspose.Page cung cấp cả phiên bản dùng thử miễn phí và phiên bản trả phí. Truy cập [here](https://releases.aspose.com/) để dùng thử miễn phí.

**H: Tôi có thể dùng Aspose.Page cho dự án thương mại không?**  
Đ: Có, Aspose.Page có giấy phép thương mại. Bạn có thể mua chúng [here](https://purchase.aspose.com/buy).

**H: Tôi có thể tìm tài liệu bổ sung ở đâu?**  
Đ: Tham khảo tài liệu [here](https://reference.aspose.com/page/java/).

**H: Làm sao để lấy giấy phép tạm thời?**  
Đ: Giấy phép tạm thời có thể được lấy [here](https://purchase.aspose.com/temporary-license/).

---

**Cập nhật lần cuối:** 2025-12-03  
**Đã kiểm thử với:** Aspose.Page 24.12 cho Java  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
