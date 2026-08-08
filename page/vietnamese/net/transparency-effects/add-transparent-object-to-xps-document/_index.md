---
date: 2026-03-29
description: Học cách thêm các đối tượng trong suốt vào tài liệu XPS và sau đó xuất
  XPS sang PDF bằng Aspose.Page cho .NET. Hướng dẫn từng bước kèm các mẹo thực tế.
linktitle: Add Transparent Object to XPS Document
second_title: Aspose.Page .NET API
title: Xuất XPS sang PDF – Thêm đối tượng trong suốt bằng Aspose.Page
url: /vi/net/transparency-effects/add-transparent-object-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Xuất XPS sang PDF – Thêm Đối Tượng Trong Suốt với Aspose.Page

## Giới thiệu

Trong tutorial này, bạn sẽ học cách thêm các đối tượng trong suốt vào tài liệu XPS và sau đó **xuất XPS sang PDF** với Aspose.Page cho .NET. Độ trong suốt có thể làm cho tài liệu của bạn trông hiện đại hơn và giúp làm nổi bật thông tin quan trọng. Chúng tôi sẽ hướng dẫn từng bước, giải thích lý do đằng sau mã, và cho bạn thấy cách hoàn thiện quy trình bằng cách chuyển đổi tệp XPS sang PDF để dễ dàng chia sẻ.

## Câu trả lời nhanh
- **Ý nghĩa của “export XPS to PDF” là gì?** Chuyển đổi một tệp XPS thành tệp PDF trong khi giữ nguyên bố cục, màu sắc và độ trong suốt.  
- **Tại sao phải thêm độ trong suốt trước?** Các đối tượng trong suốt cho phép bạn tạo đồ họa lớp đa tầng trông tuyệt vời trong PDF cuối cùng.  
- **Tôi có cần giấy phép không?** Có, cần có giấy phép Aspose.Page hợp lệ để sử dụng trong môi trường sản xuất.  
- **Có thể chạy trên .NET Core không?** Chắc chắn – Aspose.Page hỗ trợ .NET Core, .NET 5/6 và toàn bộ .NET Framework.  
- **Tôi có thể tìm thêm ví dụ ở đâu?** Kiểm tra tài liệu Aspose.Page và diễn đàn cộng đồng được liên kết bên dưới.

## Yêu cầu trước

Trước khi bắt đầu tutorial, hãy chắc chắn bạn đã chuẩn bị các yêu cầu sau:

