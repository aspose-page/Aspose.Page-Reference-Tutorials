---
date: 2026-01-23
description: Tìm hiểu cách chỉnh sửa tệp EPS bằng cách thêm các giá trị có tên sử
  dụng Aspose.Page cho .NET. Hướng dẫn từng bước này giúp các nhà phát triển thao
  tác với siêu dữ liệu EPS.
linktitle: Add Named Value
second_title: Aspose.Page .NET API
title: Cách chỉnh sửa tệp EPS – Thêm giá trị có tên với Aspose.Page
url: /vi/net/eps-metadata-management/modify-eps-metadata-add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách chỉnh sửa tệp EPS – Thêm giá trị có tên với Aspose.Page

## Cách chỉnh sửa tệp EPS – Giới thiệu

Trong hướng dẫn này về **cách chỉnh sửa EPS**, chúng tôi sẽ hướng dẫn bạn cách thêm một giá trị có tên vào tài liệu EPS bằng thư viện Aspose.Page cho .NET. Dù bạn đang xây dựng công cụ xử lý hàng loạt hay cần làm phong phú siêu dữ liệu EPS ngay lập tức, các bước dưới đây sẽ cung cấp cho bạn một hướng dẫn rõ ràng, nhanh
- ** dữ liệu XMP.  
- **Phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tôi có cần giấy phép không?** Có bản dùng thử miễn phí, nhưng giấy phép thương mại là bắt buộc cho việc sử dụng trong môi trường sản xuất.  
- **Thời gian thực hiện khoảng bao lâu?** Thông thường dưới 10 phút cho kịch bản giá trị có tên cơ bản.  
- **Có an toàn cho các tệp EPS lớn không?** Có – Aspose.Page truyền dữ liệu theo luồng, giữ mức sử dụng bộ nhớ thấp.

## Yêu cầu trước

Trước khi bắt đầu hướng dẫn, hãy chắc chắn rằng bạn đã chuẩn bị các yêu cầu sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Một môi trường phát triển tích hợp (IDE) như Visual Studio đã được cài đặt.
- Thư viện Aspose.Page cho .NET. Nếu chưa cài đặt, bạn có thể tải xuống từ [here](https://releases.aspose.com/page/net/).

## Nhập các không gian tên

Đầu tiên, hãy nhập các không gian tên cần thiết vào mã C# của bạn. Các không gian tên này rất quan trọng để truy cập các chức năng do Aspose.Page cung cấp:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Bước 1: Khởi tạo luồng nhập tệp EPS

Bước đầu tiên liên quan đến việc khởi tạo luồng nhập cho tệp EPS. Thay thế `"Your Document Directory"` bằng đường dẫn tới thư mục tài liệu của bạn:

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Bước 2: Lấy siêu dữ liệu XMP

Lấy siêu dữ liệu XMP từ tệp EPS. Nếu tệp EPS không có siêu dữ liệu XMP, một siêu dữ liệu mới sẽ được tạo, được điền bằng các giá trị từ các chú thích siêu dữ liệu PS:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Bước 3: Thay đổi giá trị siêu dữ liệu XMP

Bây giờ, chúng ta sẽ thực hiện các thay đổi đối với siêu dữ liệu XMP. Trong ví dụ này, chúng ta sẽ thêm một giá trị có tên vào cấu trúc `"xmpTPg:MaxPageSize"`:

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Bước 4: Lưu tệp EPS với siêu dữ liệu XMP đã thay đổi

Lưu tệp EPS với siêu dữ liệu XMP đã cập nhật. Tạo một luồng xuất và lưu tệp EPS đã chỉnh sửa:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Kết luận

Chúc mừng! Bạn đã thành công thêm một giá trị có tên vào tệp EPS bằng cách sử dụng Aspose.Page trong .NET. Hướng dẫn này cho thấy việc **chỉnh sửa EPS** siêu dữ liệu thật đơn giản, cho phép bạn làm phong phú tài liệu một cách lập trình.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Page có tương thích với các phiên bản tệp EPS khác nhau không?

A1: Aspose.Page hỗ trợ thích với đa2: Có, Aspose.Page đi kèm với giấy phép thương mại, và bạn có thể mua nó [here](https://purchase.aspose.com/buy).

### Câu hỏi 3: Có bản dùng thử miễn phí cho Aspose.Page không?

A3: Có, bạn có thể khám phá Aspose.Page với bản dùng thử miễn phí tại [here](https://releases.aspose.com/).

### Câu hỏi 4: Làm thế nào để tôi nhận được hỗ trợ hoặc kết nối với cộng đồng Aspose?

A4: Truy cập [Aspose.Page forum](https://forum.aspose.com/c/page/39) để nhận hỗ trợ và kết nối với cộng đồng.

### Câu hỏi 5: Giấy phép tạm thời là gì và làm sao tôi có thể lấy được?

A5: Nếu bạn cần giấy phép tạm thời để thử nghiệm hoặc đánh giá, bạn có thể lấy một giấy phép [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-23  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

---