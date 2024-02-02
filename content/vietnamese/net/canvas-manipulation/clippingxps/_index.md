---
title: Cắt XPS bằng Aspose.Page cho .NET
linktitle: Cắt XPS
second_title: API Aspose.Page .NET
description: Khám phá sức mạnh của Aspose.Page cho .NET trong hướng dẫn từng bước này về cách cắt tài liệu XPS. Tạo, thao tác và lưu tệp XPS một cách dễ dàng.
type: docs
weight: 11
url: /vi/net/canvas-manipulation/clippingxps/
---
## Giới thiệu

Chào mừng bạn đến với hướng dẫn toàn diện này về Cắt XPS bằng Aspose.Page cho .NET! Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo, thao tác và lưu tài liệu XPS bằng Aspose.Page cho .NET. XPS, hay Đặc tả giấy XML, là định dạng tài liệu mở và được chuẩn hóa, đồng thời Aspose.Page for .NET cung cấp các công cụ mạnh mẽ để làm việc với tài liệu XPS trong các ứng dụng .NET của bạn.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

- Visual Studio được cài đặt trên máy của bạn.
-  Thư viện Aspose.Page cho .NET được thêm vào dự án của bạn. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/page/net/).
- Kiến thức cơ bản về ngôn ngữ lập trình C#.

## Nhập không gian tên

Để sử dụng Aspose.Page cho các chức năng .NET, bạn cần nhập các vùng tên cần thiết vào dự án của mình. Thực hiện theo các bước sau:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Bây giờ, hãy chia mã ví dụ bạn đã cung cấp thành nhiều bước.

## Bước 1: Đặt đường dẫn thư mục tài liệu.

```csharp
string dataDir = "Your Document Directory";
```

Đảm bảo thay thế "Thư mục tài liệu của bạn" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 2: Tạo một tài liệu XPS mới.

```csharp
XpsDocument doc = new XpsDocument();
```

Thao tác này sẽ tạo một tài liệu XPS mới mà bạn sẽ làm việc.

## Bước 3: Tạo canvas chính.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

Bước này tạo canvas chính, chung cho tất cả các thành phần trang.

## Bước 4: Đặt offset bên trái và trên cùng trong khung vẽ chính.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Điều chỉnh offset bên trái và trên cùng theo yêu cầu của bạn.

## Bước 5: Tạo hình học đường dẫn hình chữ nhật.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

Điều này tạo ra một đường dẫn hình học cho một hình chữ nhật.

## Bước 6: Tạo màu tô cho hình chữ nhật.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Xác định màu tô cho hình chữ nhật.

## Bước 7: Thêm một khung vẽ khác có kẹp vào khung vẽ chính.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

Bước này thêm một canvas khác vào canvas chính.

## Bước 8: Tạo hình tròn cho clip.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Điều này tạo ra một hình dạng clip tròn và áp dụng nó cho khung vẽ thứ hai.

## Bước 9: Tạo một hình chữ nhật trong khung vẽ thứ hai và tô màu nó.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Bước này tạo một hình chữ nhật trong khung vẽ thứ hai và tô màu nó.

## Bước 10: Thêm khung vẽ thứ hai có hình chữ nhật được vuốt vào khung vẽ chính.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

Điều này thêm một canvas khác vào canvas chính.

## Bước 11: Tạo một hình chữ nhật trong khung vẽ thứ ba và vuốt nó.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

Thao tác này sẽ tạo một hình chữ nhật trong khung vẽ thứ ba và áp dụng một nét vẽ cho nó.

## Bước 12: Lưu tài liệu XPS thu được.

```csharp
doc.Save(dataDir + "output2.xps");
```

Thao tác này sẽ lưu tài liệu XPS vào thư mục được chỉ định.

## Phần kết luận

Chúc mừng! Bạn đã học thành công cách cắt XPS bằng Aspose.Page cho .NET. Hướng dẫn này cung cấp hướng dẫn chi tiết về các bước liên quan đến quy trình.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể sử dụng Aspose.Page cho .NET với các định dạng tài liệu khác không?

Câu trả lời 1: Aspose.Page dành cho .NET chủ yếu tập trung vào các tài liệu XPS, nhưng Aspose cung cấp các thư viện khác cho các định dạng tài liệu khác nhau.

### Câu hỏi 2: Aspose.Page cho .NET có phù hợp cho người mới bắt đầu không?

Câu trả lời 2: Có, Aspose.Page dành cho .NET được thiết kế thân thiện với người dùng và người mới bắt đầu có thể nhanh chóng nắm bắt các chức năng của nó bằng tài liệu thích hợp.

### Câu hỏi 3: Tôi có thể tìm thêm ví dụ và tài nguyên ở đâu?

 A3: Tham quan[tài liệu](https://reference.aspose.com/page/net/) Và[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để có được nhiều tài nguyên và ví dụ.

### Câu hỏi 4: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Page cho .NET?

 A4: Bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).

### Câu hỏi 5: Có bản dùng thử miễn phí dành cho Aspose.Page dành cho .NET không?

 Câu trả lời 5: Có, bạn có thể khám phá bản dùng thử miễn phí[đây](https://releases.aspose.com/).