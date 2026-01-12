---
date: 2026-01-12
description: Tìm hiểu cách lưu tệp PostScript và tạo tài liệu PostScript bằng Aspose.Page
  cho .NET, đồng thời áp dụng nhiều phép biến đổi cho đồ họa động.
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: Lưu tệp PostScript bằng Aspose.Page Transformations (.NET)
url: /vi/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lưu tệp PostScript với các biến đổi Aspose.Page (.NET)

## Giới thiệu

Trong hướng dẫn này, bạn sẽ khám phá cách **lưu tệp PostScript** khi làm việc với Aspose.Page cho .NET. Chúng ta sẽ đi qua việc tạo một tài liệu PostScript, áp dụng nhiều biến đổi như dịch chuyển, thu phóng, xoay và xiên, và cuối cùng lưu kết quả. Khi hoàn thành, bạn sẽ tự tin tạo đồ họa động bằng lập trình và biết chính xác nơi đặt mỗi biến đổi trong trạng thái đồ họa.

## Câu trả lời nhanh
- **Bạn có thể tạo gì?** Một tài liệu PostScript đầy đủ tính năng với đồ họa đã được biến đổi.  
- **Thư viện nào cần thiết?** Aspose.Page cho .NET (có thể tải xuống từ trang chính thức).  
- **Làm thế nào để lưu tệp?** Sử dụng `PsDocument.Save()` sau khi cấu hình trạng thái đồ họa.  
- **Có thể áp dụng nhiều biến đổi không?** Có – kết hợp chúng bằng `Transform` hoặc các lời gọi tuần tự.  
- **Cần giấy phép không?** Bản dùng thử miễn phí đủ cho phát triển; giấy phép thương mại cần cho môi trường sản xuất.

## Hoạt động “lưu tệp postscript” là gì?

Lưu tệp PostScript có nghĩa là ghi lại các lệnh vẽ mà bạn đã xây dựng trong bộ nhớ vào một tệp `.ps` trên đĩa. Tệp này sau đó có thể được bất kỳ trình thông dịch PostScript, máy in hoặc trình xem nào hỗ trợ.

## Tại sao sử dụng Aspose.Page cho .NET để tạo tài liệu postscript?

Aspose.Page cung cấp một API cấp cao, độc lập với thiết bị, trừu tượng hoá cú pháp PostScript cấp thấp. Bạn nhận được:

- Các đối tượng C# kiểu mạnh cho đường dẫn, bút vẽ và biến đổi.  
- Xử lý tự động ngăn xếp trạng thái đồ họa (save/restore).  
- Hỗ trợ đầy đủ ma trận biến đổi phức tạp mà không cần tính toán thủ công.  

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- Thư viện **Aspose.Page cho .NET** đã được tích hợp vào dự án của bạn. Tải nó từ [download link](https://releases.aspose.com/page/net/).  
- Một thư mục có quyền ghi mà tệp `.ps` được tạo sẽ được lưu vào. Thay thế đường dẫn placeholder trong mã bằng thư mục thực tế của bạn.

## Nhập không gian tên

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Bây giờ chúng ta sẽ khám phá từng bước biến đổi một cách chi tiết.

## Không có biến đổi

### Bước 1: Tạo luồng đầu ra

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Đoạn mã này tạo một **tài liệu PostScript** với một hình chữ nhật màu cam duy nhất và **lưu tệp PostScript** mà không áp dụng bất kỳ biến đổi nào.

## Dịch chuyển

### Bước 1: Lưu trạng thái đồ họa

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Lưu trạng thái đồ họa cho phép bạn quay lại sau khi di chuyển các đối tượng.

### Bước 2: Dịch chuyển trạng thái đồ họa

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

Biến đổi dịch chuyển sẽ di chuyển mọi thứ được vẽ sau lời gọi này 250 đơn vị sang phải.

### Bước 3: Đổ hình chữ nhật với biến đổi dịch chuyển

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Bây giờ một hình chữ nhật màu xanh sẽ xuất hiện cách hình chữ nhật màu cam 250 điểm.

### Bước 4: Khôi phục trạng thái đồ họa

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

Khôi phục sẽ đưa hệ tọa độ trở lại vị trí ban đầu, vì vậy các thao tác vẽ tiếp theo sẽ không bị ảnh hưởng bởi biến đổi dịch chuyển.

## Thu phóng (Scaling)

> *Bạn có thể theo cùng một mẫu—lưu trạng thái, áp dụng `Scale`, vẽ, rồi khôi phục.*  
> **Mẹo:** Sử dụng thu phóng không đồng nhất (`Scale(sx, sy)`) để kéo dài đối tượng chỉ theo một hướng.

## Xoay (Rotation)

> *Xoay quanh gốc tọa độ hoặc một điểm pivot tùy chỉnh bằng `Rotate(angle)`.*
> **Mẹo:** Kết hợp `Translate` trước khi xoay để xoay quanh một điểm cụ thể.

## Xiên (Shearing)

> *Biến đổi xiên (`Shear(shx, shy)`) làm nghiêng các hình dạng, hữu ích cho hiệu ứng in nghiêng.*  

## Biến đổi phức hợp

> *Đối với các kịch bản nâng cao, xây dựng một `Matrix` tùy chỉnh và truyền nó vào `Transform(matrix)`.*
> Đây là nơi bạn **áp dụng nhiều biến đổi** trong một bước duy nhất.

## Kết luận

Bạn đã học cách **lưu tệp PostScript**, **tạo tài liệu PostScript**, và **áp dụng nhiều biến đổi** bằng Aspose.Page cho .NET. Hãy thử nghiệm với các thứ tự biến đổi khác nhau, kết hợp chúng, và quan sát cách đồ họa phát triển.

## Câu hỏi thường gặp

**Q: Làm thế nào để áp dụng nhiều biến đổi cho một đối tượng duy nhất?**  
**A:** Sử dụng phương thức `Transform` với một `Matrix` tùy chỉnh kết hợp dịch chuyển, thu phóng, xoay hoặc xiên theo thứ tự bạn cần.

**Q: Tôi có thể xem trước các biến đổi trước khi lưu tài liệu không?**  
**A:** Có—render `PsDocument` ra hình ảnh hoặc dùng trình xem PostScript để kiểm tra đầu ra trước khi gọi `Save()`.

**Q: Có thể áp dụng biến đổi cho các phần tử cụ thể trong tài liệu không?**  
**A:** Chắc chắn. Lưu trạng thái đồ họa trước khi vẽ phần tử, áp dụng biến đổi mong muốn, vẽ, rồi khôi phục trạng thái.

**Q: Có lưu ý về hiệu năng khi làm việc với các biến đổi phức tạp không?**  
**A:** Ma trận phức tạp làm tăng tải CPU. Giữ các biến đổi càng đơn giản càng tốt và tái sử dụng trạng thái đã lưu khi vẽ nhiều đối tượng tương tự.

**Q: Làm sao tôi có thể nhận hỗ trợ hoặc trợ giúp cho các câu hỏi liên quan đến Aspose.Page?**  
**A:** Truy cập [Aspose.Page forum](https://forum.aspose.com/c/page/39) để nhận trợ giúp từ cộng đồng, hoặc liên hệ trực tiếp với bộ phận hỗ trợ của Aspose.

---

**Last Updated:** 2026-01-12  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}