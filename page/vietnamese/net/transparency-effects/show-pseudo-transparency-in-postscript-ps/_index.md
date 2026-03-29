---
date: 2026-03-29
description: Học cách sử dụng cọ gradient tuyến tính trong C# để tạo độ trong suốt
  giả trong PostScript với Aspose.Page cho .NET.
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: Cọ Gradient Tuyến Tính C# cho Độ Trong Suốt Giả trong PS
url: /vi/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bút chổi gradient tuyến tính C# cho Pseudo-Transparency trong PostScript (PS)

## Giới thiệu

Nếu bạn cần thêm hiệu ứng trong suốt nhẹ nhàng vào các tệp PostScript (PS) của mình, **linear gradient brush C#** là công cụ hoàn hảo. Aspose.Page for .NET giúp bạn dễ dàng vẽ các hình chữ nhật với cả màu nền gradient không trong suốt và trong suốt, mang lại cho tài liệu của bạn vẻ hiện đại, lớp lớp. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn chi tiết các bước cần thiết để tạo pseudo‑transparency bằng linear gradient brush trong C#.

## Câu trả lời nhanh
- **Thư viện nào cung cấp linear gradient brush?** Aspose.Page for .NET
- **Lớp đồ họa nào tạo gradient?** `LinearGradientBrush`
- **Tôi có thể kiểm soát độ trong suốt cho mỗi màu không?** Yes, using `Color.FromArgb(alpha, …)`
- **Tôi có cần giấy phép cho môi trường sản xuất không?** A valid Aspose.Page license is required
- **Các phiên bản .NET được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Linear gradient brush C# là gì?

`LinearGradientBrush` là một đối tượng GDI+ vẽ chuyển đổi mượt mà giữa hai màu dọc theo một đường thẳng. Khi bạn chỉ định kênh alpha (0‑255) cho mỗi màu, bạn có thể tạo gradient trong suốt — chính xác những gì chúng ta cần cho pseudo‑transparency trong PostScript.

## Tại sao nên sử dụng linear gradient brush C# cho pseudo‑transparency?

- **Fine‑grained opacity control:** Điều chỉnh alpha của mỗi màu để đạt mức trong suốt mong muốn.  
- **Device‑independent rendering:** Bút chổi hoạt động giống nhau trên màn hình, PDF, EPS và PS.  
- **Simple API:** Vài dòng mã C# tạo ra hiệu ứng hình ảnh chuyên nghiệp.

## Yêu cầu trước

- Aspose.Page for .NET đã được cài đặt. Bạn có thể tải xuống từ [tài liệu Aspose.Page](https://reference.aspose.com/page/net/).
- Một thư mục có quyền ghi nơi tài liệu PostScript được tạo sẽ được lưu.

Bây giờ bạn đã có các công cụ cần thiết, hãy bắt đầu tạo các hình chữ nhật pseudo‑transparent.

## Nhập không gian tên

Trước khi bắt đầu, nhập các không gian tên chứa các lớp chúng ta sẽ sử dụng:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Bước 1: Tạo luồng đầu ra cho tài liệu PostScript

Chúng ta bắt đầu bằng việc tạo một file stream để chứa tệp PS kết quả, sau đó khởi tạo `PsDocument`.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Bước 2: Tạo một hình chữ nhật với màu nền gradient **opaque**

Ở đây chúng ta tạo một `LinearGradientBrush` với các màu hoàn toàn opaque (alpha = 255). Hình chữ nhật này sẽ làm lớp nền.

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

## Bước 3: Tạo một hình chữ nhật với màu nền gradient **translucent**

Bây giờ chúng ta sử dụng **linear gradient brush C#** với các giá trị alpha nhỏ hơn 255 (ví dụ, 150 và 50). Điều này làm cho hình chữ nhật một phần trong suốt, đạt được hiệu ứng pseudo‑transparency.

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Bước 4: Đóng trang và lưu tài liệu

Cuối cùng chúng ta hoàn thành trang và ghi tệp PS ra đĩa.

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

Bằng cách thực hiện bốn bước này, bạn có thể kết hợp mượt mà các hình chữ nhật opaque và translucent, tạo ra hiệu ứng pseudo‑transparent thuyết phục trong bất kỳ đầu ra PostScript nào.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| Màu hiển thị hoàn toàn opaque | Giá trị alpha bị đặt thành 255 nhầm | Sử dụng `Color.FromArgb(alpha, …)` với `alpha` < 255 |
| Gradient bị kéo dãn không đúng | Ma trận biến đổi không chính xác | Kiểm tra các tham số ma trận khớp với kích thước hình chữ nhật |
| Tệp đầu ra rỗng | Stream không được đóng hoặc `Save()` chưa được gọi | Đảm bảo `document.ClosePage()` và `document.Save()` được thực thi trong khối `using` |

## Câu hỏi thường gặp

**Q: Aspose.Page có tương thích với mọi phiên bản .NET không?**  
A: Aspose.Page for .NET tương thích với nhiều phiên bản của .NET framework, đảm bảo tính linh hoạt và dễ dàng tích hợp.

**Q: Tôi có thể áp dụng pseudo‑transparency cho các hình dạng khác ngoài hình chữ nhật không?**  
A: Có, các nguyên tắc tương tự có thể áp dụng cho bất kỳ hình dạng nào bằng cách điều chỉnh `GraphicsPath` cho phù hợp.

**Q: Tôi có thể tìm các ví dụ và tài liệu bổ sung ở đâu?**  
A: Khám phá [tài liệu Aspose.Page](https://reference.aspose.com/page/net/) để xem các ví dụ toàn diện và tham chiếu API chi tiết.

**Q: Có bản dùng thử miễn phí cho Aspose.Page không?**  
A: Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.Page từ [liên kết này](https://releases.aspose.com/).

**Q: Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.Page?**  
A: Truy cập [liên kết này](https://purchase.aspose.com/temporary-license/) để nhận giấy phép tạm thời cho Aspose.Page.

---

**Cập nhật lần cuối:** 2026-03-29  
**Kiểm tra với:** Aspose.Page 24.11 for .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}