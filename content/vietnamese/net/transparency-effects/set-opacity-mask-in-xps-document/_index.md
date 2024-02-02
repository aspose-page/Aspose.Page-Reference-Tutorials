---
title: Đặt Mặt nạ độ mờ trong Tài liệu XPS với Aspose.Page cho .NET
linktitle: Đặt mặt nạ độ mờ trong tài liệu XPS
second_title: API Aspose.Page .NET
description: Tìm hiểu cách đặt mặt nạ độ mờ trong tài liệu XPS bằng Aspose.Page cho .NET. Nâng cao tính thẩm mỹ của tài liệu một cách dễ dàng.
type: docs
weight: 12
url: /vi/net/transparency-effects/set-opacity-mask-in-xps-document/
---
## Giới thiệu

Mặt nạ độ mờ rất cần thiết khi bạn muốn tạo các tài liệu hấp dẫn trực quan với các mức độ trong suốt khác nhau. Aspose.Page for .NET đơn giản hóa quy trình này, cung cấp cho các nhà phát triển một bộ công cụ toàn diện để nâng cao tài liệu XPS. Trong hướng dẫn này, chúng ta sẽ khám phá cách đặt mặt nạ độ mờ trong hướng dẫn từng bước.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

-  Aspose.Page for .NET: Đảm bảo bạn đã cài đặt thư viện. Nếu không, bạn có thể tải xuống từ[trang mạng](https://releases.aspose.com/page/net/).

- Thư mục Tài liệu: Thiết lập thư mục để lưu trữ tài liệu XPS của bạn.

## Nhập không gian tên

Trong dự án .NET của bạn, hãy bắt đầu bằng cách nhập các vùng tên cần thiết:

```csharp
using Aspose.Page.Xps;
using Aspose.Page.Xps.XpsModel;
using Aspose.Page.Xps.XpsModel.Shapes;
using Aspose.Page.Xps.XpsModel.Text;
using System.Drawing;
```

## Bước 1: Tạo tài liệu XPS mới

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";
// Tạo tài liệu XPS mới
XpsDocument doc = new XpsDocument();
```

Bắt đầu bằng cách tạo tài liệu XPS mới bằng Aspose.Page cho .NET.

## Bước 2: Thêm Canvas vào phiên bản XpsDocument

```csharp
// Thêm Canvas vào phiên bản XpsDocument
XpsCanvas canvas = doc.AddCanvas();
```

Bây giờ, hãy thêm canvas vào tài liệu XPS. Canvas sẽ đóng vai trò là nơi chứa các phần tử đồ họa khác nhau.

## Bước 3: Thêm hình chữ nhật với Opacity Mask

```csharp
// Hình chữ nhật có độ mờ được che bởi ImageBrush
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.OpacityMask = doc.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)path.OpacityMask).TileMode = XpsTileMode.Tile;
```

 Thêm một hình chữ nhật vào khung vẽ và đặt độ mờ của nó bằng cách sử dụng`OpacityMask`tài sản. Trong ví dụ này, chúng tôi đang sử dụng một hình ảnh làm mặt nạ độ mờ.

## Bước 4: Lưu tài liệu XPS kết quả

```csharp
// Lưu tài liệu XPS kết quả
doc.Save(dataDir + "OpacityMask_out.xps");
```

Cuối cùng, lưu tài liệu XPS đã sửa đổi với mặt nạ độ mờ được áp dụng.

## Phần kết luận

Chúc mừng! Bạn đã học thành công cách đặt mặt nạ độ mờ trong tài liệu XPS bằng Aspose.Page cho .NET. Tính năng này mở ra nhiều khả năng sáng tạo để thiết kế các tài liệu phức tạp và hấp dẫn về mặt hình ảnh.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể áp dụng mặt nạ độ mờ cho các hình dạng khác ngoài hình chữ nhật không?

Câu trả lời 1: Có, Aspose.Page dành cho .NET cho phép bạn áp dụng mặt nạ độ mờ cho nhiều hình dạng khác nhau, bao gồm hình tròn, đa giác và đường dẫn tùy chỉnh.

### Câu hỏi 2: Mặt nạ độ mờ có bị giới hạn ở hình ảnh không?

Câu trả lời 2: Không, mặc dù hướng dẫn này sử dụng hình ảnh làm mặt nạ độ mờ, nhưng bạn có thể sử dụng các màu đồng nhất, độ chuyển màu hoặc thậm chí các mẫu.

### Câu hỏi 3: Có các tùy chọn nâng cao để tinh chỉnh mức độ mờ không?

Câu trả lời 3: Hoàn toàn có thể, Aspose.Page dành cho .NET cung cấp khả năng kiểm soát chi tiết đối với cài đặt độ mờ, cho phép bạn đạt được hiệu ứng trong suốt chính xác.

### Câu hỏi 4: Tôi có thể áp dụng nhiều mặt nạ độ mờ cho một phần tử không?

Câu trả lời 4: Có, bạn có thể xếp lớp nhiều mặt nạ độ mờ để tạo hiệu ứng trong suốt phức tạp.

### Câu hỏi 5: Aspose.Page có tương thích với các định dạng tài liệu khác không?

Câu trả lời 5: Aspose.Page chủ yếu tập trung vào các tài liệu XPS, nhưng Aspose cung cấp nhiều sản phẩm để xử lý các định dạng khác nhau.