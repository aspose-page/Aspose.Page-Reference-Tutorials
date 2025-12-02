---
date: 2025-12-02
description: Tìm hiểu cách thay đổi kích thước tệp EPS trong Java một cách dễ dàng
  với Aspose.Page. Hướng dẫn từng bước này chỉ cho bạn cách thay đổi kích thước EPS
  bằng điểm, inch, milimet hoặc phần trăm.
language: vi
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Cách thay đổi kích thước tệp EPS trong Java với Aspose.Page
url: /java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thay Đổi Kích Thước Tệp EPS trong Java với Aspose.Page

## Giới thiệu
Nếu bạn đang tìm kiếm một cách đáng tin cậy **cách thay đổi kích thước EPS** một cách lập trình, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng ta sẽ đi qua việc thay đổi kích thước ảnh EPS trong Java bằng thư viện Aspose.Page. Dù bạn cần tăng gấp đôi kích thước, thu nhỏ tới một kích thước cụ thể, hay làm việc với phần trăm, các bước dưới đây sẽ cho bạn kiểm soát hoàn toàn kích thước đầu ra.

## Câu trả lời nhanh
- **Thư viện nào cần thiết?** Aspose.Page for Java  
- **Tôi có thể thay đổi kích thước bằng điểm, inch hoặc milimet không?** Có – API hỗ trợ cả ba đơn vị cùng với phần trăm.  
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí hoạt động cho việc kiểm tra; cần giấy phép cho môi trường sản xuất.  
- **Phiên bản Java nào được yêu cầu?** Java 8 hoặc mới hơn.  
- **Mã có an toàn đa luồng không?** Mỗi thể hiện `PsDocument` được cô lập, vì vậy bạn có thể xử lý các tệp song song.

## Yêu cầu trước
- Java Development Kit (JDK) đã được cài đặt trên máy của bạn.  
- Aspose.Page for Java library. Bạn có thể tải xuống **[here](https://releases.aspose.com/page/java/)**.  
- Kiến thức cơ bản về lập trình Java.  

## Nhập các gói
Trong dự án Java của bạn, bao gồm các import cần thiết để làm việc với các đối tượng Aspose.Page và các luồng I/O tiêu chuẩn.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Cách Thay Đổi Kích Thước EPS Bằng Điểm
Dưới đây là một ví dụ đầy đủ, từng bước, nhân đôi kích thước của tệp EPS bằng cách sử dụng điểm làm đơn vị đo.

### Bước 1: Thiết lập luồng đầu vào
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Bước 2: Khởi tạo đối tượng `PsDocument`
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Bước 3: Trích xuất kích thước hiện tại của hình ảnh EPS
```java
Dimension oldSize = doc.extractEpsSize();
```

### Bước 4: Tạo luồng đầu ra cho tệp đã thay đổi kích thước
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Bước 5: Thay đổi kích thước và lưu EPS bằng điểm
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Cách Thay Đổi Kích Thước EPS Bằng Inch
Mẫu năm bước tương tự áp dụng; chỉ cần thay thế `Units.Points` bằng `Units.Inches` và điều chỉnh hệ số tỷ lệ theo nhu cầu.

## Cách Thay Đổi Kích Thước EPS Bằng Milimet
Một lần nữa, thực hiện các bước tương tự, đổi đơn vị thành `Units.Millimeters`. Điều này hữu ích khi bạn cần kích thước dựa trên mét cho quy trình in.

## Cách Thay Đổi Kích Thước EPS Bằng Phần Trăm
Đối với việc tỷ lệ dựa trên phần trăm, giữ đơn vị là `Units.Percent`. Nhân chiều rộng và chiều cao gốc với phần trăm mong muốn (ví dụ, `0.5` cho giảm 50 %).

## Những Sai Lầm Thường Gặp & Mẹo
- **Luôn đóng các luồng** – Trong mã sản xuất, bao bọc các luồng bằng try‑with‑resources để tránh khóa tệp.  
- **Giữ tỷ lệ khung hình** – Nhân cả chiều rộng và chiều cao với cùng một hệ số trừ khi bạn muốn gây biến dạng có chủ ý.  
- **Kiểm tra DPI** – Thay đổi kích thước không làm thay đổi DPI; nếu bạn cần DPI khác, hãy điều chỉnh riêng sau khi thay đổi kích thước.

## Kết luận
Bây giờ bạn đã biết **cách thay đổi kích thước EPS** trong Java bằng Aspose.Page, dù bạn thích dùng điểm, inch, milimet hoặc phần trăm. Tính linh hoạt này cho phép bạn tích hợp việc xử lý EPS vào các pipeline tự động, tiện ích desktop, hoặc dịch vụ phía máy chủ.

## Câu Hỏi Thường Gặp

**Q: Tôi có thể sử dụng thư viện này cho các định dạng hình ảnh khác không?**  
A: Không, Aspose.Page chỉ chuyên về các tệp PostScript và EPS.

**Q: Có bản dùng thử miễn phí cho Aspose.Page cho Java không?**  
A: Có, bạn có thể khám phá bản dùng thử miễn phí **[here](https://releases.aspose.com/)**.

**Q: Tôi có thể tìm trợ giúp và thảo luận bổ sung ở đâu?**  
A: Truy cập **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** để nhận hỗ trợ cộng đồng.

**Q: Làm thế nào tôi có thể nhận giấy phép tạm thời?**  
A: Bạn có thể lấy giấy phép tạm thời **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Có dự án mẫu nào có sẵn không?**  
A: Có, xem tài liệu **[here](https://reference.aspose.com/page/java/)**.

---

**Cập nhật lần cuối:** 2025-12-02  
**Kiểm tra với:**:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}