---
date: 2026-02-23
description: Học cách tạo tài liệu XPS với gradient chéo bằng Aspose.Page cho .NET
  và nâng cao các bài thuyết trình trực quan của bạn một cách dễ dàng.
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: Tạo XPS Độ chuyển màu chéo với Aspose.Page cho .NET
url: /vi/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo XPS Gradient Chéo với Aspose.Page cho .NET

## Giới thiệu

Nếu bạn cần **tạo XPS gradient chéo** thu hút mắt, Aspose.Page cho .NET giúp thực hiện một cách đơn giản. Trong hướng dẫn này, bạn sẽ học cách thêm gradient chéo vào tài liệu XPS, từng bước, bằng API Aspose.Page. Khi hoàn thành, bạn sẽ có một mẫu có thể tái sử dụng và áp dụng cho bất kỳ hình dạng hoặc bảng màu nào.

## Câu trả lời nhanh
- **Phương thức API làm gì?** Nó tạo một brush gradient tuyến tính trải dài chéo qua một đường dẫn.  
- **Lớp nào đại diện cho tài liệu XPS?** `XpsDocument`.  
- **Tôi có cần giấy phép để chạy mẫu không?** Bản dùng thử miễn phí hoạt động cho phát triển; cần giấy phép cho môi trường sản xuất.  
- **Tôi có thể thay đổi hướng gradient không?** Có—điều chỉnh các giá trị `PointF` bắt đầu và kết thúc.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## **create diagonal gradient xps** là gì?
Gradient chéo là sự chuyển đổi màu mượt mà chạy từ một góc của hình tới góc đối diện. Trong XPS, hiệu ứng này đạt được bằng cách áp dụng `LinearGradientBrush` vào thuộc tính fill của một đường dẫn. Thư viện Aspose.Page trừu tượng hoá markup XPS cấp thấp, cho phép bạn tập trung vào màu sắc và hình học.

## Tại sao nên sử dụng Aspose.Page cho gradient chéo?
- **Kết xuất độ trung thực cao** – đầu ra khớp chính xác với đặc tả XPS.  
- **Tích hợp đầy đủ .NET** – hoạt động với C#, VB.NET và bất kỳ ngôn ngữ .NET nào.  
- **Không phụ thuộc bên ngoài** – mọi thứ được xử lý trong tiến trình, không cần COM hay Office.  
- **Mở rộng cho tài liệu phức tạp** – bạn có thể kết hợp nhiều gradient, hình ảnh và văn bản trên cùng một trang.

## Yêu cầu trước

1. **Thư viện Aspose.Page cho .NET** – tải xuống [tại đây](https://releases.aspose.com/page/net/).  
2. **Môi trường phát triển** – Visual Studio, Rider, hoặc bất kỳ trình soạn thảo nào hỗ trợ dự án .NET.  

Bây giờ, chúng ta hãy đi sâu vào mã.

## Nhập các Namespace

Trong dự án .NET của bạn, bao gồm các namespace cần thiết từ thư viện Aspose.Page để truy cập các lớp và phương thức yêu cầu. Thêm các namespace sau vào đầu mã của bạn:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Bước 1: Đặt Thư mục Tài liệu

Bắt đầu bằng cách chỉ định đường dẫn tới thư mục tài liệu của bạn. Đây là nơi tài liệu XPS kết quả với gradient chéo sẽ được lưu.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Bước 2: Tạo Tài liệu XPS Mới

Khởi tạo một `XpsDocument` mới bằng thư viện Aspose.Page.

```csharp
XpsDocument doc = new XpsDocument();
```

## Bước 3: Định Nghĩa Màu Gradient

Tạo một danh sách các đối tượng `XpsGradientStop`, mỗi đối tượng đại diện cho một màu trong gradient chéo.

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## Bước 4: Thêm Gradient Chéo vào Đường Dẫn

Tạo một đường dẫn mới với hình học đã định nghĩa, và áp dụng gradient chéo cho nó. Điều chỉnh biến đổi render và các thuộc tính fill khi cần.

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## Bước 5: Lưu Tài liệu XPS Kết quả

Cuối cùng, lưu tài liệu XPS đã chỉnh sửa vào thư mục đã chỉ định.

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

Bạn đã **tạo thành công một tệp XPS gradient chéo**. Hãy tự do thử nghiệm với các điểm dừng màu khác nhau, chuỗi hình học, hoặc ma trận biến đổi để tạo ra nhiều hiệu ứng hình ảnh đa dạng.

## Vấn đề Thường gặp và Giải pháp
- **Gradient không hiển thị** – Kiểm tra xem hình học đường dẫn có đóng kín không và các điểm bắt đầu/kết thúc của brush có nằm trong giới hạn đường dẫn không.  
- **Màu không đúng** – Đảm bảo bạn sử dụng `CreateColor` với các giá trị ARGB chính xác; phương thức yêu cầu giá trị trong khoảng 0‑255.  
- **Tệp không được lưu** – Kiểm tra `dataDir` trỏ tới thư mục tồn tại và ứng dụng có quyền ghi.

## Câu hỏi thường gặp

**Q: Tôi có thể áp dụng nhiều gradient cho các phần khác nhau của tài liệu không?**  
A: Có, bạn có thể tạo nhiều đường dẫn và áp dụng các gradient riêng biệt cho mỗi đường dẫn.

**Q: Có các kiểu gradient được định trước không?**  
A: Aspose.Page cho phép tạo gradient tùy chỉnh, cung cấp cho bạn toàn quyền kiểm soát quá trình chuyển đổi màu.

**Q: Tôi có thể sử dụng Aspose.Page cho .NET với các định dạng tài liệu khác không?**  
A: Aspose.Page chủ yếu tập trung vào việc thao tác tài liệu XPS.

**Q: Làm sao để xử lý lỗi liên quan đến xử lý tài liệu?**  
A: Tham khảo [tài liệu](https://reference.aspose.com/page/net/) để biết các thực hành tốt nhất về xử lý lỗi.

**Q: Có phiên bản dùng thử trước khi mua không?**  
A: Có, bạn có thể khám phá [bản dùng thử miễn phí](https://releases.aspose.com/) để trải nghiệm Aspose.Page cho .NET.

**Q: Làm sao để thay đổi hướng gradient thành dọc hoặc ngang?**  
A: Sửa các đối số `PointF` trong `CreateLinearGradientBrush` để đặt các điểm bắt đầu và kết thúc mới.

**Q: Thư viện có hỗ trợ độ trong suốt trong gradient không?**  
A: Có—bao gồm giá trị alpha khi tạo màu bằng `CreateColor`.

## Kết luận

Aspose.Page cho .NET đơn giản hoá quá trình nâng cao tài liệu XPS bằng gradient chéo. Hướng dẫn này đã đưa bạn qua mọi bước từ thiết lập yêu cầu trước tới lưu tệp cuối cùng. Tiếp tục thử nghiệm với các hình dạng và bảng màu khác nhau để làm cho báo cáo, brochure hoặc hoá đơn XPS của bạn thực sự nổi bật.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2026-02-23  
**Đã kiểm tra với:** Aspose.Page 24.11 cho .NET  
**Tác giả:** Aspose  

---