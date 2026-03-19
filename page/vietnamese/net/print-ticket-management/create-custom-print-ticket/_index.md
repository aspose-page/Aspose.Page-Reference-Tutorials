---
date: 2026-03-19
description: Tìm hiểu cách thêm vé bằng cách tạo vé in tùy chỉnh với Aspose.Page cho
  .NET. Tùy chỉnh trải nghiệm in của bạn với kiểm soát chi tiết.
linktitle: Create Custom Print Ticket
second_title: Aspose.Page .NET API
title: 'Cách Thêm Ticket: Tạo Ticket In Tùy Chỉnh với Aspose.Page cho .NET'
url: /vi/net/print-ticket-management/create-custom-print-ticket/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Ticket: Tạo Custom Print Ticket với Aspose.Page cho .NET

## Introduction

Nếu bạn cần chức năng **cách thêm ticket** trong một ứng dụng .NET, Aspose.Page cung cấp khả năng tạo custom print ticket trực tiếp từ mã. Trong hướng dẫn này, chúng tôi sẽ đi qua toàn bộ quá trình—cài đặt môi trường, tạo tài liệu XPS, đính kèm custom job print ticket, và lưu kết quả. Khi hoàn thành, bạn sẽ có thể thêm hỗ trợ ticket vào bất kỳ quy trình in nào một cách tự tin.

## Quick Answers
- **“Thêm ticket” có nghĩa là gì?** Nó đề cập đến việc nhúng một custom print ticket (metadata XPS) để điều khiển cài đặt máy in.  
- **Thư viện nào được yêu cầu?** Aspose.Page for .NET.  
- **Tôi có cần giấy phép không?** Giấy phép tạm thời hoạt động cho việc đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Tôi có thể sử dụng với .NET Core không?** Có, Aspose.Page hỗ trợ .NET Framework và .NET Core.  
- **Thời gian triển khai mất bao lâu?** Thông thường dưới 15 phút cho một ticket cơ bản.

## What is a Custom Print Ticket?
Custom print ticket là mô tả dựa trên XML về các tùy chọn máy in (như sắp xếp, số bản sao, quản lý màu sắc, v.v.) đi kèm với tài liệu XPS. Nó cho phép các nhà phát triển lập trình quyết định cách tài liệu sẽ được in, loại bỏ việc cấu hình thủ công ở phía khách hàng.

## Why add ticket support with Aspose.Page?
- **Kiểm soát chi tiết:** Đặt sắp xếp, số bản sao, loại media và nhiều hơn nữa từ mã.  
- **Tính nhất quán đa nền tảng:** Ticket giống nhau hoạt động trên bất kỳ máy in nào hiểu metadata XPS.  
- **Tích hợp liền mạch:** Hoạt động trực tiếp với các dự án .NET hiện có mà không cần dịch vụ bổ sung.

## Prerequisites

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- Kiến thức cơ bản về C# và phát triển .NET.  
- Visual Studio (bất kỳ phiên bản mới nào) đã được cài đặt.  
- Thư viện Aspose.Page for .NET đã được thêm vào dự án.  

Nếu bạn chưa thêm thư viện, có thể tải xuống từ [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/). Để nhận hỗ trợ cộng đồng, truy cập [Aspose.Page forum](https://forum.aspose.com/c/page/39).

## Import Namespaces

Bắt đầu bằng cách nhập các namespace cung cấp các lớp XPS và metadata.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsMetadata;
using Aspose.Page.XPS.XpsModel;
using System;
using System.Drawing;
```

Bây giờ chúng ta sẽ phân tích triển khai từng bước.

## Step 1: Set up Document Directory

Xác định nơi sẽ lưu tệp XPS được tạo.

```csharp
string dir = "Your Document Directory";
```

## Step 2: Create a New XPS Document

Khởi tạo một tài liệu XPS mới sẽ chứa các trang và ticket.

```csharp
XpsDocument xDocs = new XpsDocument();
```

## Step 3: Add Custom Job Print Ticket

Đính kèm một custom job print ticket vào tài liệu. Đây là phần cốt lõi của **cách thêm ticket**—tại đây bạn chỉ định sắp xếp, số bản sao, ý định render, quản lý màu và bất kỳ cài đặt nào khác bạn cần.

```csharp
xDocs.JobPrintTicket = new JobPrintTicket(
    new PageDevModeSnaphot("SABlAGwAbABvACEAAAA="),
    new DocumentCollate(Collate.CollateOption.Collated),
    // Add other print settings as needed
);
```

> **Pro tip:** Thay thế chuỗi snapshot placeholder bằng một cấu trúc DEVMODE được mã hoá Base64 phù hợp với khả năng của máy in của bạn.

## Step 4: Save the Document

Lưu tài liệu XPS (với ticket được nhúng) vào đĩa.

```csharp
xDocs.Save(dir + "output1.xps");
```

Khi bạn mở *output1.xps* trong một trình xem hỗ trợ metadata XPS, máy in sẽ tự động áp dụng các cài đặt được định nghĩa trong ticket.

## Common Issues and Solutions

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|-----------|
| Ticket không được áp dụng | Trình xem bỏ qua metadata XPS | Sử dụng driver máy in hỗ trợ XPS print tickets hoặc trình xem như Microsoft XPS Viewer. |
| Snapshot Base64 không hợp lệ | Dữ liệu DEVMODE bị hỏng | Tạo lại snapshot từ driver máy in bằng API `GetPrinter`. |
| Thiếu quyền | Không có quyền ghi vào `dir` | Đảm bảo ứng dụng chạy với đủ quyền truy cập hệ thống tập tin. |

## Frequently Asked Questions

**Q: Tôi có thể sử dụng Aspose.Page for .NET với các framework .NET khác không?**  
A: Có, Aspose.Page hoạt động với .NET Framework, .NET Core, .NET 5/6 và các phiên bản sau.

**Q: Làm sao để lấy giấy phép tạm thời cho Aspose.Page?**  
A: Truy cập [this link](https://purchase.aspose.com/temporary-license/) để nhận giấy phép tạm thời cho Aspose.Page.

**Q: Có diễn đàn cộng đồng nào hỗ trợ Aspose.Page không?**  
A: Chắc chắn, bạn có thể tìm các thảo luận hữu ích và hỗ trợ trên [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q: Những loại media nào được hỗ trợ trong custom print tickets?**  
A: Aspose.Page hỗ trợ nhiều loại media, bao gồm giấy thường, giấy bóng và các định nghĩa media tùy chỉnh.

**Q: Có dự án mẫu nào cho Aspose.Page for .NET không?**  
A: Khám phá [documentation](https://reference.aspose.com/page/net/) để xem các dự án mẫu và đoạn mã giúp bạn bắt đầu phát triển.

## Conclusion

Chúng ta đã tìm hiểu **cách thêm ticket** vào tài liệu XPS bằng Aspose.Page cho .NET. Thực hiện các bước này, bạn có thể nhúng các hướng dẫn in phong phú trực tiếp vào tệp, cho phép kiểm soát toàn bộ quy trình in từ trong ứng dụng .NET của mình. Hãy thử nghiệm thêm các cài đặt ticket để phù hợp với môi trường in cụ thể của bạn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Page for .NET (latest stable version)  
**Author:** Aspose