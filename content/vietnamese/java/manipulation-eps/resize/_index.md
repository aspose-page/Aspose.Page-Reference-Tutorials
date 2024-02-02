---
title: Thay đổi kích thước tệp EPS trong Java bằng Aspose.Page
linktitle: Thay đổi kích thước tệp EPS trong Java
second_title: API Java Aspose.Page
description: Tìm hiểu cách thay đổi kích thước tệp EPS trong Java một cách dễ dàng với Aspose.Page cho Java. Hãy làm theo hướng dẫn toàn diện của chúng tôi để biết hướng dẫn từng bước.
type: docs
weight: 11
url: /vi/java/manipulation-eps/resize/
---
## Giới thiệu
Chào mừng bạn đến với hướng dẫn từng bước của chúng tôi về cách thay đổi kích thước tệp EPS trong Java bằng thư viện Aspose.Page mạnh mẽ. Nếu bạn cần điều chỉnh kích thước của hình ảnh EPS theo chương trình thì bạn đã đến đúng nơi. Trong hướng dẫn này, chúng ta sẽ khám phá các tùy chọn thay đổi kích thước khác nhau, bao gồm điểm, inch, milimet và tỷ lệ phần trăm, mang đến cho bạn sự linh hoạt cần thiết cho các yêu cầu cụ thể của mình.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có những điều sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên máy của bạn.
-  Aspose.Page cho thư viện Java. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/page/java/).
- Hiểu biết cơ bản về lập trình Java.
## Gói nhập khẩu
Trong dự án Java của bạn, hãy đảm bảo bạn có các nội dung nhập cần thiết để sử dụng các chức năng của Aspose.Page. Đây là một ví dụ:
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
Bây giờ, hãy chia hướng dẫn thành nhiều bước cho mỗi tùy chọn thay đổi kích thước:
## Thay đổi kích thước EPS bằng Điểm
### Bước 1: Thiết lập luồng đầu vào
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### Bước 2: Khởi tạo đối tượng PsDocument
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### Bước 3: Trích xuất kích thước hiện tại của ảnh EPS
```java
Dimension oldSize = doc.extractEpsSize();
```
### Bước 4: Tạo luồng đầu ra
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### Bước 5: Thay đổi kích thước và lưu điểm
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## Thay đổi kích thước EPS bằng inch
Thực hiện theo các bước tương tự như Ví dụ 1, thay thế "Điểm" bằng "Inch" và điều chỉnh kích thước mới cho phù hợp.
## Thay đổi kích thước EPS bằng milimét
Thực hiện theo các bước tương tự như Ví dụ 1, thay thế "Điểm" bằng "Milimet" và điều chỉnh kích thước mới cho phù hợp.
## Thay đổi kích thước EPS bằng Tỷ lệ phần trăm
Thực hiện theo các bước tương tự như Ví dụ 1, thay thế "Điểm" bằng "Phần trăm" và điều chỉnh kích thước mới cho phù hợp.
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách thay đổi kích thước tệp EPS trong Java bằng Aspose.Page. Hướng dẫn này cung cấp cho bạn các tùy chọn linh hoạt, đảm bảo bạn có thể điều chỉnh quy trình thay đổi kích thước để đáp ứng nhu cầu cụ thể của mình.

## Câu hỏi thường gặp
### Tôi có thể sử dụng thư viện này cho các định dạng hình ảnh khác không?
Không, Aspose.Page được thiết kế đặc biệt để xử lý các tệp PostScript và EPS.
### Có bản dùng thử miễn phí cho Aspose.Page cho Java không?
Có, bạn có thể khám phá bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Tôi có thể tìm thêm trợ giúp và thảo luận ở đâu?
 Tham quan[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để hỗ trợ cộng đồng.
### Làm thế nào tôi có thể có được giấy phép tạm thời?
 Bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Có bất kỳ dự án ví dụ nào có sẵn không?
 Có, kiểm tra tài liệu[đây](https://reference.aspose.com/page/java/).