---
date: 2026-01-10
description: Tìm hiểu cách hợp nhất tài liệu XPS bằng Aspose.Page cho .NET. Hướng
  dẫn từng bước này trình bày các kỹ thuật thao tác trang để đạt hiệu quả tối ưu.
linktitle: Manipulate Pages
second_title: Aspose.Page .NET API
title: Hợp nhất tài liệu XPS với Aspose.Page cho .NET
url: /vi/net/cross-document-editing/manipulate-pages/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kết hợp tài liệu XPS với Aspose.Page cho .NET

## Giới thiệu

Trong hướng dẫn này, bạn sẽ khám phá cách **kết hợp tài liệu XPS** và thao tác các trang của chúng bằng thư viện Aspose.Page trong môi trường .NET. Dù bạn cần kết hợp nhiều báo cáo thành một tệp XPS duy nhất hoặc sắp xếp lại các trang để có kết quả hoàn thiện, hướng dẫn này sẽ hướng dẫn bạn qua từng bước với các giải pháp rõ ràng và sẵn sàng chạy.

## Trả lời nhanh
- **Bạn có thể làm gì với Aspose.Page?** Kết hợp tài liệu XPS, chèn, thêm hoặc xóa các trang và lưu kết quả.
- **Có cần giấy phép để thử nghiệm không?** Có sẵn một giấy phép tạm thời để đánh giá.
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
- **Có cần Visual Studio không?** Không, bất kỳ IDE nào hỗ trợ C# đều hoạt động, nhưng Visual Studio được khuyến nghị.
- **Quá trình kết hợp mất bao lâu?** Thông số chỉ vài giây thông thường cho tiêu chuẩn kích thước XPS của tệp.

## Hợp nhất tài liệu XPS là gì?
Kết quả XPS tài liệu hợp nhất có nghĩa là tìm các trang từ hai hoặc nhiều tệp XPS hiện có và tổng hợp chúng lại thành một XPS duy nhất tài liệu. Điều này hữu ích cho việc tạo tổng hợp báo cáo, biên soạn nhiều trang hoặc chuẩn bị sẵn các gói mà không cần chuyển đổi sang định dạng khác.

## Tại sao nên sử dụng Aspose.Page cho .NET?
Aspose.Page cung cấp một **API .NET tĩnh** làm việc trực tiếp với các tệp XPS—không cần công cụ bên ngoài hay thành phần của bên thứ ba. Nó cho phép bạn kiểm soát chi tiết trang, vị trí và chèn công việc tồn tại nội dung, làm cho quá trình kết thúc trở nên đáng tin cậy và nhanh chóng.

## Điều kiện tiên quyết

- **Aspose.Page for .NET** – tải xuống từ [tài liệu Aspose.Page for .NET](https://reference.aspose.com/page/net/).
- **Môi trường phát triển** – Visual Studio, Rider, hoặc bất kỳ IDE nào hỗ trợ C#.
- ** Đầu vào tệp XPS** – ba mẫu tệp (`input1.xps`, `input2.xps`, `input3.xps`) được đặt trong một thư mục đã biết.

## Nhập không gian tên

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Các không gian tên này cho phép bạn truy cập vào các lớp tài liệu XPS cốt lõi, mô hình trang và các tiện ích vẽ cơ bản.

## Bước 1: Thiết lập thư mục tài liệu

```csharp
string dataDir = "Your Document Directory";
```

Thay thế **Your Document Directory** bằng đường dẫn đầy đủ nơi lưu trữ các tệp XPS của bạn, ví dụ: `C:\\Docs\\XpsFiles\\`.

## Bước 2: Tạo các bản sao tài liệu XPS

```csharp
XpsDocument doc1 = new XpsDocument(dataDir + "input1.xps");
XpsDocument doc2 = new XpsDocument(dataDir + "input2.xps");
XpsDocument doc3 = new XpsDocument(dataDir + "input3.xps");
XpsDocument doc4 = new XpsDocument();
```

- `doc1`, `doc2`, và `doc3` đại diện cho các tài liệu nguồn mà bạn muốn kết hợp.  
- `doc4` là một tài liệu XPS trống sẽ chứa kết quả đã được kết hợp.

## Bước 3: Chèn, thêm và xóa trang

```csharp
doc4.InsertPage(1, doc2.Page, false);
doc4.AddPage(doc3.Page, false);
doc4.RemovePageAt(2);
doc4.InsertPage(2, doc1.SelectActivePage(3), false);
```

Đây là những gì mỗi dòng thực hiện:

1. **InsertPage(1, doc2.Page, false)** – đặt trang đầu tiên của `doc2` vào vị trí 1 trong `doc4`.  
2. **AddPage(doc3.Page, false)** – thêm trang đầu tiên của `doc3` vào cuối `doc4`.  
3. **RemovePageAt(2)** – xóa trang hiện tại ở chỉ mục 2 (hữu ích để loại bỏ các trang không mong muốn).  
4. **InsertPage(2, doc1.SelectActivePage(3), false)** – chèn trang thứ ba của `doc1` vào vị trí 2, hoàn thành việc kết hợp.

Các thao tác này minh họa cách bạn có thể **kết hợp tài liệu XPS** trong khi sắp xếp lại hoặc loại bỏ các trang khi cần.

## Bước 4: Lưu tài liệu đã hợp nhất

```csharp
doc4.Save(dataDir + "out.xps");
```

Tệp XPS đã được kết hợp cuối cùng (`out.xps`) được ghi vào cùng thư mục. Bạn có thể mở nó trong bất kỳ trình xem XPS nào hoặc tiếp tục xử lý nó bằng Aspose.Page.

## Các vấn đề thường gặp và giải pháp
- **Không tìm thấy tệp** – kiểm tra lại đường dẫn `dataDir` và đảm bảo các tệp đầu vào tồn tại.
- **Chỉ mục trang không hợp lệ** – chỉ mục trang bắt đầu từ 1; cố gắng chèn một trang không tồn tại sẽ gây ra ngoại lệ.
- **Lỗi giấy phép** – use giấy phép tạm thời hoặc đầy đủ trước khi phát triển khai báo vào môi trường sản xuất.

## Câu hỏi thường gặp

**Q: Tôi có thể kết hợp hơn ba tệp XPS không?**
A: Chắc chắn. Tạo thêm các thể hiện `XpsDocument` và sử dụng liên tục `InsertPage` hoặc `AddPage` để xây dựng một kết hợp tài liệu lớn hơn.

**Q: Quá trình kết hợp có định dạng nguyên và không có đồ họa gốc?**
A: Có. Aspose.Page sao chép nội dung trang theo từng byte, vì bản văn, hình ảnh và vectơ đồ họa vẫn không thay đổi.

**Q: Làm sao để chèn một trang vào cuối mà không cần chỉ định mục?**
A: Sử dụng `AddPage(sourcePage, false)` để thêm trang vào tài liệu cuối cùng.

**Q: Có thể kết hợp XPS tài liệu trên máy chủ mà không có người dùng giao diện?**
A: API hoàn toàn không có giao diện; bạn có thể chạy cùng mã hóa trong ASP.NET, Azure Functions hoặc bất kỳ môi trường .NET nào từ máy chủ.

**Q: Nếu các tệp XPS của tôi được bảo vệ bằng mật khẩu thì sao?**
A: Aspose.Page hiện không hỗ trợ các tệp XPS được mã hóa; bạn phải giải mã chúng trước khi hợp nhất.

---

**Cập nhật lần cuối:** 2026-01-10
**Kiểm tra với:** Aspose.Page for .NET 24.10
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}