- Aspose.Page for .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Page cho .NET. Bạn có thể tải xuống từ [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

## Nhập các Namespace

Để bắt đầu, bao gồm các namespace cần thiết trong dự án của bạn:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Bây giờ, hãy tiếp tục với hướng dẫn từng bước.

## Bước 1: Tạo Tài liệu XPS Mới

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Mã này khởi tạo một tài liệu XPS mới bằng Aspose.Page cho .NET.

## Bước 2: Thực hiện Độ trong suốt

```csharp
// Just to demonstrate transparency
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

Các dòng này tạo hai đường dẫn màu xám sẽ làm nền cho các hình dạng trong suốt mà chúng ta sẽ thêm sau.

## Bước 3: Tạo Đường dẫn với Hình chữ nhật Đóng

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Ở đây chúng ta tạo một hình chữ nhật màu xanh. Vì sau này chúng ta sẽ thay đổi độ mờ của nó, hình chữ nhật sẽ xuất hiện bán trong suốt trong PDF cuối cùng.

## Bước 4: Thao tác Đường dẫn và Màu sắc

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

Chúng ta sao chép hình chữ nhật đầu tiên, thêm nó vào trang, và chuyển màu nền sang màu xanh lá. Điều này minh họa cách dễ dàng tái sử dụng hình học hiện có.

## Bước 5: Nhân bản và Biến đổi Đường dẫn

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

Đường dẫn đã sao chép được dịch xuống 300 đơn vị và tô màu đỏ, tạo hiệu ứng lớp chồng lên nhau.

## Bước 6: Lặp lại và Sửa đổi Đường dẫn

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Chúng ta tái sử dụng dữ liệu hình học từ `path2`, di chuyển nó sang bên phải và áp dụng màu nền xanh lại.

## Bước 7: Quản lý Độ mờ

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

Đặt thuộc tính `Opacity` thành 0.8 làm cho hình chữ nhật này có độ mờ 80 %, minh họa cách bạn có thể tinh chỉnh độ trong suốt cho từng phần tử.

## Bước 8: Lưu Tài liệu XPS

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

Tệp XPS hiện đã được lưu với tất cả các đối tượng trong suốt đã được áp dụng.  

**Xuất sang PDF:** Để **xuất XPS sang PDF**, chỉ cần gọi lại `doc.Save` với phần mở rộng `.pdf`, ví dụ, `doc.Save(dataDir + "TransparentDocument.pdf");`. Độ trung thực hình ảnh, bao gồm các thiết lập độ trong suốt, sẽ được giữ nguyên trong PDF tạo ra.

## Tại sao phải xuất XPS sang PDF sau khi thêm độ trong suốt?

- **Tương thích rộng rãi:** PDF được hỗ trợ rộng rãi trên nhiều nền tảng, trong khi XPS còn khá hẹp.  
- **Bảo toàn hiệu ứng hình ảnh:** Aspose.Page giữ nguyên độ trong suốt, gradient và các phép biến đổi ma trận trong quá trình chuyển đổi.  
- **Dễ dàng chia sẻ:** PDF có thể mở trong trình duyệt, thiết bị di động và nhiều phần mềm đọc khác mà không cần plugin bổ sung.

## Các trường hợp sử dụng phổ biến

- **Brochure marketing** nơi đồ họa lớp đa tầng tạo cảm giác cao cấp.  
- **Sơ đồ kỹ thuật** cần làm nổi bật các phần mà không làm rối bố cục.  
- **Tạo báo cáo** khi bạn muốn chồng watermark hoặc logo với độ trong suốt một phần.

## Mẹo & Lưu ý

- **Mẹo chuyên nghiệp:** Luôn đặt giá trị `Opacity` trong khoảng 0 đến 1. Các giá trị ngoài phạm vi này sẽ bị cắt và có thể cho kết quả không mong muốn.  
- **Mẹo hiệu năng:** Tái sử dụng hình học (`path2.Data`) giảm tiêu thụ bộ nhớ khi bạn cần nhiều hình dạng tương tự.  
- **Cạm bẫy:** Lưu trực tiếp sang PDF sau khi thêm độ trong suốt hoạt động ngay lập tức, nhưng nếu bạn chỉnh sửa PDF bằng các công cụ khác, một số trình xem cũ có thể không hiển thị độ trong suốt đúng cách.

## Kết luận

Thêm các đối tượng trong suốt vào tài liệu XPS bằng Aspose.Page cho .NET cung cấp một cách linh hoạt để nâng cao trình bày hình ảnh. Khi tệp XPS của bạn đã đạt dạng mong muốn, bạn có thể **xuất XPS sang PDF** chỉ bằng một dòng lệnh, giữ nguyên tất cả các hiệu ứng trong suốt cho việc phân phối rộng rãi.

## Câu hỏi thường gặp

### Câu 1: Tôi có thể áp dụng độ trong suốt cho bất kỳ đối tượng nào trong tài liệu XPS không?

A1: Có, độ trong suốt có thể được áp dụng cho nhiều đối tượng như đường dẫn, hình dạng và hình ảnh trong tài liệu XPS.

### Câu 2: Làm sao tôi có thể điều chỉnh độ mờ của một phần tử cụ thể?

A2: Bạn có thể đặt thuộc tính độ trong suốt của Fill hoặc Stroke để điều chỉnh độ trong suốt của phần tử đó.

### Câu 3: Aspose.Page có tương thích với .NET Core không?

A3: Có, Aspose.Page hỗ trợ .NET Core, cho phép phát triển đa nền tảng.

### Câu 4: Tôi có thể xuất tài liệu XPS sang các định dạng khác bằng Aspose.Page không?

A4: Aspose.Page cung cấp chức năng xuất tài liệu XPS sang nhiều định dạng, bao gồm PDF và hình ảnh.

### Câu 5: Tôi có thể tìm hỗ trợ và thảo luận cộng đồng ở đâu?

A5: Để nhận hỗ trợ bổ sung và thảo luận cộng đồng, hãy truy cập [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

### Câu 6: Quá trình chuyển đổi PDF có giữ lại các thiết lập độ trong suốt của tôi không?

A6: Chắc chắn. Khi bạn xuất XPS sang PDF với Aspose.Page, tất cả các thiết lập độ trong suốt và pha trộn đều được giữ nguyên.

### Câu 7: Tôi có thể xử lý hàng loạt nhiều tệp XPS sang PDF không?

A7: Có, bạn có thể lặp qua một tập hợp các tệp XPS và gọi `doc.Save(...".pdf")` cho mỗi tệp, tự động hoá quá trình chuyển đổi hàng loạt.

**Last Updated:** 2026-03-29  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}