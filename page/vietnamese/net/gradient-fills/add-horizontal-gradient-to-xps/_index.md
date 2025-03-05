---
title: Thêm gradient ngang vào XPS với Aspose.Page for .NET
linktitle: Thêm độ dốc ngang vào XPS
second_title: API Aspose.Page .NET
description: Tìm hiểu cách thêm độ dốc ngang tuyệt đẹp vào tài liệu XPS của bạn bằng Aspose.Page cho .NET. Nâng cao sự hấp dẫn trực quan một cách dễ dàng.
type: docs
weight: 13
url: /vi/net/gradient-fills/add-horizontal-gradient-to-xps/
---
## Giới thiệu

Trong hướng dẫn này, chúng ta sẽ khám phá cách nâng cao tài liệu XPS bằng cách thêm dải màu ngang bằng Aspose.Page cho .NET. Aspose.Page for .NET là một thư viện mạnh mẽ cung cấp khả năng xử lý liền mạch các tài liệu XPS (Đặc tả giấy XML) trong các ứng dụng .NET. Việc thêm độ dốc có thể mang lại sự hấp dẫn trực quan cho tài liệu của bạn và hướng dẫn này sẽ hướng dẫn bạn từng bước thực hiện quy trình.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1.  Aspose.Page for .NET Library: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.Page for .NET trong môi trường phát triển của mình. Bạn có thể tải nó xuống từ[Aspose.Page cho Tài liệu .NET](https://reference.aspose.com/page/net/).

2. Môi trường phát triển: Thiết lập môi trường phát triển phù hợp, bao gồm trình soạn thảo mã như Visual Studio.

## Nhập không gian tên

Bắt đầu bằng cách nhập các không gian tên cần thiết vào dự án của bạn. Các không gian tên này rất cần thiết để làm việc với Aspose.Page cho .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Bây giờ, hãy chia ví dụ được cung cấp thành nhiều bước.

## Bước 1: Đặt đường dẫn thư mục tài liệu

```csharp
// Bắt đầu:3
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Bước 2: Tạo tài liệu XPS mới

```csharp
// ExStart:4
// Tạo tài liệu XPS mới
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Bước 3: Khởi tạo các điểm dừng chuyển màu

```csharp
// ExStart:5
// Khởi tạo danh sách XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Bước 4: Tạo đường dẫn mới

```csharp
// ExStart:6
//Tạo đường dẫn mới bằng cách xác định hình học ở dạng viết tắt
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Bước 5: Lưu tài liệu XPS kết quả

```csharp
// ExStart:7
// Lưu tài liệu XPS kết quả
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Bây giờ, bạn đã thêm thành công dải màu ngang vào tài liệu XPS của mình bằng Aspose.Page cho .NET.

## Phần kết luận

Cải thiện tài liệu XPS của bạn bằng độ dốc không chỉ cải thiện sự hấp dẫn trực quan của chúng mà còn mang lại trải nghiệm người dùng hấp dẫn hơn. Aspose.Page for .NET đơn giản hóa quy trình này, cho phép bạn đạt được kết quả chuyên nghiệp một cách dễ dàng.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể tìm tài liệu Aspose.Page cho .NET ở đâu?

 A1: Bạn có thể tìm tài liệu[đây](https://reference.aspose.com/page/net/).

### Câu hỏi 2: Làm cách nào để tải xuống Aspose.Page cho .NET?

 A2: Bạn có thể tải xuống thư viện từ[Trang tải xuống Aspose.Page cho .NET](https://releases.aspose.com/page/net/).

### Câu 3: Tôi có thể mua Aspose.Page cho .NET ở đâu?

 Câu trả lời 3: Bạn có thể mua Aspose.Page cho .NET từ[trang mua hàng](https://purchase.aspose.com/buy).

### Q4: Có bản dùng thử miễn phí không?

 Đ4: Có, bạn có thể dùng thử miễn phí từ[đây](https://releases.aspose.com/).

### Câu hỏi 5: Làm cách nào để có được giấy phép tạm thời cho Aspose.Page cho .NET?

 Câu trả lời 5: Bạn có thể xin giấy phép tạm thời từ[liên kết này](https://purchase.aspose.com/temporary-license/).