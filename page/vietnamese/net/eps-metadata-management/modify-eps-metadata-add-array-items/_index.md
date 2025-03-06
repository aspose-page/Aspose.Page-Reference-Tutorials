---
title: Thêm các mục mảng với Aspose.Page
linktitle: Thêm các mục mảng
second_title: API Aspose.Page .NET
description: Khám phá cách thêm các mục mảng trong tệp EPS bằng Aspose.Page cho .NET. Thực hiện theo hướng dẫn từng bước của chúng tôi để thao tác tài liệu liền mạch.
weight: 11
url: /vi/net/eps-metadata-management/modify-eps-metadata-add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm các mục mảng với Aspose.Page

## Giới thiệu

Trong lĩnh vực thao tác và xử lý tài liệu trong .NET, Aspose.Page nổi bật như một công cụ mạnh mẽ. Trong số nhiều khả năng của nó, việc xử lý các mục mảng trong tệp EPS là một yêu cầu chung. Trong hướng dẫn này, chúng ta sẽ khám phá quy trình từng bước thêm các mục mảng bằng Aspose.Page trong môi trường .NET. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay người mới, hướng dẫn này sẽ hướng dẫn bạn thực hiện quy trình một cách rõ ràng và chính xác.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Hiểu biết cơ bản về lập trình .NET.
-  Aspose.Page cho .NET được cài đặt. Nếu không, bạn có thể tải nó từ[đây](https://releases.aspose.com/page/net/).
- Một trình soạn thảo mã, chẳng hạn như Visual Studio, để làm theo các ví dụ.

## Nhập không gian tên

Trong dự án .NET của bạn, hãy đảm bảo nhập các vùng tên cần thiết để sử dụng các chức năng Aspose.Page. Thêm các dòng sau vào đầu mã của bạn:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Các không gian tên này cung cấp quyền truy cập vào các lớp và phương thức thiết yếu cần thiết để thao tác với tệp EPS.

## Bước 1: Khởi tạo luồng đầu vào tệp EPS

```csharp
// Bắt đầu:3
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";
// Khởi tạo luồng đầu vào tệp EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Tạo phiên bản PsDocument từ luồng
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

 Ở đây, chúng tôi đang thiết lập luồng đầu vào ban đầu cho tệp EPS và tạo một`PsDocument` ví dụ.

## Bước 2: Nhận siêu dữ liệu XMP

```csharp
// ExStart:4
// Nhận siêu dữ liệu XMP. Nếu tệp EPS không chứa siêu dữ liệu XMP, chúng tôi sẽ nhận được tệp mới chứa đầy các giá trị từ nhận xét siêu dữ liệu PS (%%Creator, %%CreatDate, %%Title, v.v.)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

Truy xuất siêu dữ liệu XMP từ tệp EPS. Nếu tệp EPS thiếu siêu dữ liệu XMP thì một tệp mới sẽ được tạo với các giá trị từ nhận xét siêu dữ liệu PS.

## Bước 3: Thay đổi giá trị siêu dữ liệu XMP

```csharp
// ExStart:5
// Thay đổi giá trị siêu dữ liệu XMP

// Thêm một tiêu đề nữa. Nó sẽ được thêm vào cuối mảng theo mặc định.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Thêm một người sáng tạo nữa. Nó sẽ được thêm vào mảng theo chỉ số (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

Sửa đổi siêu dữ liệu XMP bằng cách thêm tiêu đề và người tạo mới vào mảng.

## Bước 4: Lưu tệp EPS với siêu dữ liệu XMP đã thay đổi

```csharp
// ExStart:6
// Lưu tệp EPS với siêu dữ liệu XMP đã thay đổi

// Tạo luồng đầu ra
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Lưu tập tin EPS
    document.Save(outPsStream);
}
// ExEnd:6
```

Cuối cùng, lưu tệp EPS với siêu dữ liệu XMP đã cập nhật. Những thay đổi được thực hiện đối với các mục trong mảng sẽ được phản ánh trong tệp đầu ra.

## Phần kết luận

Việc thêm các mục mảng bằng Aspose.Page trong .NET là một quá trình đơn giản, như được trình bày trong hướng dẫn này. Với các điều kiện tiên quyết phù hợp và hướng dẫn từng bước, nhà phát triển có thể thao tác liền mạch với tệp EPS, đảm bảo tài liệu của họ đáp ứng các yêu cầu siêu dữ liệu cụ thể.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Page có tương thích với tất cả môi trường .NET không?

Câu trả lời 1: Có, Aspose.Page được thiết kế để hoạt động liền mạch với tất cả các môi trường .NET, cung cấp chức năng nhất quán trên các nền tảng.

### Câu 2: Tôi có thể sử dụng Aspose.Page miễn phí không?

 Câu trả lời 2: Aspose.Page cung cấp phiên bản dùng thử miễn phí, cho phép người dùng khám phá các tính năng của nó. Để tiếp tục sử dụng, phải mua giấy phép từ[đây](https://purchase.aspose.com/buy).

### Câu hỏi 3: Giấy phép tạm thời có sẵn cho Aspose.Page không?

 Câu trả lời 3: Có, giấy phép tạm thời có thể được lấy từ[đây](https://purchase.aspose.com/temporary-license/) cho nhu cầu dự án ngắn hạn.

### Câu hỏi 4: Tôi có thể tìm sự hỗ trợ của cộng đồng cho Aspose.Page ở đâu?

A4: Để thảo luận và hỗ trợ cộng đồng, hãy truy cập[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39).

### Câu hỏi 5: Phiên bản mới nhất của Aspose.Page dành cho .NET là gì?

 Câu trả lời 5: Để truy cập phiên bản mới nhất của Aspose.Page cho .NET, hãy tham khảo[tài liệu](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
