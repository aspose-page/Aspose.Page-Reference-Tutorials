---
date: 2026-09-24
description: Tìm hiểu cách sử dụng Aspose.Page để chuyển đổi EPS sang PNG trong Java,
  cấu hình metered license và viết mã Java tạo tệp PNG một cách hiệu quả.
keywords:
- aspose page convert eps
- write png file java
- metered license java
- eps to png conversion
lastmod: 2026-09-24
linktitle: Cài đặt Metered License trong Java
og_description: Aspose.Page chuyển đổi EPS sang PNG trong Java với metered license.
  Hướng dẫn này trình bày chi tiết cách cấu hình giấy phép, render EPS và viết mã
  Java tạo tệp PNG.
og_image_alt: Guide showing Aspose.Page Java converting EPS to PNG with metered license
og_title: Aspose.Page chuyển đổi EPS sang PNG trong Java (metered license)
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  headline: Aspose.Page convert EPS to PNG in Java (metered license)
  type: TechArticle
- description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  name: Aspose.Page convert EPS to PNG in Java (metered license)
  steps:
  - name: initialize document and image format
    text: First, set the metered keys and define the output format (PNG). This establishes
      the foundation for the conversion. The `MeteredLicense` class stores your public
      and private keys, while `ImageSaveOptions` tells Aspose.Page to produce PNG
      output.
  - name: initialize PostScript input stream
    text: Open the EPS file you want to convert. The stream feeds the document into
      Aspose.Page. The `FileInputStream` reads the EPS file from disk, allowing the
      `Document` constructor to parse the PostScript data.
  - name: check document license
    text: Always verify that the metered license was applied correctly before processing.
      The `isLicensed()` method returns `true` only when the supplied keys are valid,
      preventing accidental usage of an unlicensed library.
  - name: initialize options and image device
    text: Create the options object that controls conversion settings and the device
      that will receive the rendered image. `ImageDevice` captures the rasterized
      output in memory, while `ImageSaveOptions` lets you tweak DPI, compression level,
      and color depth.
  - name: save EPS file as image
    text: This is the core **save EPS as PNG** call. The document is rendered into
      the image device using the options we configured. The `document.save(device,
      options)` method performs the rasterization in a single step.
  - name: get and save image bytes
    text: Extract the PNG bytes from the device and write them to a file on disk.
      This step demonstrates how to **write PNG file Java** safely. `Files.write(Paths.get("output.png"),
      device.getImagesBytes()[0])` persists the image without additional libraries.
  type: HowTo
