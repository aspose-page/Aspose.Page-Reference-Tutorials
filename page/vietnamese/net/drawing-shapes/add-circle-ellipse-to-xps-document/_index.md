---
title: Thêm hình elip hình tròn vào tài liệu XPS bằng Aspose.Page for .NET
linktitle: Thêm hình elip hình tròn vào tài liệu XPS
second_title: API Aspose.Page .NET
description: Nâng cao tài liệu XPS với độ dốc xuyên tâm sống động bằng Aspose.Page for .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để có được hiệu ứng hình ảnh ấn tượng.
weight: 11
url: /vi/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm hình elip hình tròn vào tài liệu XPS bằng Aspose.Page for .NET

## Giới thiệu

Tạo các tài liệu XPS hấp dẫn trực quan là một yêu cầu phổ biến trong các ứng dụng khác nhau. Aspose.Page for .NET cung cấp một bộ tính năng mạnh mẽ để thao tác các tài liệu XPS một cách hiệu quả. Trong hướng dẫn này, chúng tôi sẽ tập trung vào việc thêm hình elip hình tròn vào tài liệu XPS bằng Aspose.Page cho .NET. Thực hiện theo các bước bên dưới để cải thiện tài liệu XPS của bạn với độ dốc xuyên tâm sống động.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

-  Đã cài đặt Aspose.Page cho thư viện .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/page/net/).
- Môi trường phát triển, tốt nhất là Visual Studio hoặc bất kỳ công cụ phát triển .NET nào khác.
- Kiến thức cơ bản về lập trình C#.

## Nhập không gian tên

Để bắt đầu, hãy bao gồm các vùng tên cần thiết trong mã C# của bạn:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Bây giờ, hãy chia ví dụ thành nhiều bước:

## Bước 1: Thiết lập tài liệu

```csharp
// Bắt đầu:1
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";
// Tạo tài liệu XPS mới
XpsDocument doc = new XpsDocument();
```

Ở đây, chúng tôi khởi tạo tài liệu XPS mới bằng Aspose.Page cho .NET.

## Bước 2: Xác định hình elip gradient xuyên tâm

```csharp
// Hình elip có nét chuyển động hướng tâm ở phía dưới bên trái
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

Bước này liên quan đến việc xác định một hình elip có độ dốc hướng tâm với nhiều điểm dừng màu khác nhau.

## Bước 3: Đặt cọ chuyển động xuyên tâm

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

Ở đây, chúng ta đặt nét vẽ của hình elip thành một cọ gradient xuyên tâm, cung cấp cho nó các tham số cần thiết.

## Bước 4: Điều chỉnh độ dày nét

```csharp
path.StrokeThickness = 12f;
```

Bước này liên quan đến việc điều chỉnh độ dày của nét vẽ để hình dung rõ hơn.

## Bước 5: Lưu tài liệu XPS kết quả

```csharp
// Lưu tài liệu XPS kết quả
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// ExEnd:1
```

Cuối cùng, lưu tài liệu XPS đã sửa đổi vào vị trí mong muốn.

## Phần kết luận

Chúc mừng! Bạn đã thêm thành công hình elip hình tròn có chuyển màu hướng tâm vào tài liệu XPS của mình bằng Aspose.Page for .NET. Thử nghiệm với các thông số và màu sắc khác nhau để đạt được hiệu ứng hình ảnh mong muốn trong tài liệu của bạn.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể sử dụng Aspose.Page cho .NET với các định dạng tài liệu khác không?

Câu trả lời 1: Aspose.Page dành cho .NET xử lý cụ thể thao tác với tài liệu XPS. Đối với các định dạng khác, hãy cân nhắc sử dụng các thư viện Aspose có liên quan.

### Câu hỏi 2: Giấy phép tạm thời có sẵn cho mục đích thử nghiệm không?

 Câu trả lời 2: Có, bạn có thể lấy giấy phép tạm thời để thử nghiệm bằng cách truy cập[liên kết này](https://purchase.aspose.com/temporary-license/).

### Câu hỏi 3: Tôi có thể tìm thêm trợ giúp và thảo luận ở đâu?

 A3: Tham quan[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để được cộng đồng hỗ trợ và thảo luận.

### Q4: Có tài liệu mẫu nào để tham khảo không?

 A4: Khám phá[tài liệu](https://reference.aspose.com/page/net/) để có những ví dụ và hướng dẫn toàn diện.

### Câu hỏi 5: Tôi có thể mua Aspose.Page cho .NET không?

 A5: Có, bạn có thể mua thư viện[đây](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
