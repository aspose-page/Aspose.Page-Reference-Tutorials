---
title: Tích hợp giấy phép đo lường dễ dàng với Aspose.Page Java
linktitle: Đặt giấy phép đo lường trong Java
second_title: API Java Aspose.Page
description: Khám phá sự tích hợp liền mạch của Aspose.Page với Java. Thiết lập giấy phép được đo lường một cách dễ dàng và nâng cao khả năng xử lý tài liệu của bạn.
type: docs
weight: 10
url: /vi/java/license-management/set-metered-license/
---
## Giới thiệu
Chào mừng bạn đến với hướng dẫn toàn diện của chúng tôi về cách thiết lập giấy phép đo lường trong Java bằng Aspose.Page. Nếu bạn đang tìm cách nâng cao khả năng xử lý tài liệu của mình và đảm bảo tích hợp liền mạch với Aspose.Page thì bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn thực hiện quy trình, chia nhỏ từng bước thành các phần dễ hiểu.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Kiến thức cơ bản về lập trình Java.
-  Đã cài đặt thư viện Aspose.Page. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/page/java/).
- Khóa công khai và khóa riêng tư được đo lường mà bạn có thể lấy thông qua tài khoản Aspose của mình.
## Gói nhập khẩu
Hãy bắt đầu bằng cách nhập các gói cần thiết cho chương trình Java của chúng ta. Đảm bảo bạn đã tích hợp thư viện Aspose.Page vào dự án của mình.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## Bước 1: Khởi tạo định dạng tài liệu và hình ảnh
Bước đầu tiên là thiết lập tài liệu và xác định định dạng hình ảnh mong muốn.
```java
// đặt khóa công khai và khóa riêng tư được đo lường
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Truy cập thuộc tính setMeteredKey và chuyển khóa chung và khóa riêng làm tham số
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## Bước 2: Khởi tạo luồng đầu vào PostScript
Trong bước này, chúng tôi khởi tạo luồng đầu vào PostScript để xử lý.
```java
// Khởi tạo luồng đầu vào PostScript
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## Bước 3: Kiểm tra giấy phép
Trước khi tiếp tục, điều quan trọng là phải xác minh xem tài liệu có được cấp phép hợp lệ hay không.
```java
// Kiểm tra xem tài liệu có được cấp phép không
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## Bước 4: Khởi tạo các tùy chọn và thiết bị hình ảnh
Bây giờ, hãy khởi tạo các tùy chọn và thiết bị hình ảnh với các thông số mặc định.
```java
// Khởi tạo đối tượng tùy chọn với các tham số mặc định.
ImageSaveOptions options = new ImageSaveOptions();
// Khởi tạo đối tượng ImageDevice với các tham số mặc định.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## Bước 5: Lưu tệp EPS dưới dạng hình ảnh
Lưu tệp EPS dưới dạng hình ảnh bằng các tùy chọn và thiết bị đã xác định.
```java
// Lưu tệp EPS dưới dạng hình ảnh
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## Bước 6: Nhận và lưu byte hình ảnh
Truy xuất byte hình ảnh và lưu chúng vào một tệp.
```java
// Nhận byte hình ảnh. Mảng một byte cho một trang. Trong trường hợp của chúng tôi, chúng tôi có một trang.
byte[][] imagesBytes = device.getImagesBytes();
// Lưu byte hình ảnh vào tập tin
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## Phần kết luận
Chúc mừng! Bạn đã thiết lập thành công giấy phép đo lường trong Java bằng Aspose.Page. Hướng dẫn này cung cấp hướng dẫn từng bước để đảm bảo quá trình tích hợp diễn ra suôn sẻ.
## Câu hỏi thường gặp
### Câu hỏi: Làm cách nào để có được khóa công khai và khóa riêng tư?
Bạn có thể lấy các khóa này thông qua tài khoản Aspose của mình.
### Câu hỏi: Thư viện Aspose.Page có miễn phí không?
 Aspose.Page cung cấp cả phiên bản dùng thử miễn phí và trả phí. Thăm nom[đây](https://releases.aspose.com/) để dùng thử miễn phí.
### Câu hỏi: Tôi có thể sử dụng Aspose.Page cho các dự án thương mại không?
 Có, Aspose.Page cung cấp giấy phép thương mại. Bạn có thể mua chúng[đây](https://purchase.aspose.com/buy).
### Hỏi: Tôi có thể tìm tài liệu bổ sung ở đâu?
 Tham khảo tài liệu[đây](https://reference.aspose.com/page/java/).
### Hỏi: Làm thế nào tôi có thể nhận được giấy phép tạm thời?
 Giấy phép tạm thời có thể được lấy[đây](https://purchase.aspose.com/temporary-license/).