---
title: Thêm văn bản vào tài liệu PostScript (PS) bằng Aspose.Page
linktitle: Thêm văn bản vào tài liệu PostScript (PS)
second_title: API Aspose.Page .NET
description: Nâng cao kỹ năng phát triển .NET của bạn bằng cách học cách thêm văn bản vào tài liệu PostScript (PS) bằng Aspose.Page. Khám phá các ví dụ từng bước và giải phóng sức mạnh của thao tác tài liệu.
type: docs
weight: 10
url: /vi/net/text-manipulation/add-text-to-postscript-ps-document/
---
## Giới thiệu

Trong thế giới phát triển .NET năng động, việc thao tác và nâng cao các tài liệu PostScript (PS) là một yêu cầu chung. Aspose.Page for .NET cung cấp một bộ công cụ mạnh mẽ để dễ dàng thêm văn bản vào tài liệu PS của bạn. Hướng dẫn này sẽ hướng dẫn bạn thực hiện quy trình, đảm bảo bạn có thể tích hợp liền mạch chức năng này vào các dự án của mình.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

-  Aspose.Page for .NET: Đảm bảo rằng bạn đã tích hợp thư viện Aspose.Page vào dự án .NET của mình. Bạn có thể tải nó xuống từ[Tài liệu Aspose.Page .NET](https://reference.aspose.com/page/net/).

- Thư mục tài liệu: Thiết lập một thư mục nơi tài liệu của bạn sẽ được lưu trữ. Điều này sẽ được gọi là "Thư mục tài liệu của bạn" trong các ví dụ.

- Thư mục Phông chữ: Tạo một thư mục để lưu trữ các phông chữ tùy chỉnh, được gọi là "Thư mục Tài liệu của Bạn" trong các ví dụ.

## Nhập không gian tên

Trước khi bắt đầu, hãy đảm bảo bao gồm các không gian tên cần thiết trong dự án của bạn:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Bây giờ, hãy chia ví dụ thành nhiều bước.

## Bước 1: Tạo luồng đầu ra cho tài liệu PS

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Bước 2: Điền văn bản bằng phông chữ hệ thống

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

## Bước 3: Điền văn bản với phông chữ tùy chỉnh

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Bước 4: Phác thảo văn bản với phông chữ hệ thống

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

## Bước 5: Phác thảo văn bản với phông chữ tùy chỉnh

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

## Bước 6: Đóng và lưu

```csharp
document.ClosePage();
document.Save();
}
```

## Phần kết luận

Chúc mừng! Bạn đã học thành công cách thêm văn bản vào tài liệu PostScript (PS) bằng Aspose.Page cho .NET. Hãy thoải mái khám phá nhiều tính năng hơn và nâng cao khả năng thao tác tài liệu của bạn.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể sử dụng Aspose.Page với các thư viện .NET khác không?

Câu trả lời 1: Có, Aspose.Page tích hợp liền mạch với các thư viện .NET khác, cung cấp một môi trường linh hoạt để thao tác tài liệu.

### Câu hỏi 2: Phông chữ tùy chỉnh có cần thiết cho quá trình này không?

Câu trả lời 2: Mặc dù bạn có thể sử dụng phông chữ hệ thống, nhưng việc kết hợp các phông chữ tùy chỉnh sẽ mang lại sự linh hoạt và lựa chọn thiết kế cao hơn.

### Câu hỏi 3: Aspose.Page có phù hợp để xử lý tài liệu quy mô lớn không?

A3: Chắc chắn rồi! Aspose.Page được thiết kế để xử lý việc xử lý tài liệu quy mô lớn với hiệu quả và độ tin cậy.

### Q4: Tôi có thể sửa đổi vị trí của văn bản trong tài liệu PS không?

A4: Chắc chắn rồi! Điều chỉnh tọa độ trong các ví dụ được cung cấp để thay đổi vị trí của văn bản đã thêm.

### Câu hỏi 5: Tôi có thể tìm kiếm hỗ trợ ở đâu cho các truy vấn liên quan đến Aspose.Page?

 A5: Tham quan[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để kết nối với cộng đồng và tìm kiếm lời khuyên của chuyên gia.