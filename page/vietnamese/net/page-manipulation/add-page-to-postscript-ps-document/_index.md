---
date: 2026-03-03
description: Tìm hiểu cách đặt kích thước trang tùy chỉnh và thêm một trang PS thứ
  hai vào tài liệu PostScript bằng Aspose.Page cho .NET.
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Đặt kích thước trang tùy chỉnh trong tài liệu PS bằng Aspose.Page
url: /vi/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm Trang vào Tài liệu PostScript (PS) bằng Aspose.Page

## Giới thiệu

Trong phát triển .NET, khả năng **đặt kích thước trang tùy chỉnh** và **thêm trang PS thứ hai** vào một tài liệu PostScript (PS) cho phép bạn kiểm soát chi tiết bố cục của các bản in, báo cáo hoặc đồ họa được tạo ra. Aspose.Page cho .NET làm cho nhiệm vụ này trở nên đơn giản với một API sạch sẽ, hướng đối tượng. Trong hướng dẫn này, bạn sẽ học cách tạo một tệp PS đa trang, xác định kích thước tùy chỉnh cho mỗi trang, và lưu kết quả—tất cả chỉ với vài dòng mã C#.

## Câu trả lời nhanh
- **Tôi có thể đặt kích thước trang tùy chỉnh không?** Yes – chỉ cần truyền chiều rộng và chiều cao khi mở một trang.  
- **Làm thế nào để thêm trang PS thứ hai?** Gọi `document.OpenPage(width, height)` lần thứ hai.  
- **Phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tôi có cần giấy phép không?** Giấy phép tạm thời hoạt động cho việc thử nghiệm; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Tôi có thể tải Aspose.Page ở đâu?** Từ trang tải xuống chính thức được liên kết bên dưới.

## Yêu cầu trước

Trước khi bắt đầu hướng dẫn, hãy chắc chắn rằng bạn đã chuẩn bị các yêu cầu sau:

- Kiến thức làm việc về phát triển .NET.  
- Visual Studio đã được cài đặt trên máy của bạn.  
- Thư viện Aspose.Page cho .NET, bạn có thể tải về [tại đây](https://releases.aspose.com/page/net/).  
- Thư mục tài liệu ưa thích của bạn để thử nghiệm.

## Nhập không gian tên

Đảm bảo rằng bạn bao gồm các không gian tên cần thiết trong dự án để truy cập các chức năng do Aspose.Page cung cấp. Trong ví dụ được đưa ra, các không gian tên được bao gồm ngầm, nhưng bạn cần kiểm tra lại và điều chỉnh tùy theo cấu trúc dự án của mình.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Bước 1: Thiết lập dự án của bạn

Tạo một dự án .NET mới trong Visual Studio và thiết lập các cấu hình cần thiết. Đảm bảo tham chiếu thư viện Aspose.Page trong dự án của bạn.

## Đặt kích thước trang tùy chỉnh và Thêm trang PS thứ hai

Phần này trình bày chi tiết cách **đặt kích thước trang tùy chỉnh** cho mỗi trang và cách **thêm trang PS thứ hai** vào cùng một tài liệu.

### Bước 2: Khởi tạo tài liệu

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### Bước 3: Thêm Trang đầu tiên (kích thước mặc định)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### Bước 4: Thêm Trang thứ hai với Kích thước Khác (Tùy chỉnh)

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### Bước 5: Lưu tài liệu

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

Thực hiện các bước này một cách tỉ mỉ, và bạn sẽ thành công trong việc **đặt kích thước trang tùy chỉnh** và thêm một **trang PS thứ hai** vào tài liệu PostScript bằng Aspose.Page cho .NET.

## Tại sao điều này quan trọng

- **Bố cục chính xác** – Kích thước trang tùy chỉnh cho phép bạn khớp với thông số máy in hoặc tạo các định dạng brochure độc đáo.  
- **Nhiều trang** – Thêm trang thứ hai (hoặc hơn) cho phép tạo báo cáo đa trang mà không cần công cụ hợp nhất bên ngoài.  
- **Đa nền tảng** – Tệp PS được tạo có thể được hiển thị trên bất kỳ thiết bị tương thích PostScript nào hoặc chuyển đổi sang PDF sau này.

## Những lỗi thường gặp & Khắc phục

- **Đường dẫn không đúng** – Đảm bảo `dataDir` kết thúc bằng ký tự phân tách đường dẫn hoặc sử dụng `Path.Combine`.  
- **Vấn đề giấy phép** – Nếu không có giấy phép hợp lệ, thư viện có thể thêm watermark hoặc giới hạn số trang.  
- **Nhầm lẫn đơn vị** – Chiều rộng và chiều cao được đo bằng điểm (1 point = 1/72 inch). Điều chỉnh cho phù hợp.

## Câu hỏi thường gặp

**Câu hỏi 1: Aspose.Page có tương thích với các định dạng tài liệu khác nhau không?**  
A1: Aspose.Page chủ yếu tập trung vào việc thao tác tài liệu PostScript. Đối với các định dạng khác, bạn có thể khám phá các thư viện Aspose được thiết kế cho nhu cầu cụ thể.

**Câu hỏi 2: Tôi có thể tùy chỉnh kích thước trang trong Aspose.Page không?**  
A2: Chắc chắn! Như đã trình bày trong hướng dẫn, bạn có thể chỉ định các kích thước khác nhau cho mỗi trang theo yêu cầu của mình.

**Câu hỏi 3: Tôi có thể tìm thêm ví dụ và tài liệu ở đâu?**  
A3: Tham khảo [tài liệu](https://reference.aspose.com/page/net/) để có thông tin chi tiết và nhiều ví dụ đa dạng.

**Câu hỏi 4: Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.Page?**  
A4: Điều hướng tới [liên kết này](https://purchase.aspose.com/temporary-license/) để nhận giấy phép tạm thời cho mục đích thử nghiệm.

**Câu hỏi 5: Tôi có thể tìm hỗ trợ cộng đồng hoặc đặt câu hỏi ở đâu?**  
A5: Tham gia [diễn đàn cộng đồng Aspose.Page](https://forum.aspose.com/c/page/39) để kết nối với các nhà phát triển khác, chia sẻ kinh nghiệm và tìm kiếm trợ giúp.

---

**Cập nhật lần cuối:** 2026-03-03  
**Kiểm tra với:** Aspose.Page 24.11 for .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}