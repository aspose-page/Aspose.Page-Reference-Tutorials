---
date: 2026-03-03
description: Tìm hiểu cách thay đổi kích thước hình ảnh EPS trong .NET với Aspose.Page
  – hướng dẫn từng bước về cách thay đổi kích thước EPS bằng điểm, inch, milimét hoặc
  phần trăm.
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: Cách thay đổi kích thước hình ảnh EPS bằng Aspose.Page cho .NET
url: /vi/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thay đổi kích thước hình ảnh EPS với Aspose.Page cho .NET

## Introduction

Bạn đang tìm kiếm **cách thay đổi kích thước EPS** một cách liền mạch bằng Aspose.Page cho .NET? Hướng dẫn này là tài liệu toàn diện giúp bạn dễ dàng thao tác kích thước của hình ảnh EPS ở các đơn vị khác nhau như points, inches, millimeters và percentages. Aspose.Page cho .NET cung cấp một bộ công cụ mạnh mẽ, và trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước.

## Quick Answers
- **Thư viện nào xử lý việc thay đổi kích thước EPS?** Aspose.Page for .NET  
- **Các đơn vị nào được hỗ trợ?** Points, Inches, Millimeters, và Percents  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** Có – cần giấy phép thương mại  
- **Tôi có thể thay đổi kích thước nhiều tệp cùng lúc không?** Chắc chắn – chỉ cần lặp qua các tệp  
- **.NET Core có được hỗ trợ không?** Có, API hoạt động với .NET Framework và .NET Core  

## What is EPS Resizing?
Encapsulated PostScript (EPS) là một định dạng đồ họa dựa trên vector thường được sử dụng trong quy trình in ấn và thiết kế. Thay đổi kích thước một tệp EPS thay đổi bounding box mà không rasterize tác phẩm, giữ độ sắc nét ở bất kỳ tỉ lệ nào.

## Why Resize EPS Images?
- **Duy trì chất lượng in:** Thu phóng vector giữ các cạnh sắc nét.  
- **Phù hợp với yêu cầu bố cục:** Điều chỉnh kích thước để khớp với trang hoặc kích thước canvas.  
- **Tự động hoá công việc batch:** Thay đổi kích thước hàng chục tệp một cách lập trình trong vài giây.  

## Prerequisites

Trước khi bắt đầu vào phép thuật thay đổi kích thước, hãy đảm bảo bạn đã có các yêu cầu sau:

- Aspose.Page for .NET Library: Đảm bảo bạn đã cài đặt thư viện Aspose.Page cho .NET. Bạn có thể tải xuống từ [here](https://releases.aspose.com/page/net/).

- Document Directory: Tạo một thư mục để lưu trữ tệp EPS đầu vào và các tệp đã thay đổi kích thước đầu ra.

Bây giờ bạn đã có mọi thứ sẵn sàng, hãy tiến hành nhập các namespace cần thiết và đi sâu vào hướng dẫn từng bước.

## Import Namespaces

Trong dự án .NET của bạn, bắt đầu bằng việc nhập các namespace cần thiết để làm việc với Aspose.Page. Thêm đoạn mã sau vào đầu file của bạn:

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

## How to Resize EPS in Points

Points là một đơn vị đo chuẩn trong ngành in ấn. Ví dụ dưới đây gấp đôi chiều rộng và chiều cao gốc.

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
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

## How to Resize EPS in Inches

Inches thường được các nhà thiết kế đồ họa sử dụng khi chuẩn bị tài nguyên cho việc in ấn.

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
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

## How to Resize EPS in Millimeters

Millimeters phổ biến ở các khu vực sử dụng hệ mét.

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
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

## How to Resize EPS Using Percentages

Việc thay đổi kích thước dựa trên phần trăm cho phép bạn thu phóng hình ảnh tương đối so với kích thước gốc.

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
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

Bạn có thể tự do tích hợp các phương pháp này vào dự án của mình, và bạn sẽ thay đổi kích thước hình ảnh EPS một cách dễ dàng. Hãy thử nghiệm với các đơn vị khác nhau để đạt được kích thước mong muốn.

## Common Issues and Solutions
- **File không tồn tại:** Kiểm tra `dataDir` trỏ tới thư mục đúng và `input.eps` tồn tại.  
- **Kích thước không mong đợi:** Nhớ rằng `Units.Percents` yêu cầu giá trị như 150 cho 150 % kích thước gốc.  
- **Lỗi giấy phép:** Nếu bạn gặp lỗi giấy phép, hãy chắc chắn rằng tệp giấy phép Aspose.Page hợp lệ đã được tải trước khi tạo `PsDocument`.

## Conclusion

Chúc mừng! Bạn đã thành thạo **cách thay đổi kích thước EPS** với Aspose.Page cho .NET. Thư viện mạnh mẽ này mở ra một thế giới khả năng cho việc thao tác đồ họa vector. Dù bạn đang thiết kế cho in ấn hay truyền thông kỹ thuật số, Aspose.Page cho phép bạn đạt được kết quả chính xác và tùy chỉnh.

## FAQ's

### Q1: Tôi có thể thay đổi kích thước nhiều hình ảnh EPS đồng thời không?

A1: Có, bạn có thể lặp qua một tập hợp các tệp EPS, áp dụng các phương pháp thay đổi kích thước tương ứng.

### Q2: Aspose.Page có tương thích với các định dạng hình ảnh khác không?

A2: Aspose.Page chủ yếu tập trung vào định dạng PostScript và EPS. Đối với các định dạng hình ảnh khác, hãy cân nhắc sử dụng Aspose.Imaging.

### Q3: Có những lưu ý về giấy phép cho các dự án thương mại không?

A3: Có, hãy đảm bảo bạn có giấy phép hợp lệ. Truy cập [here](https://purchase.aspose.com/buy) để biết chi tiết về giấy phép.

### Q4: Tôi có thể dùng thử Aspose.Page trước khi mua không?

A4: Chắc chắn! Bạn có thể nhận bản dùng thử miễn phí [here](https://releases.aspose.com/).

### Q5: Tôi có thể tìm trợ giúp bổ sung hoặc thảo luận các vấn đề ở đâu?

A5: Truy cập [Aspose.Page forum](https://forum.aspose.com/c/page/39) để kết nối với cộng đồng và nhận hỗ trợ.

## Frequently Asked Questions

**Q: Mã này có hoạt động với .NET Core 6 không?**  
A: Có. API tương thích với .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, và .NET 6+.

**Q: Làm sao để giữ nguyên hồ sơ màu gốc?**  
A: Phương thức `ResizeEps` không thay đổi dữ liệu màu; nó chỉ thay đổi bounding box.

**Q: Có thể thay đổi kích thước EPS mà không tải toàn bộ tệp vào bộ nhớ không?**  
A: Sử dụng stream như trong ví dụ giúp giảm mức sử dụng bộ nhớ; tài liệu được xử lý ngay khi đọc.

**Q: Tôi có thể chuỗi nhiều thao tác thay đổi kích thước không?**  
A: Chắc chắn. Gọi `ResizeEps` liên tiếp trên cùng một đối tượng `PsDocument`.

**Q: Điều gì xảy ra với các hình ảnh nhúng bên trong EPS?**  
A: Chúng được thu phóng tỷ lệ cùng với nội dung vector, giữ nguyên chất lượng.

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}