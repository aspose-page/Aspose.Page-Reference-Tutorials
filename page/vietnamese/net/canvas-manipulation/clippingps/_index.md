---
date: 2026-01-05
description: Tìm hiểu cách thêm đường cắt trong PostScript bằng Aspose.Page cho .NET
  – hướng dẫn từng bước với kỹ thuật đặt cọ vẽ và vẽ hình chữ nhật gạch chéo.
linktitle: Clipping PS
second_title: Aspose.Page .NET API
title: Thêm Đường Cắt vào PS bằng Aspose.Page cho .NET
url: /vi/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm clipping path vào PS với Aspose.Page cho .NET

## Giới thiệu

Trong hướng dẫn toàn diện này, bạn sẽ khám phá cách **thêm clipping path** vào tài liệu PostScript (PS) bằng Aspose.Page cho .NET. Chúng tôi sẽ hướng dẫn từng bước, chỉ cho bạn cách **đặt brush vẽ**, và minh họa cách **vẽ hình chữ nhật gạch đứt** quanh nội dung đã được cắt. Khi kết thúc, bạn sẽ có một tệp PS hoạt động đầy đủ, thể hiện việc cắt theo hình dạng, giúp đồ họa của bạn trở nên sinh động và chuyên nghiệp hơn.

## Câu trả lời nhanh
- **Thêm “clipping path” làm gì?** Nó giới hạn các thao tác vẽ trong một hình dạng đã định, ẩn mọi thứ nằm ngoài hình đó.  
- **Thư viện nào xử lý clipping trong .NET?** Aspose.Page cho .NET cung cấp API phong phú để thao tác PS/EPS.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể thay đổi màu brush không?** Có, sử dụng `SetPaint` với bất kỳ `SolidBrush` hoặc gradient nào bạn muốn.  
- **Có thể vẽ hình chữ nhật gạch đứt không?** Chắc chắn – tạo một `Pen` với `DashStyle.Dash` và dùng `Draw`.  

## Clipping path là gì trong PostScript?
Một clipping path xác định vùng hiển thị cho các lệnh vẽ tiếp theo. Bất kỳ thứ gì được vẽ ngoài đường cắt sẽ bị bỏ qua, cho phép bạn tạo đồ họa mask phức tạp mà không thay đổi nội dung gốc.

## Tại sao nên dùng Aspose.Page để clipping?
- **Không phụ thuộc bên ngoài** – thư viện .NET thuần.  
- **Kiểm soát đầy đủ** trạng thái đồ họa (save/restore, translate, rotate).  
- **Các primitive vẽ phong phú** như `SetPaint`, `Clip`, và `Draw` với bút và brush có thể tùy chỉnh.  

## Yêu cầu trước

- Kiến thức cơ bản về lập trình C#.  
- Thư viện Aspose.Page cho .NET đã được cài đặt – bạn có thể tải xuống [tại đây](https://releases.aspose.com/page/net/).  
- Visual Studio hoặc bất kỳ IDE .NET nào bạn ưa thích.  

## Nhập các Namespace

Đầu tiên, nhập các namespace cần thiết cho việc thao tác đồ họa:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Bây giờ chúng ta sẽ phân tích ví dụ thành các bước rõ ràng, được đánh số.

### Bước 1: Đặt thư mục tài liệu

Xác định thư mục nơi các tệp nguồn và đầu ra sẽ được lưu.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Bước 2: Tạo Output Stream cho tài liệu PostScript

Tạo một stream có thể ghi để chứa tệp PS được tạo.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Bước 3: Tạo Save Options

Khởi tạo `PsSaveOptions` với các thiết lập mặc định. Bạn có thể tùy chỉnh sau nếu cần.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Bước 4: Tạo một tài liệu PS 1‑Trang mới

Khởi tạo đối tượng `PsDocument` đại diện cho tệp PS của bạn.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Bước 5: Tạo Graphics Path từ hình chữ nhật

Chúng ta sẽ sử dụng một hình chữ nhật làm hình dạng cơ bản, sau này sẽ được cắt.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Bước 6: Clipping theo hình dạng

Ở đây chúng tôi **thêm clipping path** bằng một vòng tròn, **đặt brush vẽ** màu xanh, và tô đầy hình chữ nhật trong vùng đã được cắt.

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### Bước 7: Di chuyển Graphics State cấp cao & Vẽ hình chữ nhật gạch đứt

Sau khi khôi phục trạng thái trước đó, chúng tôi di chuyển con trỏ đồ họa một lần nữa, **vẽ một hình chữ nhật gạch đứt**, và áp dụng nét màu xanh.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### Bước 8: Đóng và Lưu tài liệu

Kết thúc trang và ghi tệp PS ra đĩa.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Bạn đã thành công **thêm clipping path**, đặt brush vẽ tùy chỉnh, và vẽ một hình chữ nhật gạch đứt quanh đồ họa của mình bằng Aspose.Page cho .NET.

## Các vấn đề thường gặp và giải pháp

- **Clipping không hiển thị:** Đảm bảo bạn gọi `WriteGraphicsSave()` trước khi dịch chuyển và `WriteGraphicsRestore()` sau khi tô.  
- **Màu không đúng:** Kiểm tra rằng `SetPaint` được gọi sau `Clip` và trước `Fill`.  
- **Đường gạch đứt hiện thành nét liền:** Đảm bảo `DashStyle` của `Pen` được đặt thành `DashStyle.Dash` trước `SetStroke`.  

## Câu hỏi thường gặp

### Q1: Tôi có thể dùng Aspose.Page cho .NET với các ngôn ngữ lập trình khác không?
A: Aspose.Page chủ yếu được thiết kế cho các ứng dụng .NET. Tuy nhiên, Aspose cung cấp các thư viện tương tự cho các ngôn ngữ lập trình khác.

### Q2: Tôi có thể tìm các ví dụ và tài liệu bổ sung cho Aspose.Page cho .NET ở đâu?
A: Bạn có thể khám phá thêm các ví dụ và tài liệu chi tiết trên [tài liệu Aspose.Page](https://reference.aspose.com/page/net/).

### Q3: Có bản dùng thử miễn phí cho Aspose.Page cho .NET không?
A: Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.Page cho .NET [tại đây](https://releases.aspose.com/).

### Q4: Làm sao để tôi có được giấy phép tạm thời cho Aspose.Page cho .NET?
A: Bạn có thể nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

### Q5: Tôi có thể nhận hỗ trợ hoặc thảo luận các câu hỏi liên quan đến Aspose.Page ở đâu?
A: Ghé thăm [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để được cộng đồng hỗ trợ và thảo luận.

---

**Cập nhật lần cuối:** 2026-01-05  
**Kiểm tra với:** Aspose.Page 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}