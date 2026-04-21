---
date: 2026-01-02
description: Tìm hiểu cách thêm mặt nạ độ trong suốt vào tài liệu XPS bằng Aspose.Page
  Java. Hướng dẫn từng bước để tạo hình chữ nhật mặt nạ độ trong suốt và nâng cao
  chất lượng hình ảnh.
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: Thiết lập mặt nạ độ trong suốt trong Java XPS bằng Aspose.Page Java
url: /vi/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt Mặt Nạ Độ Trong suốt trong Java XPS bằng Aspose.Page Java

## Giới thiệu
Chào mừng bạn đến với hướng dẫn toàn diện của chúng tôi về **aspose page java** mặt nạ độ trong suốt. Trong tutorial này bạn sẽ học cách tạo tài liệu XPS, thêm canvas, và áp dụng mặt nạ độ trong suốt lên một hình chữ nhật — tất cả đều bằng API mạnh mẽ của Aspose.Page Java. Khi kết thúc, bạn sẽ có thể thêm các hình chữ nhật có mặt nạ độ trong suốt giúp các tệp XPS của bạn trông bóng bẩy, bán trong suốt.

## Câu trả lời nhanh
- **Mặt nạ độ trong suốt làm gì?** Nó định nghĩa các mức độ trong suốt thay đổi cho một hình dạng, cho phép nội dung bên dưới hiển thị qua.
- **Thư viện nào được yêu cầu?** Aspose.Page for Java (aspose page java).
- **Tôi có cần giấy phép không?** Giấy phép tạm thời hoạt động cho việc thử nghiệm; giấy phép đầy đủ cần thiết cho môi trường sản xuất.
- **Có bao nhiêu dòng mã?** Khoảng 20 dòng Java cộng với một vài câu lệnh thiết lập.
- **Tôi có thể tái sử dụng mặt nạ cho nhiều hình dạng không?** Có, bạn có thể gán cùng một ImageBrush cho nhiều đường.

## Mặt nạ độ trong suốt trong XPS là gì?
Mặt nạ độ trong suốt là một bitmap hoặc vector kiểm soát alpha (độ trong suốt) của mỗi pixel trong một hình dạng. Khi được áp dụng lên một hình chữ nhật, các phần của hình chữ nhật sẽ trở nên hoàn toàn không trong suốt, một phần trong suốt, hoặc hoàn toàn trong suốt, tạo ra các hiệu ứng hình ảnh tinh vi.

## Tại sao nên sử dụng Aspose.Page Java cho mặt nạ độ trong suốt?
- **Full .NET‑style API in Java** – mô hình đối tượng trực quan.  
- **No external dependencies** – hoạt động với Java thuần.  
- **High‑fidelity rendering** – mặt nạ được render chính xác như trong đặc tả XPS.  
- **Cross‑platform** – chạy trên Windows, Linux hoặc macOS mà không cần thay đổi.

## Yêu cầu trước
- Kiến thức cơ bản về lập trình Java.  
- Thư viện Aspose.Page for Java đã được cài đặt. Bạn có thể tải xuống **[here](https://releases.aspose.com/page/java/)**.  
- Giấy phép hợp lệ cho Aspose.Page. Nếu bạn chưa có, hãy lấy giấy phép tạm thời **[here](https://purchase.aspose.com/temporary-license/)**.  
- Môi trường phát triển có khả năng biên dịch và chạy các ứng dụng Java (ví dụ: IntelliJ IDEA, Eclipse, hoặc VS Code).

## Nhập các gói
Bắt đầu bằng cách nhập các lớp cần thiết từ thư viện Aspose.Page. Điều này đảm bảo API có sẵn cho dự án của bạn.

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
Đầu tiên, khởi tạo một tài liệu XPS mới sẽ chứa tất cả đồ họa của chúng ta.

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
Ở đây chúng ta tạo một đường hình chữ nhật và gán cho nó màu nền đỏ đặc. Hình chữ nhật này sau này sẽ nhận mặt nạ độ trong suốt.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Bước 4: Thêm mặt nạ độ trong suốt bằng ImageBrush
Chúng ta tải một ảnh TIFF, định nghĩa các hình chữ nhật nguồn và đích, và đặt brush ở chế độ tile để mặt nạ lặp lại nếu cần.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Bước 5: Lưu tài liệu XPS kết quả
Cuối cùng, lưu tài liệu vào đĩa. Tệp đầu ra sẽ chứa hình chữ nhật với mặt nạ độ trong suốt đã được áp dụng.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Thực hiện cẩn thận các bước này để tích hợp chức năng **add opacity mask** vào tài liệu Java XPS của bạn bằng Aspose.Page.

## Các vấn đề thường gặp & Khắc phục
- **Image not found** – Kiểm tra `dataDir` trỏ tới thư mục đúng và `R08SY_NN.tif` tồn tại.  
- **Mask appears solid** – Đảm bảo ảnh nguồn thực sự chứa các giá trị alpha thay đổi; ảnh hoàn toàn không trong suốt sẽ không hiển thị độ trong suốt.  
- **Tile mode not respected** – Hình chữ nhật đích phải nhỏ hơn hình chữ nhật nguồn để việc lặp lại (tiling) có thể nhận thấy.

## Câu hỏi thường gặp

**Q: Aspose.Page có tương thích với mọi môi trường phát triển Java không?**  
A: Có, Aspose.Page được thiết kế để hoạt động liền mạch với nhiều IDE Java và công cụ xây dựng.

**Q: Tôi có thể sử dụng Aspose.Page mà không có giấy phép không?**  
A: Mặc dù bạn có thể đánh giá thư viện bằng giấy phép tạm thời, nhưng giấy phép đầy đủ là cần thiết cho việc sử dụng trong môi trường sản xuất.

**Q: Có bất kỳ hạn chế nào trên phiên bản dùng thử không?**  
A: Phiên bản dùng thử có thể áp đặt giới hạn về kích thước hoặc tính năng; hãy tham khảo tài liệu chính thức để biết chi tiết.

**Q: Làm thế nào tôi có thể nhận hỗ trợ cho Aspose.Page?**  
A: Truy cập **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** để nhận trợ giúp cộng đồng hoặc mua giấy phép để được hỗ trợ cao cấp.

**Q: Có bảo đảm hoàn tiền cho Aspose.Page không?**  
A: Tham khảo **[purchase page](https://purchase.aspose.com/buy)** để biết thông tin về chính sách hoàn trả.

---

**Last Updated:** 2026-01-02  
**Tested With:** Aspose.Page Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}