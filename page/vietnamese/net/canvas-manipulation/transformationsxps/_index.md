---
date: 2026-01-05
description: Tìm hiểu cách chuyển đổi tài liệu XPS một cách dễ dàng với Aspose.Page
  cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để có những chuyển đổi
  liền mạch.
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: Cách chuyển đổi XPS bằng Aspose.Page cho .NET
url: /vi/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Chuyển Đổi XPS với Aspose.Page cho .NET

## Giới thiệu

Chào mừng bạn đến với thế giới Aspose.Page cho .NET, một thư viện mạnh mẽ cho phép bạn thực hiện các chuyển đổi khác nhau trên tài liệu XPS một cách dễ dàng. **Trong hướng dẫn này, bạn sẽ khám phá cách chuyển đổi tài liệu XPS bằng Aspose.Page cho .NET**, dù bạn là một nhà phát triển dày dặn kinh nghiệm hay mới bắt đầu. Chúng tôi sẽ hướng dẫn từng bước, giải thích lý do đằng sau mỗi chuyển đổi và cung cấp các mẹo thực tế mà bạn có thể áp dụng trong các dự án thực tế.

## Câu trả lời nhanh
- **Bạn có thể đạt được gì?** Tạo, dịch chuyển, thu phóng và xoay các phần tử canvas XPS một cách lập trình.  
- **Thư viện nào được yêu cầu?** Aspose.Page cho .NET (phiên bản mới nhất).  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho việc phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Các nền tảng được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Thời gian triển khai mất bao lâu?** Khoảng 10‑15 phút cho các chuyển đổi cơ bản được trình bày ở đây.

## “how to transform xps” là gì?
Cụm từ *how to transform xps* đề cập đến việc thay đổi bố cục, kích thước và hướng của các phần tử bên trong tài liệu XPS (XML Paper Specification) một cách lập trình. Sử dụng Aspose.Page, bạn có thể áp dụng các chuyển đổi dựa trên ma trận cho các canvas, cho phép kiểm soát chi tiết vị trí, thu phóng và xoay mà không cần chỉnh sửa XML XPS thủ công.

## Tại sao nên sử dụng Aspose.Page cho việc chuyển đổi XPS?
- **Tích hợp .NET đầy đủ** – hoạt động liền mạch với Visual Studio, Rider và các IDE khác.  
- **Không phụ thuộc bên ngoài** – API xử lý mọi chi tiết XPS cấp thấp cho bạn.  
- **Hỗ trợ chuyển đổi phong phú** – dịch chuyển, thu phóng, xoay và kết hợp nhiều chuyển đổi trong một lời gọi.  
- **Tối ưu hiệu năng** – phù hợp cho việc tạo báo cáo, hoá đơn hoặc bất kỳ đồ họa có thể in ngay lập tức.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

- **Thư viện Aspose.Page cho .NET** – tải xuống và cài đặt từ tài liệu chính thức: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **Môi trường phát triển** – Visual Studio, Visual Studio Code hoặc bất kỳ IDE nào hỗ trợ .NET.  
- **Thư mục tài liệu** – một thư mục trên máy của bạn nơi bạn sẽ đọc/ghi các tệp XPS. Thay thế phần giữ chỗ trong mã bằng đường dẫn thực tế.

Bây giờ chúng ta đã sẵn sàng, hãy đi sâu vào mã.

## Nhập không gian tên

Đầu tiên, nhập các không gian tên cung cấp các lớp Aspose.Page mà bạn sẽ cần:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Cách Chuyển Đổi XPS – Hướng Dẫn Từng Bước

### Bước 1: Tạo tài liệu XPS mới

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Giải thích*: Chúng ta bắt đầu bằng việc xác định thư mục chứa các tệp nguồn và đầu ra, sau đó khởi tạo một `XpsDocument` rỗng. Đối tượng này sẽ là canvas cho tất cả các chuyển đổi tiếp theo.

### Bước 2: Tạo một Canvas chính

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Tại sao điều này quan trọng*: Canvas chính hoạt động như một container cho tất cả các canvas khác. Bằng cách áp dụng một offset nhỏ, chúng ta đảm bảo nội dung không bị cắt ở mép trang.

