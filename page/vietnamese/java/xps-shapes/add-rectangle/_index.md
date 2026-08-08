---
date: 2026-04-24
description: Tìm hiểu cách đặt màu cho hình chữ nhật và thêm hình chữ nhật trong Java
  XPS bằng Aspose.Page. Hướng dẫn này bao gồm cách thêm hình chữ nhật trong Java và
  thay đổi nét viền của hình chữ nhật.
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: Thêm hình chữ nhật trong Java XPS
second_title: Aspose.Page Java API
title: Thiết lập màu hình chữ nhật và Thêm hình chữ nhật trong Java XPS
url: /vi/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt màu hình chữ nhật và Thêm hình chữ nhật trong Java XPS

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học cách **set rectangle color** và **add a rectangle** trong Java XPS bằng thư viện Aspose.Page. Cho dù bạn cần vẽ các hình đơn giản cho báo cáo hoặc tạo đồ họa vector phức tạp, việc thành thạo cách định dạng hình chữ nhật sẽ cho bạn khả năng kiểm soát chính xác tài liệu XPS.  

## Câu trả lời nhanh
- **Thư viện nào được yêu cầu?** Aspose.Page for Java  
- **Có thể thay đổi đường viền của hình chữ nhật không?** Yes, using `setStroke` and `setStrokeThickness`  
- **Có hỗ trợ hồ sơ màu CMYK không?** Chắc chắn – bạn có thể tải hồ sơ ICC như đã chỉ ra  
- **Có cần giấy phép cho môi trường sản xuất không?** Có, cần giấy phép thương mại cho việc sử dụng không phải để đánh giá  
- **Thời gian triển khai mất bao lâu?** Thông thường dưới 10 phút cho một hình chữ nhật cơ bản

## **set rectangle color** là gì?
Đặt màu cho hình chữ nhật có nghĩa là xác định màu nền hoặc màu viền mà hình sẽ hiển thị trong tài liệu XPS cuối cùng. Với Aspose.Page, bạn có thể sử dụng RGB, CMYK, hoặc thậm chí các hồ sơ màu ICC tùy chỉnh để đạt được sự khớp màu chính xác.

## Tại sao nên sử dụng Aspose.Page để **add rectangle java** và **change rectangle stroke**?
- **Full‑featured API** – hỗ trợ cả màu đặc và gradient.  
- **Cross‑platform** – hoạt động trên bất kỳ môi trường Java nào mà không cần phụ thuộc gốc.  
- **Rich geometry support** – tạo các đường dẫn phức tạp, áp dụng biến đổi và quản lý độ dày viền một cách dễ dàng.  

## Yêu cầu trước
Trước khi chúng ta bắt đầu với mã, hãy đảm bảo bạn có:

- Kiến thức cơ bản về lập trình Java.  
- Thư viện Aspose.Page đã được cài đặt. Nếu chưa, tải xuống từ [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
- Môi trường phát triển Java hoạt động (IDE, JDK, v.v.).  

## Nhập gói
Để bắt đầu, nhập các gói cần thiết vào dự án Java của bạn. Đảm bảo rằng thư viện Aspose.Page đã được thêm đúng vào classpath. Dưới đây là một ví dụ cơ bản:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Bây giờ, chúng ta sẽ phân tích ví dụ đã cung cấp thành nhiều bước để **add a rectangle** và **set its color** trong Java XPS.

## Bước 1: Đặt thư mục tài liệu
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
Thay thế `"Your Document Directory"` bằng đường dẫn tuyệt đối nơi bạn muốn đọc/ghi các tệp XPS.

## Bước 2: Tạo tài liệu XPS mới
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
Dòng này khởi tạo một tài liệu XPS mới sẽ chứa các hình dạng của chúng ta.

## Bước 3: Thêm hình chữ nhật viền màu CMYK đặc
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Bước này thêm một **stroked rectangle** với màu CMYK đặc. Phương thức `setStroke` xác định màu viền của hình chữ nhật, trong khi `setStrokeThickness` kiểm soát độ rộng đường—hoàn hảo cho **changing rectangle stroke**.

### Mẹo chuyên nghiệp:
Nếu bạn muốn màu RGB, hãy thay thế lời gọi `createColor` bằng `doc.createColor(0, 0, 255)` để tạo màu xanh đậm đặc.

## Bước 4: Lưu tài liệu XPS kết quả
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
Cuối cùng, lưu tài liệu XPS vào đĩa. Tệp `AddRectangle_out.xps` hiện chứa một hình chữ nhật với màu và viền mà bạn đã định nghĩa.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|------------|----------|
| **Hình chữ nhật không hiển thị** | Đường dẫn không đúng hoặc độ dày viền được đặt bằng 0 | Kiểm tra chuỗi đường dẫn (`"M 20,10 L 220,10 220,100 20,100 Z"`) và đảm bảo `setStrokeThickness` lớn hơn 0. |
| **Màu sai** | Sử dụng hồ sơ ICC không khớp với không gian màu mong muốn | Sử dụng `doc.createColor(r, g, b)` cho RGB hoặc kiểm tra lại đường dẫn tệp ICC. |
| **Tệp không được lưu** | `dataDir` trỏ tới thư mục không tồn tại hoặc thiếu quyền ghi | Tạo thư mục trước hoặc chọn vị trí có thể ghi. |

## Câu hỏi thường gặp

**Q:** *Có thể thêm nhiều hình chữ nhật trong một tài liệu XPS duy nhất không?*  
A: Có. Chỉ cần lặp lại các bước tạo hình học và định dạng cho mỗi hình chữ nhật bạn cần.

**Q:** *Làm sao để thay đổi màu nền của hình chữ nhật thay vì màu viền?*  
A: Sử dụng `path.setFill(...)` với một brush màu đặc, tương tự như cách sử dụng `setStroke`.

**Q:** *Aspose.Page có phù hợp cho việc thao tác tài liệu XPS phức tạp không?*  
A: Chắc chắn. Thư viện hỗ trợ các tính năng nâng cao như gradient, biến đổi và phông chữ nhúng.

**Q:** *Tôi có thể tìm các ví dụ bổ sung và hỗ trợ cộng đồng ở đâu?*  
A: Khám phá [Aspose.Page forum](https://forum.aspose.com/c/page/39) để xem thêm mẫu mã và hỗ trợ từ cộng đồng.

**Q:** *Tôi có thể dùng thử Aspose.Page trước khi mua không?*  
A: Có, bạn có thể khám phá một [free trial](https://releases.aspose.com/) để đánh giá khả năng của API.

---

**Cập nhật lần cuối:** 2026-04-24  
**Được kiểm tra với:** Aspose.Page for Java 24.12  
**Tác giả:** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}