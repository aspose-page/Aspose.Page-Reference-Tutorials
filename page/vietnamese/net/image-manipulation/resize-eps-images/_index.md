---
title: Thay đổi kích thước hình ảnh EPS bằng Aspose.Page cho .NET
linktitle: Thay đổi kích thước hình ảnh EPS
second_title: API Aspose.Page .NET
description: Khám phá quy trình thay đổi kích thước hình ảnh EPS trong .NET một cách liền mạch bằng Aspose.Page. Đạt được độ chính xác theo điểm, inch, milimet và tỷ lệ phần trăm một cách dễ dàng.
weight: 11
url: /vi/net/image-manipulation/resize-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thay đổi kích thước hình ảnh EPS bằng Aspose.Page cho .NET

## Giới thiệu

Bạn đang muốn thay đổi kích thước hình ảnh EPS một cách liền mạch bằng Aspose.Page cho .NET? Hướng dẫn này là hướng dẫn toàn diện giúp bạn dễ dàng thao tác kích thước của hình ảnh EPS theo nhiều đơn vị khác nhau như điểm, inch, milimét và tỷ lệ phần trăm. Aspose.Page cho .NET cung cấp một bộ công cụ mạnh mẽ và trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước thực hiện quy trình.

## Điều kiện tiên quyết

Trước khi đi sâu vào phép thuật thay đổi kích thước, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

-  Aspose.Page for .NET Library: Đảm bảo bạn đã cài đặt thư viện Aspose.Page cho .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/page/net/).

- Thư mục Tài liệu: Tạo một thư mục nơi bạn sẽ lưu trữ tệp EPS đầu vào và các tệp đã thay đổi kích thước đầu ra.

Bây giờ bạn đã thiết lập xong mọi thứ, hãy tiến hành nhập các không gian tên cần thiết và đi sâu vào hướng dẫn từng bước.

## Nhập không gian tên

Trong dự án .NET của bạn, hãy bắt đầu bằng cách nhập các vùng tên cần thiết để hoạt động với Aspose.Page. Thêm mã sau vào đầu tệp của bạn:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## Bước 1: Thay đổi kích thước điểm

Hãy bắt đầu bằng cách thay đổi kích thước hình ảnh EPS theo điểm. Điểm là đơn vị đo lường tiêu chuẩn trong ngành in ấn.

```csharp
public static void ResizeInPoints()
{
    // Thư mục tài liệu của bạn
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## Bước 2: Thay đổi kích thước theo inch

Bây giờ, hãy thay đổi kích thước hình ảnh EPS theo inch, một đơn vị phổ biến được sử dụng trong thiết kế đồ họa.

```csharp
public static void ResizeInInches()
{
    // Thư mục tài liệu của bạn
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## Bước 3: Thay đổi kích thước theo milimét

Bây giờ, hãy thay đổi kích thước hình ảnh EPS theo milimet, một đơn vị khác được sử dụng rộng rãi trong thiết kế và in ấn.

```csharp
public static void ResizeInMillimeters()
{
    // Thư mục tài liệu của bạn
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## Bước 4: Thay đổi kích thước theo phần trăm

Cuối cùng, hãy thay đổi kích thước hình ảnh EPS bằng tỷ lệ phần trăm, cung cấp cách tiếp cận linh hoạt để điều chỉnh kích thước hình ảnh.

```csharp
public static void ResizeInPercents()
{
    // Thư mục tài liệu của bạn
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

Hãy thoải mái tích hợp các phương pháp này vào dự án của bạn và bạn sẽ thay đổi kích thước hình ảnh EPS một cách dễ dàng. Thử nghiệm với các đơn vị khác nhau để đạt được kích thước mong muốn.

## Phần kết luận

Chúc mừng! Bạn đã thành thạo nghệ thuật thay đổi kích thước hình ảnh EPS bằng Aspose.Page cho .NET. Thư viện mạnh mẽ này mở ra một thế giới khả năng thao tác đồ họa vector. Cho dù bạn đang thiết kế cho phương tiện in ấn hay kỹ thuật số, Aspose.Page đều cho phép bạn đạt được kết quả chính xác và tùy chỉnh.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể thay đổi kích thước nhiều hình ảnh EPS cùng một lúc không?

Câu trả lời 1: Có, bạn có thể lặp qua một tập hợp các tệp EPS, áp dụng các phương pháp thay đổi kích thước cho phù hợp.

### Câu hỏi 2: Aspose.Page có tương thích với các định dạng hình ảnh khác không?

Câu trả lời 2: Aspose.Page chủ yếu tập trung vào các định dạng PostScript và EPS. Đối với các định dạng hình ảnh khác, hãy cân nhắc sử dụng Aspose.Imaging.

### Câu hỏi 3: Có bất kỳ cân nhắc nào về việc cấp phép cho các dự án thương mại không?

 A3: Có, đảm bảo bạn có giấy phép hợp lệ. Thăm nom[đây](https://purchase.aspose.com/buy) để biết chi tiết cấp phép.

### Câu hỏi 4: Tôi có thể dùng thử Aspose.Page trước khi mua không?

 A4: Chắc chắn rồi! Bạn có thể dùng thử miễn phí[đây](https://releases.aspose.com/).

### Câu hỏi 5: Tôi có thể tìm thêm trợ giúp hoặc thảo luận vấn đề ở đâu?

 A5: Tham quan[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để kết nối với cộng đồng và nhận được sự trợ giúp.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