### Bước 3: Tạo một hình học đường dẫn hình chữ nhật

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Mẹo*: Chuỗi đường dẫn tuân theo cú pháp đường dẫn XPS chuẩn (`M` di chuyển, `L` vẽ đường thẳng, `Z` đóng). Điều chỉnh các tọa độ để thay đổi kích thước hình chữ nhật.

### Bước 4: Thêm màu nền cho các hình chữ nhật

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Pro tip*: Sử dụng `CreateColor` với các giá trị RGB để phù hợp với bảng màu thương hiệu của bạn.

### Bước 5: Thêm một Canvas mới mà không có chuyển đổi

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Ở đây chúng ta chỉ đặt một hình chữ nhật lên trang mà không áp dụng bất kỳ chuyển đổi nào — hữu ích làm phần tử cơ sở.

### Bước 6: Thêm một Canvas mới với chuyển đổi dịch chuyển

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*Điều gì đang xảy ra?* Ma trận đầu tiên di chuyển hình chữ nhật xuống 200 đơn vị. Lệnh `Translate` tiếp theo dịch nó sang phải 500 đơn vị, minh họa cách chuỗi nhiều dịch chuyển có thể được nối tiếp.

### Bước 7: Thêm một Canvas mới với chuyển đổi tỷ lệ gấp đôi

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*Tại sao lại tỷ lệ?* Thu phóng lên 2 lần sẽ gấp đôi chiều rộng và chiều cao của hình chữ nhật, cho phép bạn tạo đồ họa lớn hơn mà không cần định nghĩa lại hình học.

### Bước 8: Thêm một Canvas mới với chuyển đổi xoay quanh một điểm

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Điểm quan trọng*: `RotateAround` xoay canvas quanh một điểm tùy chỉnh (ở đây là (100, 50)), cung cấp kiểm soát chi tiết về trục quay.

### Bước 9: Lưu tài liệu XPS kết quả

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

Sau khi tất cả các chuyển đổi được áp dụng, tài liệu sẽ được lưu vào `output1.xps`. Mở tệp này bằng bất kỳ trình xem XPS nào để thấy các hình chữ nhật xếp chồng với các dịch chuyển, thu phóng và xoay tương ứng.

## Các vấn đề thường gặp & Khắc phục

| Triệu chứng | Nguyên nhân có thể | Cách khắc phục |
|------------|--------------------|----------------|
| Tệp đầu ra trống | `dataDir` trỏ tới thư mục không tồn tại | Đảm bảo thư mục tồn tại hoặc sử dụng đường dẫn tuyệt đối |
| Hình chữ nhật không nằm ở vị trí mong muốn | Giá trị ma trận sai | Kiểm tra lại thứ tự các lời gọi `Translate`, `Scale`, và `RotateAround` |
| Màu sắc hiển thị sai | Giá trị RGB vượt quá phạm vi 0‑255 | Sử dụng các giá trị byte hợp lệ cho mỗi kênh |

## Câu hỏi thường gặp

**H: Aspose.Page cho .NET có tương thích với mọi môi trường phát triển .NET không?**  
Đ: Có, nó hoạt động liền mạch với Visual Studio, Visual Studio Code, Rider và bất kỳ IDE nào hỗ trợ .NET.

**H: Tôi có thể tìm thêm ví dụ và tài liệu API chi tiết ở đâu?**  
Đ: Tham khảo tài liệu chính thức tại [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**H: Tôi có thể dùng thử Aspose.Page trước khi mua giấy phép không?**  
Đ: Chắc chắn. Bản dùng thử miễn phí có sẵn tại: [Aspose.Page Free Trial](https://releases.aspose.com/).

**H: Làm sao để tôi nhận được giấy phép tạm thời để thử nghiệm?**  
Đ: Bạn có thể yêu cầu qua trang giấy phép tạm thời: [Temporary License](https://purchase.aspose.com/temporary-license/).

**H: Tôi mua giấy phép đầy đủ ở đâu?**  
Đ: Mua trực tiếp từ cửa hàng Aspose: [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**Cập nhật lần cuối:** 2026-01-05  
**Được kiểm tra với:** Aspose.Page 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}