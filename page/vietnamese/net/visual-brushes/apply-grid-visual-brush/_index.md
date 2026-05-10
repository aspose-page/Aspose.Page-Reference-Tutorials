---
date: 2026-04-03
description: Tìm hiểu cách thêm một hình chữ nhật trong suốt và áp dụng Grid Visual
  Brush trong .NET bằng Aspose.Page để tạo các tài liệu XPS ấn tượng.
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: Áp dụng Brush trực quan lưới
second_title: Aspose.Page .NET API
title: Thêm hình chữ nhật trong suốt sử dụng Grid Visual Brush (.NET)
url: /vi/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm Hình Chữ Nhật Trong Suốt bằng Grid Visual Brush (.NET)

## Giới thiệu

Nếu bạn đang muốn **thêm một hình chữ nhật trong suốt** vào tài liệu XPS đồng thời áp dụng một Grid Visual Brush phong cách, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ đi qua các bước chính xác cần thiết với Aspose.Page cho .NET, để bạn có thể tạo ra các tài liệu giàu hình ảnh nổi bật. Khi hoàn thành, bạn sẽ có một ví dụ hoàn chỉnh, có thể chạy được, minh họa cả hai kỹ thuật trong một quy trình dễ‑theo.

## Câu trả lời nhanh
- **Hình chữ nhật trong suốt làm gì?** Nó thêm một lớp phủ bán trong suốt cho phép nội dung nền hiển thị qua.  
- **API nào tạo brush?** `XpsDocument.CreateVisualBrush` tạo Grid Visual Brush.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho việc thử nghiệm; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Thời gian thực hiện khoảng bao nhiêu?** Khoảng 10‑15 phút cho một ví dụ cơ bản.

## Hình chữ nhật trong suốt trong XPS là gì?
Hình chữ nhật trong suốt đơn giản là một hình dạng có màu nền bao gồm thành phần alpha nhỏ hơn 1.0, cho phép các đồ họa nền hiển thị một phần. Điều này hoàn hảo để làm nổi bật các phần mà không che khuất hoàn toàn nền.

## Tại sao nên sử dụng Grid Visual Brush?
Grid Visual Brush cho phép bạn lặp lại một đồ họa vector nhỏ trên một khu vực lớn, tạo ra các mẫu như lưới, vằn hoặc kết cấu tùy chỉnh. Kết hợp nó với một hình chữ nhật trong suốt sẽ cho bạn các hiệu ứng lớp phủ vừa nhẹ vừa độc lập với độ phân giải.

## Yêu cầu trước

Trước khi bắt đầu viết mã, hãy chắc chắn rằng bạn đã có:

- **Aspose.Page for .NET** – bạn có thể tải xuống [tại đây](https://releases.aspose.com/page/net/).
- Môi trường phát triển .NET (Visual Studio, VS Code, hoặc bất kỳ IDE nào bạn thích).
- Một thư mục để lưu các tệp XPS được tạo.

## Nhập không gian tên

Trong tệp C# của bạn, nhập các không gian tên cần thiết:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Bây giờ chúng ta sẽ chia giải pháp thành các bước rõ ràng, được đánh số.

## Bước 1: Khởi tạo XpsDocument

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

Chúng ta bắt đầu bằng việc tạo một thể hiện `XpsDocument`, nơi sẽ chứa tất cả các thao tác vẽ tiếp theo.

## Bước 2: Tạo hình học lưới màu hồng

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

Hình học này xác định đường viền của lưới mà visual brush sẽ lấp đầy.

## Bước 3: Thiết kế Magenta Grid VisualBrush

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

Ở đây chúng ta vẽ một ô gạch màu hồng nhỏ sẽ được lặp lại trên toàn lưới.

## Bước 4: Áp dụng VisualBrush lên Grid

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

Lệnh `CreateVisualBrush` liên kết ô gạch màu hồng với hình học lưới và cho phép lặp lại.

## Bước 5: Thêm Grid vào Canvas

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

Chúng ta đặt lưới đã lặp lại lên một canvas và áp dụng phép biến đổi dịch chuyển để nó xuất hiện ở vị trí mong muốn.

## Bước 6: Thêm hình chữ nhật trong suốt

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

Trong bước này chúng ta **thêm một hình chữ nhật trong suốt** (hình đỏ với `Opacity = 0.7f`). Điều chỉnh giá trị opacity để kiểm soát mức độ trong suốt của hình chữ nhật.

## Bước 7: Lưu tài liệu

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

Tệp XPS sẽ được ghi vào thư mục bạn đã chỉ định trước đó.

## Các trường hợp sử dụng phổ biến

- **Làm nổi bật báo cáo:** Đặt lớp phủ bán trong suốt lên để nhấn mạnh biểu đồ hoặc bảng.  
- **Hiệu ứng watermark:** Kết hợp lưới lặp lại với lớp phủ trong suốt để tạo thương hiệu nhẹ nhàng.  
- **PDF/XPS tương tác:** Sử dụng mẫu làm nền cho các trường biểu mẫu trong khi giữ giao diện người dùng dễ đọc.

## Mẹo khắc phục sự cố

- **Opacity không hiển thị?** Đảm bảo trình xem của bạn hỗ trợ độ trong suốt XPS; một số trình xem cũ có thể bỏ qua thuộc tính `Opacity`.  
- **Kích thước tile không đúng?** Kiểm tra hình chữ nhật nguồn (`new RectangleF(0f, 0f, 10f, 10f)`) có khớp với kích thước của tile vector không.  
- **File không được lưu?** Kiểm tra lại `dataDir` trỏ tới thư mục tồn tại và có quyền ghi.

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Page cho .NET trong cả ứng dụng web và desktop không?**  
A: Có, thư viện hoạt động trên mọi loại ứng dụng .NET.

**Q: Có phiên bản dùng thử nào trước khi mua không?**  
A: Chắc chắn, bạn có thể truy cập bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

**Q: Tôi có thể tìm hỗ trợ bổ sung hoặc thảo luận cộng đồng ở đâu?**  
A: Ghé thăm [Aspose.Page Forum](https://forum.aspose.com/c/page/39) để nhận trợ giúp từ cộng đồng và các kỹ sư Aspose.

**Q: Làm sao để có được giấy phép tạm thời để đánh giá?**  
A: Bạn có thể lấy giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

**Q: Tài liệu khác nào có sẵn cho Aspose.Page cho .NET?**  
A: Khám phá tài liệu đầy đủ [tại đây](https://reference.aspose.com/page/net/).

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}