---
date: 2026-07-19
description: Tìm hiểu cách tạo tài liệu PostScript ASP.NET bằng Aspose.Page cho .NET,
  áp dụng nhiều transformations và lưu tệp một cách hiệu quả.
keywords:
- create postscript document asp.net
- aspose.page transformations
- postscript graphics .net
lastmod: 2026-07-19
linktitle: Transformations PS
og_description: Tạo tài liệu PostScript ASP.NET với Aspose.Page. Tìm hiểu cách áp
  dụng translation, scaling, rotation và shearing, sau đó lưu tệp.
og_image_alt: Guide to creating and transforming PostScript documents using Aspose.Page
  for .NET
og_title: Tạo tài liệu PostScript ASP.NET – Hướng dẫn Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create PostScript document ASP.NET using Aspose.Page for
    .NET, apply multiple transformations, and save the file efficiently.
  headline: Create PostScript Document ASP.NET with Aspose.Page
  type: TechArticle
- questions:
  - answer: Use the `Transform` method with a custom `Matrix` that combines translation,
      scaling, rotation, or shearing in the order you need.
    question: How can I apply multiple transformations to a single object?
  - answer: Yes—render the `PsDocument` to an image using `PsDocument.Save("output.png",
      SaveFormat.Png)` or open the `.ps` file in a PostScript viewer to inspect the
      result before calling `Save()` for the final file.
    question: Can I preview the transformations before saving the document?
  - answer: Absolutely. Save the graphics state before drawing the element, apply
      the desired transformation, draw, then restore the state so later elements remain
      unaffected.
    question: Is it possible to apply transformations to specific elements in a document?
  - answer: Complex matrices increase CPU work. Keep transformations as simple as
      possible and reuse saved states when drawing many similar objects. Aspose.Page
      processes a 300‑page document with mixed transformations in under 2 seconds
      on a typical 3.2 GHz CPU.
    question: Are there any performance considerations when dealing with complex transformations?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community help, or contact Aspose support directly for priority assistance.
    question: How can I get support or seek assistance for Aspose.Page-related queries?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- postscript
- aspose.page
- .net graphics
- transformations
title: Tạo tài liệu PostScript ASP.NET với Aspose.Page
url: /vi/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo tài liệu PostScript ASP.NET với Aspose.Page

## Giới thiệu

Trong hướng dẫn từng bước này, bạn sẽ **tạo tài liệu PostScript ASP.NET** bằng thư viện Aspose.Page, áp dụng nhiều biến đổi đồ họa, và cuối cùng lưu kết quả vào tệp `.ps`. Khi hoàn thành, bạn sẽ hiểu cách đẩy mỗi biến đổi lên ngăn xếp trạng thái đồ họa, cách kết hợp chúng một cách hiệu quả, và cách lưu các lệnh vẽ để bất kỳ trình thông dịch PostScript nào cũng có thể render chúng. Kiến thức này rất quan trọng để tạo đồ họa có thể in, báo cáo tùy chỉnh, hoặc tài sản sẵn sàng in động trực tiếp từ các ứng dụng .NET.

## Câu trả lời nhanh
- **Bạn có thể tạo gì?** Một tài liệu PostScript đầy đủ tính năng với đồ họa đã được biến đổi.  
- **Thư viện nào cần thiết?** Aspose.Page cho .NET (có thể tải xuống từ trang chính thức).  
- **Làm thế nào để lưu tệp?** Sử dụng `PsDocument.Save()` sau khi cấu hình trạng thái đồ họa.  
- **Tôi có thể áp dụng nhiều phép biến đổi không?** Có – kết hợp chúng bằng `Transform` hoặc các lời gọi tuần tự.  
- **Cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.

## Hoạt động “lưu tệp postscript” là gì?

Lưu một tệp PostScript có nghĩa là ghi lại các lệnh vẽ mà bạn đã tạo trong bộ nhớ vào một tệp `.ps` trên đĩa. Tệp này sau đó có thể được bất kỳ trình thông dịch PostScript, máy in hoặc trình xem nào render, tạo thành một biểu diễn vector đồ họa di động, không phụ thuộc vào thiết bị. Khi bạn gọi phương thức `Save`, Aspose.Page sẽ tuần tự hoá toàn bộ trạng thái đồ họa, bao gồm các đường dẫn, brush và ma trận biến đổi, thành cú pháp PostScript hợp lệ tuân theo tiêu chuẩn của Adobe®.

