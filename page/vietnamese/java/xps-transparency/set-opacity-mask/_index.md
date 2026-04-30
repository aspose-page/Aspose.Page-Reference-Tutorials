---
date: 2026-04-30
description: Tìm hiểu cách tạo tài liệu XPS bằng Java và thêm mặt nạ độ trong suốt
  bằng Aspose.Page Java. Hướng dẫn chi tiết từng bước kèm ví dụ mã.
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: Thiết lập mặt nạ độ trong suốt trong Java XPS
second_title: Aspose.Page Java API
title: Tạo tài liệu XPS Java – Đặt mặt nạ độ trong suốt với Aspose.Page
url: /vi/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thiết lập Mặt nạ Độ trong suốt trong Java XPS bằng Aspose.Page Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ **tạo tệp tài liệu XPS Java** và học cách áp dụng một mặt nạ độ trong suốt giúp đồ họa của bạn trông mịn màng, bán trong suốt. Chúng tôi sẽ hướng dẫn toàn bộ quy trình — từ khởi tạo tài liệu XPS, thêm canvas, vẽ hình chữ nhật, đến gắn mặt nạ độ trong suốt dựa trên hình ảnh — bằng API trực quan của Aspose.Page Java. Khi hoàn thành, bạn sẽ có thể tạo các tệp XPS chuyên nghiệp một cách lập trình và tái sử dụng mặt nạ trên bất kỳ hình dạng nào bạn cần.

## Câu trả lời nhanh
- **Mặt nạ độ trong suốt làm gì?** Nó xác định các mức độ trong suốt khác nhau cho một hình dạng, cho phép nội dung phía dưới hiển thị.  
- **Thư viện nào được yêu cầu?** Aspose.Page cho Java (aspose page java).  
- **Tôi có cần giấy phép không?** Giấy phép tạm thời hoạt động cho việc thử nghiệm; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Có bao nhiêu dòng mã?** Khoảng 20 dòng Java cộng với một vài câu lệnh thiết lập.  
- **Tôi có thể tái sử dụng mặt nạ trên nhiều hình dạng không?** Có, bạn có thể gán cùng một `ImageBrush` cho nhiều đường dẫn.

## Mặt nạ Độ trong suốt trong XPS là gì?
Mặt nạ độ trong suốt là một bitmap hoặc vector kiểm soát alpha (độ trong suốt) của mỗi pixel trong một hình dạng. Khi được áp dụng cho một hình chữ nhật, các phần của hình chữ nhật sẽ trở nên hoàn toàn không trong suốt, bán trong suốt hoặc hoàn toàn trong suốt, tạo ra các hiệu ứng hình ảnh tinh vi mà không cần lớp vẽ bổ sung.

## Tại sao nên dùng Aspose.Page Java để **tạo tài liệu XPS java**?
- **API thuần Java** – Không phụ thuộc vào native, vì vậy cùng một đoạn mã chạy được trên Windows, Linux hoặc macOS.  
- **Tuân thủ đầy đủ chuẩn XPS** – Mặt nạ được hiển thị chính xác như định nghĩa trong tiêu chuẩn XPS.  
- **Thiết kế hướng đối tượng** – Giống .NET, dễ tiếp cận nếu bạn đã dùng Aspose trong các ngôn ngữ khác.  
- **Hiệu năng cao** – Tối ưu cho tài liệu lớn và xử lý hàng loạt.