- questions:
  - answer: Log into your Aspose account, navigate to the **Metered License** section,
      and copy the generated public and private keys.
    question: How do I obtain metered public and private keys?
  - answer: Aspose.Page offers a free trial with full functionality; production use
      requires a paid license. Download the trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is the Aspose.Page library free?
  - answer: Yes, a commercial license permits deployment in production environments.
      Purchase a license [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: The full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: Temporary licenses are provided through the Aspose portal [Aspose temporary
      license page](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image conversion
- metered licensing
title: Aspose.Page chuyển đổi EPS sang PNG trong Java (metered license)
url: /vi/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page chuyển đổi EPS sang PNG trong Java (giấy phép tính theo mức)

## Giới thiệu
Nếu bạn cần **lưu EPS dưới dạng PNG** trong một ứng dụng Java đồng thời giữ giấy phép đơn giản, bạn đã đến đúng nơi. Hướng dẫn này sẽ chỉ cho bạn cách cấu hình **giấy phép tính theo mức** cho Aspose.Page, tải tệp EPS (Encapsulated PostScript) và chuyển đổi nó thành ảnh PNG. Khi hoàn thành, bạn sẽ hiểu cách **render EPS sang PNG một cách hiệu quả** và cách viết mã **write PNG file Java** hoạt động ổn định trong môi trường production.

## Câu trả lời nhanh
- **“Lưu EPS dưới dạng PNG” có nghĩa là gì?** Nó chuyển đổi tệp EPS vector thành ảnh PNG raster, giữ nguyên độ trong suốt và nén không mất dữ liệu.  
- **Tại sao lại dùng giấy phép tính theo mức?** Bạn chỉ trả tiền cho số trang bạn xử lý, rất phù hợp cho khối lượng công việc biến đổi.  
- **Có cần kết nối internet không?** Không, các khóa tính theo mức được xác thực cục bộ trên JVM.  
- **Yêu cầu phiên bản Java nào?** Java 8 trở lên được hỗ trợ đầy đủ.  
- **Thiết lập mất bao lâu?** Khoảng 10 phút cho một triển khai cơ bản.

## “Lưu EPS thành PNG” là gì?
Lưu EPS dưới dạng PNG chuyển đổi tài liệu Encapsulated PostScript vector thành ảnh PNG raster, giữ nguyên độ trong suốt và cung cấp nén không mất dữ liệu. Việc chuyển đổi này hữu ích khi bạn cần đồ họa sẵn sàng cho web, ảnh thu nhỏ, hoặc bản xem trước có thể in mà không cần trình thông dịch PostScript.

## Tại sao phải render EPS sang PNG với Aspose.Page?
Aspose.Page cung cấp API thuần Java giúp rasterize các tệp EPS với độ trung thực cao, hỗ trợ hơn 50 định dạng đầu ra, và cung cấp giấy phép tính theo mức để bạn chỉ trả cho những gì bạn chuyển đổi. Thư viện có thể xử lý tài liệu hàng trăm trang mà không cần tải toàn bộ tệp vào bộ nhớ, mang lại tốc độ render nhanh và chính xác trên bất kỳ nền tảng nào hỗ trợ JVM.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- Kinh nghiệm phát triển Java cơ bản.  
- Thư viện Aspose.Page đã tải về từ [Aspose.Page Java download page](https://releases.aspose.com/page/java/).  
- Một cặp khóa công khai và riêng tính theo mức từ tài khoản Aspose của bạn.  

## Nhập các gói
Các câu lệnh `import` đưa các lớp cần thiết vào phạm vi. Giữ nguyên khối này như đã hiển thị để mã biên dịch mà không cần thay đổi.

Các lớp `java.io` xử lý luồng tệp, trong khi các lớp Aspose.Page quản lý giấy phép, tải tài liệu và render ảnh.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Cách lưu EPS thành PNG bằng Aspose.Page Java
Dưới đây là hướng dẫn từng bước kết hợp giấy phép, tải tệp, render và ghi tệp PNG cuối cùng.

### Câu trả lời trực tiếp
Tải tệp EPS của bạn, áp dụng giấy phép tính theo mức, cấu hình `ImageSaveOptions` cho PNG, render tài liệu vào một `ImageDevice`, và cuối cùng ghi mảng byte kết quả ra đĩa. Quy trình này hoàn thành **lưu EPS dưới dạng PNG** chỉ trong vài dòng mã Java.

### Bước 1: khởi tạo tài liệu và định dạng ảnh
Đầu tiên, đặt các khóa tính theo mức và xác định định dạng đầu ra (PNG). Điều này tạo nền tảng cho quá trình chuyển đổi.

Lớp `MeteredLicense` lưu trữ khóa công khai và riêng, trong khi `ImageSaveOptions` chỉ định Aspose.Page tạo ra đầu ra PNG.

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

### Bước 2: khởi tạo luồng nhập PostScript
Mở tệp EPS bạn muốn chuyển đổi. Luồng này cung cấp dữ liệu cho tài liệu Aspose.Page.

`FileInputStream` đọc tệp EPS từ đĩa, cho phép hàm khởi tạo `Document` phân tích dữ liệu PostScript.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Bước 3: kiểm tra giấy phép tài liệu
Luôn xác minh rằng giấy phép tính theo mức đã được áp dụng đúng trước khi xử lý.

Phương thức `isLicensed()` trả về `true` chỉ khi các khóa cung cấp hợp lệ, ngăn ngừa việc sử dụng thư viện không có giấy phép.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Bước 4: khởi tạo tùy chọn và thiết bị ảnh
Tạo đối tượng tùy chọn điều khiển cài đặt chuyển đổi và thiết bị sẽ nhận ảnh đã render.

`ImageDevice` lưu trữ đầu ra raster trong bộ nhớ, trong khi `ImageSaveOptions` cho phép bạn tinh chỉnh DPI, mức nén và độ sâu màu.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Bước 5: lưu tệp EPS dưới dạng ảnh
Đây là lời gọi **lưu EPS dưới dạng PNG** cốt lõi. Tài liệu được render vào thiết bị ảnh bằng các tùy chọn đã cấu hình.

Phương thức `document.save(device, options)` thực hiện rasterization trong một bước duy nhất.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Bước 6: lấy và lưu byte ảnh
Trích xuất byte PNG từ thiết bị và ghi chúng vào tệp trên đĩa. Bước này minh họa cách **write PNG file Java** một cách an toàn.

`Files.write(Paths.get("output.png"), device.getImagesBytes()[0])` lưu ảnh mà không cần thư viện bổ sung.

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

## Vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| **Giấy phép không được nhận dạng** | Khóa không đúng hoặc `setMeteredKey` được gọi sau khi xử lý tài liệu. | Kiểm tra lại chuỗi khóa công khai/riêng và đảm bảo `setMeteredKey` chạy trước bất kỳ lời gọi nào của Aspose.Page. |
| **Tệp đầu ra rỗng** | `device.getImagesBytes()` trả về `null` vì tệp EPS không thể phân tích. | Xác minh tệp EPS hợp lệ và `ImageSaveOptions` chỉ định kích thước canvas khác 0. |
| **Lỗi OutOfMemoryError khi EPS lớn** | Việc render các tệp vector lớn tiêu tốn nhiều bộ nhớ heap. | Xử lý các trang từng cái một hoặc tăng bộ nhớ heap JVM (`-Xmx2g`). |

## Câu hỏi thường gặp

**Q: Làm sao để lấy khóa công khai và riêng cho giấy phép tính theo mức?**  
A: Đăng nhập vào tài khoản Aspose, chuyển đến phần **Metered License**, và sao chép các khóa công khai và riêng đã tạo.

**Q: Thư viện Aspose.Page có miễn phí không?**  
A: Aspose.Page cung cấp bản dùng thử miễn phí với đầy đủ chức năng; sử dụng trong môi trường sản xuất yêu cầu mua giấy phép trả phí. Tải bản dùng thử tại [Aspose trial download page](https://releases.aspose.com/).

**Q: Tôi có thể sử dụng Aspose.Page cho dự án thương mại không?**  
A: Có, giấy phép thương mại cho phép triển khai trong môi trường sản xuất. Mua giấy phép tại [Aspose purchase page](https://purchase.aspose.com/buy).

**Q: Tôi có thể tìm tài liệu bổ sung ở đâu?**  
A: Tham khảo đầy đủ API tại [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Làm sao để nhận giấy phép tạm thời để đánh giá?**  
A: Giấy phép tạm thời được cung cấp qua cổng Aspose tại [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Nếu tôi cần chuyển đổi các tệp EPS đa trang thì sao?**  
A: Lặp qua từng trang bằng `device.getImagesBytes()` và ghi mỗi mảng byte thành một tệp PNG riêng.

**Q: Tôi có thể thay đổi chất lượng PNG hoặc độ sâu màu không?**  
A: Có, cấu hình `ImageSaveOptions` (ví dụ, `options.setCompressionLevel(9)`) trước khi gọi `document.save(...)`.

---

**Cập nhật lần cuối:** 2026-09-24  
**Kiểm tra với:** Aspose.Page 24.12 for Java (mới nhất)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách đặt giấy phép cho Aspose.Page Java API – Quản lý giấy phép](/page/java/license-management/)
- [Chuyển đổi PS sang PNG với Aspose.Page Java API](/page/java/postscript-conversion/to-image/)
- [Thay đổi kích thước EPS bằng Aspose.Page – Manipulation EPS Java](/page/java/manipulation-eps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}