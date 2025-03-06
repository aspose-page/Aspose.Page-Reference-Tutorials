---
title: Thêm gradient chéo vào PostScript (PS) bằng Aspose.Page .NET
linktitle: Thêm chuyển màu chéo vào PostScript (PS)
second_title: API Aspose.Page .NET
description: Khám phá sự đơn giản của việc thêm độ dốc đường chéo vào tài liệu PostScript trong .NET với Aspose.Page. Nâng tầm dự án của bạn bằng các yếu tố trực quan năng động.
weight: 10
url: /vi/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm gradient chéo vào PostScript (PS) bằng Aspose.Page .NET

## Giới thiệu

Việc thêm dải màu chéo vào tài liệu PostScript (PS) có thể mang lại sự hấp dẫn trực quan và tính sáng tạo cho dự án của bạn. Aspose.Page for .NET cung cấp giải pháp liền mạch để tích hợp tính năng này vào ứng dụng của bạn. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thêm dải màu chéo vào tài liệu PS bằng Aspose.Page, từng bước một.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

-  Aspose.Page for .NET Library: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.Page for .NET. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/page/net/).

- Thư mục Tài liệu: Thiết lập một thư mục cho tài liệu của bạn nơi tệp PS đầu ra sẽ được lưu.

Bây giờ, hãy chuyển sang hướng dẫn từng bước.

## Nhập không gian tên

Trước tiên, hãy đảm bảo nhập các không gian tên cần thiết vào dự án của bạn. Các không gian tên này rất quan trọng để làm việc với các chức năng của Aspose.Page.

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
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Bước 2: Tạo tùy chọn lưu với khổ A4

```csharp
	//Tạo tùy chọn lưu với khổ A4
	PsSaveOptions options = new PsSaveOptions();
```

## Bước 3: Tạo tài liệu PS 1 trang mới

```csharp
	// Tạo tài liệu PS 1 trang mới
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Bước 4: Xác định tham số hình chữ nhật

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Bước 5: Tạo đường dẫn đồ họa

```csharp
	//Tạo đường dẫn đồ họa từ hình chữ nhật đầu tiên
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Bước 6: Tạo cọ chuyển màu tuyến tính

```csharp
	//Tạo cọ vẽ gradient tuyến tính với hình chữ nhật làm màu giới hạn, màu bắt đầu và màu kết thúc
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Bước 7: Tạo Transform cho Brush

```csharp
	//Tạo một biến đổi cho cọ vẽ. Thành phần tỷ lệ X và Y phải bằng chiều rộng và chiều cao tương ứng của hình chữ nhật.
	// Các thành phần dịch là phần bù của hình chữ nhật
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Bước 8: Áp dụng các chuyển đổi cho Brush

```csharp
	//Xoay gradient, sau đó chia tỷ lệ và dịch để có được chuyển đổi màu hiển thị trong hình chữ nhật được yêu cầu
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Bước 9: Đặt Transform thành Brush

```csharp
	//Đặt biến đổi
	brush.Transform = brushTransform;
```

## Bước 10: Đặt màu và tô màu cho hình chữ nhật

```csharp
	//Đặt sơn
	document.SetPaint(brush);

	//Điền vào hình chữ nhật
	document.Fill(path);
```

## Bước 11: Đóng trang hiện tại

```csharp
	//Đóng trang hiện tại
	document.ClosePage();
```

## Bước 12: Lưu tài liệu

```csharp
	//Lưu tài liệu
	document.Save();
}
// ExEnd:1
```

Bằng cách làm theo các bước này, bạn sẽ thêm thành công dải màu chéo vào tài liệu PostScript bằng Aspose.Page cho .NET.

## Phần kết luận

Cải thiện tài liệu PS của bạn bằng các đường chéo có thể làm cho dự án của bạn trở nên hấp dẫn và năng động về mặt trực quan. Aspose.Page for .NET đơn giản hóa quy trình này, cho phép các nhà phát triển dễ dàng tích hợp tính năng này vào ứng dụng của họ.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Page có tương thích với tất cả các khung .NET không?

Câu trả lời 1: Aspose.Page hỗ trợ nhiều khung .NET khác nhau, đảm bảo khả năng tương thích với nhiều môi trường phát triển.

### Câu hỏi 2: Tôi có thể tùy chỉnh màu chuyển màu trong Aspose.Page không?

Câu trả lời 2: Có, Aspose.Page cung cấp sự linh hoạt trong việc lựa chọn và tùy chỉnh màu chuyển sắc theo yêu cầu dự án của bạn.

### Câu 3: Có phiên bản dùng thử cho Aspose.Page không?

 Câu trả lời 3: Có, bạn có thể khám phá các tính năng của Aspose.Page bằng cách tải xuống phiên bản dùng thử[đây](https://releases.aspose.com/).

### Câu hỏi 4: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Page?

 A4: Lấy giấy phép tạm thời cho Aspose.Page[đây](https://purchase.aspose.com/temporary-license/) để mở khóa các tính năng bổ sung.

### Câu hỏi 5: Tôi có thể tìm sự hỗ trợ của cộng đồng cho Aspose.Page ở đâu?

 Câu trả lời 5: Tương tác với cộng đồng Aspose.Page trên[diễn đàn](https://forum.aspose.com/c/page/39) để được hỗ trợ và thảo luận.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