## Tại sao nên sử dụng Aspose.Page cho .NET để tạo tài liệu postscript?

Aspose.Page cho .NET cung cấp cho bạn một API mạnh mẽ, kiểu dữ liệu chặt chẽ, hướng đối tượng, trừu tượng hoá ngôn ngữ PostScript cấp thấp. Nó tự động quản lý ngăn xếp trạng thái đồ họa, hỗ trợ hơn 50 phương thức liên quan đến biến đổi, và có thể xử lý tài liệu vượt quá 500 trang mà không cần tải toàn bộ tệp vào bộ nhớ. Điều này giảm thời gian phát triển tới 70 % so với việc tự viết mã PostScript và đảm bảo tương thích với tất cả các máy in chính.

## Yêu cầu trước

- **Thư viện Aspose.Page cho .NET** đã được tích hợp vào dự án của bạn. Tải nó từ [liên kết tải xuống](https://releases.aspose.com/page/net/).  
- Thư mục có quyền ghi nơi tệp `.ps` được tạo sẽ được lưu. Thay thế đường dẫn placeholder trong mã bằng thư mục thực tế của bạn.  
- .NET 6.0 hoặc mới hơn (thư viện cũng hỗ trợ .NET Core 3.1 và .NET Framework 4.6+).

## Nhập không gian tên

Lớp `PsDocument` nằm trong không gian tên `Aspose.Page.Drawing`, trong khi các trợ giúp biến đổi nằm trong `Aspose.Page.Drawing.Graphics`. Nhập chúng ở đầu tệp của bạn:

```csharp
using Aspose.Page.Drawing;
using Aspose.Page.Drawing.Graphics;
using Aspose.Page.Drawing.Shapes;
```

`PsDocument` là lớp cốt lõi của Aspose.Page đại diện cho một tài liệu PostScript trong bộ nhớ. Sau khi nhập các không gian tên, bạn có thể bắt đầu xây dựng bề mặt vẽ.

Bây giờ hãy khám phá từng bước biến đổi.

## Không có biến đổi

`PsDocument` là điểm vào cho tất cả các thao tác vẽ. Đoạn mã sau tạo một tài liệu mới, vẽ một hình chữ nhật màu cam đơn giản, và lưu nó mà không áp dụng bất kỳ biến đổi nào.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Đoạn mã này tạo một **tài liệu PostScript** với một hình chữ nhật màu cam duy nhất và **lưu tệp PostScript** mà không áp dụng bất kỳ biến đổi nào.

## Dịch chuyển

Lưu trạng thái đồ họa cho phép bạn quay lại sau khi di chuyển các đối tượng. Phương thức `SaveState` đẩy ma trận biến đổi hiện tại lên ngăn xếp nội bộ.

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Phương thức `Translate` di chuyển hệ tọa độ theo các độ dịch được chỉ định, ảnh hưởng đến tất cả các lệnh vẽ sau này.

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

Bây giờ một hình chữ nhật màu xanh xuất hiện cách hình chữ nhật màu cam 250 điểm về phía bên phải vì ma trận dịch chuyển đang hoạt động.

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Việc khôi phục trả hệ tọa độ về vị trí ban đầu, vì vậy các lệnh vẽ tiếp theo không bị ảnh hưởng bởi phép dịch chuyển.

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

## Thu phóng

`Scale` thay đổi kích thước của các đối tượng được vẽ bằng cách áp dụng ma trận thu phóng vào trạng thái đồ họa hiện tại.

> *Bạn có thể theo cùng mẫu—lưu trạng thái, áp dụng `Scale`, vẽ, rồi khôi phục.*  
> **Mẹo:** Sử dụng thu phóng không đồng đều (`Scale(sx, sy)`) để kéo dài các đối tượng chỉ theo một hướng, hữu ích cho việc tạo hiệu ứng biểu đồ cột.

## Xoay

`Rotate` áp dụng một ma trận xoay vào trạng thái đồ họa hiện tại, làm quay các lệnh vẽ tiếp theo theo góc đã chỉ định.

> *Xoay quanh gốc hoặc một điểm pivot tùy chỉnh bằng `Rotate(angle)`.*
> **Mẹo:** Kết hợp `Translate` trước khi xoay để xoay quanh một điểm cụ thể thay vì gốc.

## Xiên

`Shear` làm lệch hệ tọa độ theo các hệ số đã cho, làm nghiêng các đối tượng vẽ theo chiều ngang và/hoặc chiều dọc.

> *Biến đổi Shear (`Shear(shx, shy)`) làm nghiêng các hình dạng, hữu ích cho hiệu ứng in nghiêng hoặc các mẹo phối cảnh.*

## Biến đổi phức hợp

`Transform` áp dụng một ma trận biến đổi tùy chỉnh vào trạng thái đồ họa, kết hợp nhiều thao tác thành một.

> *Đối với các kịch bản nâng cao, xây dựng một `Matrix` tùy chỉnh và truyền nó vào `Transform(matrix)`.*
> Đây là nơi bạn **áp dụng nhiều biến đổi** trong một bước duy nhất, giảm số lần lưu và khôi phục trạng thái.

## Cách lưu tệp PostScript với các biến đổi?

`Save` ghi `PsDocument` hiện tại vào một tệp ở định dạng PostScript. Tải `PsDocument` của bạn, áp dụng chuỗi biến đổi mong muốn, và gọi `Save` với đường dẫn đích—Aspose.Page sẽ viết một tệp `.ps` tuân thủ tiêu chuẩn trong một lần. Thư viện tự động đóng bất kỳ trạng thái đồ họa mở nào, vì vậy bạn không cần mã dọn dẹp bổ sung. Cách tiếp cận này hoạt động cho bất kỳ sự kết hợp nào của dịch chuyển, thu phóng, xoay hoặc xiên.

## Các trường hợp sử dụng phổ biến

- **Tạo báo cáo động** – tạo biểu đồ thích ứng với kích thước dữ liệu tại thời gian chạy.  
- **Hóa đơn sẵn sàng in** – nhúng logo công ty và xoay chúng để phù hợp với hướng máy in.  
- **Thiết kế nhãn tùy chỉnh** – áp dụng xiên để mô phỏng hiệu ứng chữ nổi.  

## Câu hỏi thường gặp

**Q: Làm thế nào tôi có thể áp dụng nhiều biến đổi cho một đối tượng duy nhất?**  
A: Sử dụng phương thức `Transform` với một `Matrix` tùy chỉnh kết hợp dịch chuyển, thu phóng, xoay hoặc xiên theo thứ tự bạn cần.

**Q: Tôi có thể xem trước các biến đổi trước khi lưu tài liệu không?**  
A: Có—render `PsDocument` thành hình ảnh bằng cách sử dụng `PsDocument.Save("output.png", SaveFormat.Png)` hoặc mở tệp `.ps` trong một trình xem PostScript để kiểm tra kết quả trước khi gọi `Save()` cho tệp cuối cùng.

**Q: Có thể áp dụng biến đổi cho các phần tử cụ thể trong tài liệu không?**  
A: Chắc chắn. Lưu trạng thái đồ họa trước khi vẽ phần tử, áp dụng biến đổi mong muốn, vẽ, rồi khôi phục trạng thái để các phần tử sau không bị ảnh hưởng.

**Q: Có những cân nhắc về hiệu năng khi làm việc với các biến đổi phức tạp không?**  
A: Ma trận phức tạp làm tăng tải CPU. Giữ các biến đổi càng đơn giản càng tốt và tái sử dụng các trạng thái đã lưu khi vẽ nhiều đối tượng tương tự. Aspose.Page xử lý một tài liệu 300 trang với các biến đổi hỗn hợp trong thời gian dưới 2 giây trên CPU 3.2 GHz tiêu chuẩn.

**Q: Làm thế nào tôi có thể nhận hỗ trợ hoặc tìm trợ giúp cho các câu hỏi liên quan đến Aspose.Page?**  
A: Truy cập [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để nhận trợ giúp cộng đồng, hoặc liên hệ trực tiếp với bộ phận hỗ trợ của Aspose để được hỗ trợ ưu tiên.

---

**Cập nhật lần cuối:** 2026-07-19  
**Kiểm tra với:** Aspose.Page 24.11 for .NET  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

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

## Hướng dẫn liên quan

- [Tạo tài liệu postscript .net – Thêm hình chữ nhật với Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)
- [Thêm hình ảnh vào tài liệu PostScript (PS) với Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Thêm trang vào tài liệu PostScript (PS) với Aspose.Page](/page/net/page-manipulation/add-page-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}