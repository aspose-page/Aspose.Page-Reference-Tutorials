---
date: 2026-02-23
description: Tìm hiểu cách thêm gradient vào các tệp PostScript, lưu tệp PostScript
  với kích thước trang A4 và tô màu gradient cho hình chữ nhật bằng Aspose.Page cho
  .NET.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Cách Thêm Gradient – Gradient Đường Chéo trong PostScript (PS) bằng Aspose.Page
  .NET
url: /vi/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Gradient: Gradient Đường Chéo vào PostScript (PS) với Aspose.Page .NET

## Giới thiệu

Thêm một gradient đường chéo vào tài liệu PostScript (PS) có thể cải thiện đáng kể tính thẩm mỹ, đặc biệt khi bạn cần các hiệu ứng **how to add gradient** trong các báo cáo kỹ thuật, brochure, hoặc các ứng dụng đồ họa nặng. Trong hướng dẫn này, bạn sẽ thấy cách thêm gradient vào tệp PostScript, đặt kích thước trang A4, và tô một hình chữ nhật với chuyển đổi màu mượt mà bằng Aspose.Page cho .NET.

## Câu trả lời nhanh
- **Thư viện nào được yêu cầu?** Aspose.Page for .NET  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **Tôi có thể thay đổi hướng gradient không?** Yes – rotate the brush transform as shown in the code  
- **Làm thế nào để lưu kết quả?** Use `PsDocument.Save()` which writes a PostScript file to disk  
- **Có cần giấy phép cho môi trường sản xuất không?** Yes, a commercial license unlocks full functionality  

## Gradient đường chéo là gì trong PostScript?

Gradient đường chéo là một chuyển đổi màu tuyến tính chạy theo một góc (thường là 45°) trên một hình dạng. Trong PostScript, điều này được thực hiện bằng cách áp dụng một `LinearGradientBrush` với ma trận biến đổi tùy chỉnh để xoay, co giãn và dịch chuyển gradient sao cho phù hợp với hình chữ nhật mong muốn.

## Tại sao nên sử dụng Aspose.Page cho việc tô gradient?

Aspose.Page trừu tượng hoá các lệnh PostScript cấp thấp, cho phép bạn làm việc với các đối tượng đồ họa .NET quen thuộc. Bạn có thể tạo các lớp tô phức tạp, đặt kích thước trang, và xuất trực tiếp tới một **save PostScript file** mà không phải xử lý cú pháp PS thô.

## Yêu cầu trước

- **Aspose.Page for .NET Library** – tải xuống tại [here](https://releases.aspose.com/page/net/).  
- **Document Directory** – thư mục nơi tệp `*.ps` được tạo sẽ được ghi.

Bây giờ chúng ta đã nắm được các kiến thức cơ bản, hãy cùng đi qua việc triển khai từng bước.

## Nhập các không gian tên

Đầu tiên, nhập các không gian tên cho phép bạn truy cập vào thiết bị EPS, các tiện ích vẽ, và các lớp I/O.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Bước 1: Tạo luồng đầu ra cho tài liệu PostScript (Tạo tài liệu PostScript)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Bước 2: Đặt kích thước trang A4 (Tùy chọn lưu)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## Bước 3: Tạo một tài liệu PS mới với 1 trang

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Bước 4: Định nghĩa các tham số hình chữ nhật

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Bước 5: Tạo đường đồ họa

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Bước 6: Tạo Linear Gradient Brush (Tô gradient cho hình chữ nhật)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Bước 7: Tạo biến đổi cho Brush

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Bước 8: Áp dụng các biến đổi lên Brush (Xoay, Co giãn, Dịch chuyển)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Bước 9: Đặt biến đổi cho Brush

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## Bước 10: Đặt Paint và tô hình chữ nhật

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## Bước 11: Đóng trang hiện tại

```csharp
	//Close current page
	document.ClosePage();
```

## Bước 12: Lưu tài liệu (Lưu tệp PostScript)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## Cách lưu tệp PostScript

Lệnh `PsDocument.Save()` sẽ ghi nội dung PostScript đã hoàn chỉnh vào luồng bạn đã mở ở **Step 1**. Sau khi khối `using` kết thúc, tệp `DiagonaGradient_outPS.ps` sẽ có sẵn trong thư mục bạn đã chỉ định.

## Các trường hợp sử dụng phổ biến

- **Technical documentation** cần một nền shading nhẹ nhàng.  
- **Marketing brochures** nơi gradient đường chéo tạo vẻ hiện đại.  
- **Automated report generators** tạo ra các tệp PS có thể in ngay lập tức.  

## Khắc phục sự cố & Mẹo

- **Incorrect colors** – kiểm tra lại các giá trị ARGB truyền vào `LinearGradientBrush`.  
- **Gradient not visible** – đảm bảo ma trận biến đổi xoay và co giãn đúng; lệnh `Rotate(-45)` đặt góc đường chéo.  
- **File not created** – xác minh rằng `dataDir` trỏ tới một thư mục tồn tại và ứng dụng có quyền ghi.  

## Câu hỏi thường gặp

**Q: Aspose.Page có tương thích với tất cả các framework .NET không?**  
A: Aspose.Page hỗ trợ một loạt các phiên bản .NET, từ .NET Framework 4.5+ đến .NET 6+, đảm bảo tính tương thích rộng rãi.

**Q: Tôi có thể tùy chỉnh màu gradient trong Aspose.Page không?**  
A: Có, bạn có thể chỉ định bất kỳ màu ARGB nào khi tạo `LinearGradientBrush`, cho phép bạn kiểm soát hoàn toàn màu bắt đầu và kết thúc.

**Q: Có phiên bản dùng thử cho Aspose.Page không?**  
A: Có, bạn có thể khám phá các tính năng của Aspose.Page bằng cách tải phiên bản dùng thử [here](https://releases.aspose.com/).

**Q: Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.Page?**  
A: Nhận giấy phép tạm thời cho Aspose.Page [here](https://purchase.aspose.com/temporary-license/) để mở khóa các khả năng bổ sung trong quá trình đánh giá.

**Q: Tôi có thể tìm hỗ trợ cộng đồng cho Aspose.Page ở đâu?**  
A: Tham gia cộng đồng Aspose.Page trên [forum](https://forum.aspose.com/c/page/39) để được hỗ trợ và thảo luận.

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Page for .NET (latest stable release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}