## Các trường hợp sử dụng phổ biến
- **Đánh dấu bản quyền** – Áp dụng logo bán trong suốt trên toàn bộ trang.  
- **Thay đổi giao diện động** – Thay đổi phong cách trực quan của các thành phần UI trong báo cáo được tạo tự động.  
- **Xem trước bản in** – Hiển thị thiết kế với các mức độ trong suốt khác nhau trước khi gửi tới máy in.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:
- Kiến thức cơ bản về lập trình Java.  
- Thư viện Aspose.Page cho Java đã được cài đặt. Bạn có thể tải xuống **[tại đây](https://releases.aspose.com/page/java/)**.  
- Giấy phép hợp lệ cho Aspose.Page. Nếu chưa có, hãy lấy giấy phép tạm thời **[tại đây](https://purchase.aspose.com/temporary-license/)**.  
- Môi trường phát triển có khả năng biên dịch và chạy ứng dụng Java (ví dụ: IntelliJ IDEA, Eclipse hoặc VS Code).

## Nhập khẩu các gói
Bắt đầu bằng cách nhập các lớp cần thiết từ thư viện Aspose.Page. Điều này sẽ đảm bảo API có sẵn cho dự án của bạn.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Hướng dẫn từng bước

### Bước 1: Tạo tài liệu XPS mới
Đầu tiên, khởi tạo một tài liệu XPS mới sẽ chứa tất cả các đồ họa của chúng ta.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Bước 2: Thêm Canvas
Canvas hoạt động như một bề mặt vẽ bên trong trang XPS.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Bước 3: Thêm hình chữ nhật và áp dụng màu nền đặc
Ở đây chúng ta tạo một đường dẫn hình chữ nhật và gán cho nó màu nền đỏ đặc. Hình chữ nhật này sẽ nhận mặt nạ độ trong suốt sau này.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Bước 4: Thêm Mặt nạ Độ trong suốt bằng ImageBrush
Chúng ta tải ảnh TIFF, xác định các hình chữ nhật nguồn và đích, và đặt brush ở chế độ lặp lại để mặt nạ lặp lại nếu cần.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Bước 5: Lưu tài liệu XPS đã tạo
Cuối cùng, ghi tài liệu ra đĩa. Tệp đầu ra sẽ chứa hình chữ nhật với mặt nạ độ trong suốt đã được áp dụng.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Thực hiện các bước này một cách cẩn thận để tích hợp chức năng **thêm mặt nạ độ trong suốt** vào tài liệu Java XPS của bạn bằng Aspose.Page.

## Các vấn đề thường gặp & Khắc phục
- **Không tìm thấy ảnh** – Kiểm tra lại `dataDir` trỏ đúng thư mục và `R08SY_NN.tif` tồn tại.  
- **Mặt nạ hiển thị đầy màu** – Đảm bảo ảnh nguồn thực sự chứa các giá trị alpha khác nhau; ảnh hoàn toàn không trong suốt sẽ không hiển thị hiệu ứng.  
- **Chế độ lặp không hoạt động** – Hình chữ nhật đích phải nhỏ hơn hình chữ nhật nguồn để việc lặp được nhận thấy.

## Câu hỏi thường gặp

**H: Aspose.Page có tương thích với mọi môi trường phát triển Java không?**  
Đ: Có, Aspose.Page được thiết kế để hoạt động liền mạch với nhiều IDE và công cụ xây dựng Java.

**H: Tôi có thể dùng Aspose.Page mà không có giấy phép không?**  
Đ: Bạn có thể đánh giá thư viện bằng giấy phép tạm thời, nhưng giấy phép đầy đủ là bắt buộc cho môi trường sản xuất.

**H: Phiên bản dùng thử có giới hạn gì không?**  
Đ: Bản dùng thử có thể áp đặt giới hạn về kích thước hoặc tính năng; hãy tham khảo tài liệu chính thức để biết chi tiết.

**H: Làm sao tôi có thể nhận hỗ trợ cho Aspose.Page?**  
Đ: Truy cập **[diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39)** để nhận trợ giúp cộng đồng hoặc mua giấy phép để được hỗ trợ cao cấp.

**H: Có bảo đảm hoàn tiền cho Aspose.Page không?**  
Đ: Tham khảo **[trang mua hàng](https://purchase.aspose.com/buy)** để biết chính sách hoàn trả.

---

**Cập nhật lần cuối:** 2026-04-30  
**Đã kiểm tra với:** Aspose.Page Java 24.11 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}