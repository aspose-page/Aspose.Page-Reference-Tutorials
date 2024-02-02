---
title: Hiển thị tính minh bạch giả trong PostScript (PS) với Aspose.Page
linktitle: Hiển thị tính minh bạch giả trong PostScript (PS)
second_title: API Aspose.Page .NET
description: Khám phá sức mạnh của tính minh bạch giả trong PostScript với Aspose.Page cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để có được những tài liệu có hình ảnh bắt mắt.
type: docs
weight: 13
url: /vi/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
---
## Giới thiệu

Bạn đang tìm cách nâng cao sự hấp dẫn trực quan của tài liệu PostScript (PS) của mình bằng cách kết hợp tính minh bạch giả? Aspose.Page for .NET cung cấp một giải pháp mạnh mẽ để đạt được hiệu quả này một cách dễ dàng. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn quy trình hiển thị tính minh bạch giả trong PostScript bằng Aspose.Page.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Aspose.Page for .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Page cho .NET. Bạn có thể tải nó xuống từ[Tài liệu Aspose.Page](https://reference.aspose.com/page/net/).

- Thư mục Tài liệu: Thiết lập một thư mục để lưu trữ các tài liệu PostScript của bạn.

Bây giờ bạn đã có các công cụ cần thiết trong kho vũ khí của mình, hãy khám phá cách thể hiện tính minh bạch giả trong PostScript bằng Aspose.Page.

## Nhập không gian tên

Trước khi đi sâu vào ví dụ, hãy đảm bảo bạn nhập các không gian tên được yêu cầu:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Bước 1: Tạo luồng đầu ra cho tài liệu PostScript

```csharp
// Bắt đầu:1
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";
//Tạo luồng đầu ra cho tài liệu PostScript
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Tạo tùy chọn lưu với khổ A4
	PsSaveOptions options = new PsSaveOptions();

	// Tạo tài liệu PS 1 trang mới
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Bước 2: Tạo hình chữ nhật với màu tô gradient mờ

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Bước 3: Tạo hình chữ nhật với màu tô chuyển màu mờ

```csharp
	offsetX = 350;

	//Tạo đường dẫn đồ họa từ hình chữ nhật đầu tiên
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Tạo các màu cọ gradient tuyến tính có độ trong suốt không phải là 255 mà là 150 và 50. Vì vậy, nó mờ.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Bước 4: Đóng trang hiện tại và lưu tài liệu

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

Bằng cách làm theo các bước này, bạn có thể tích hợp liền mạch tính minh bạch giả vào tài liệu PostScript của mình bằng Aspose.Page cho .NET.

## Phần kết luận

Tóm lại, Aspose.Page dành cho .NET cung cấp một cách đơn giản và hiệu quả để nâng cao các yếu tố trực quan trong tài liệu PostScript của bạn. Các bước được nêu ở trên cung cấp một lộ trình rõ ràng để kết hợp tính minh bạch giả, cho phép bạn tạo ra các kết quả đầu ra có hình ảnh ấn tượng.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Page có tương thích với tất cả các phiên bản .NET không?

Câu trả lời 1: Aspose.Page for .NET tương thích với nhiều phiên bản khác nhau của .NET framework, đảm bảo tính linh hoạt và dễ tích hợp.

### Câu hỏi 2: Tôi có thể áp dụng tính năng giả trong suốt cho các hình dạng khác ngoài hình chữ nhật không?

Câu trả lời 2: Có, các nguyên tắc tương tự có thể được áp dụng cho các hình dạng khác bằng cách điều chỉnh GraphicsPath cho phù hợp.

### Câu hỏi 3: Tôi có thể tìm thêm ví dụ và tài liệu ở đâu?

 A3: Khám phá[Tài liệu Aspose.Page](https://reference.aspose.com/page/net/) để có ví dụ toàn diện và tài liệu chi tiết.

### Câu hỏi 4: Aspose.Page có bản dùng thử miễn phí không?

 Câu trả lời 4: Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.Page từ[liên kết này](https://releases.aspose.com/).

### Câu hỏi 5: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Page?

 A5: Thăm quan[liên kết này](https://purchase.aspose.com/temporary-license/) để có được giấy phép tạm thời cho Aspose.Page.