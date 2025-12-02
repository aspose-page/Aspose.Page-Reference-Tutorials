---
date: 2025-12-02
description: 學習如何在 Java 中使用 Aspose.Page 輕鬆調整 EPS 檔案大小。本分步指南將示範如何以點、英吋、毫米或百分比來調整 EPS
  的尺寸。
language: zh-hant
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: 如何在 Java 中使用 Aspose.Page 調整 EPS 檔案大小
url: /java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.Page 調整 EPS 檔案大小

## 簡介
如果您正在尋找可靠的 **如何調。在本教學中，我們將示範如何使用 Aspose.Page 函式庫在 Java 中調整 EPS 圖片大小。無論您需要將尺寸加倍、縮小至特定尺寸，或是使用百分比，以下步驟都能讓您完整掌控輸出尺寸。

## 快速答覆
- **需要哪個函式庫？** Aspose.Page for Java  
- **我可以使用點、英吋或毫米來調整大小嗎？** 可以 – API 支援這三種單位以及百分比。  
- **開發時需要授權嗎？** 免費試用可用於測試；正式環境需要授權。  
- **需要哪個 Java 版本？** Java 8 或更新版本。  
- **程式碼是執行緒安全的嗎？** 每個 `PsDocument` 實例是獨立的，因此可以平行處理檔案。

## 先決條件
在深入程式碼之前，請確保您具備以下項目：

- 已在機器上安裝 Java Development Kit (JDK)。  
- Aspose.Page for Java 函式庫。您可於 **[此處](https://releases.aspose.com/page/java/)** 下載。  
- 具備基本的 Java 程式設計概念。  

## 匯入套件
在您的 Java 專案中，加入必要的匯入，以便使用 Aspose.Page 物件與標準 I/O 串流。

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## 如何使用點 (Points) 調整 EPS 大小
以下是一個完整的逐步範例，示範如何使用點作為測量單位將 EPS 檔案大小加倍。

### 步驟 1：設定輸入串流
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### 步驟 2：初始化 `PsDocument` 物件
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### 步驟 3：取得 EPS 圖片的目前尺寸
```java
Dimension oldSize = doc.extractEpsSize();
```

### 步驟 4：為調整大小後的檔案建立輸出串流
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### 步驟 5：使用點單位調整大小並儲存 EPS
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## 如何使用英吋 (Inches) 調整 EPS 大小
相同的五步流程仍然適用；只需將 `Units.Points` 換成 `Units.Inches`，並依需求調整縮放係數。

## 如何使用毫米 (Millimeters) 調整 EPS 大小
同樣遵循相同步驟，將單位改為 `Units.Millimeters`。當您需要以公制為基礎的列印尺寸時，這非常方便。

## 如何使用百分比 (Percent) 調整 EPS 大小
若使用百分比縮放，保持單位為 `Units.Percent`。將原始寬度與高度乘以目標百分比（例如 `0.5` 代表縮小 50 %）。

## 常見問題與技巧
- **務必關閉串流** – 在正式程式碼中，使用 try‑with‑resources 包裝串流，以避免檔案鎖定。  
- **保持長寬比** – 除非刻意要產生變形，否則寬度與高度應以相同係數相乘。  
- **檢查 DPI** – 調整大小不會改變 DPI；若需不同 DPI，請在調整後另行設定。

## 結論
現在您已了解如何在 Java 中使用 Aspose.Page **調整 EPS** 檔案大小，無論是點、英吋、毫米或百分比。此彈性讓您能將 EPS 操作整合至自動化流程、桌面工具或伺服器端服務中。

## 常見問答

**Q: 我可以將此函式庫用於其他影像格式嗎？**  
A: 不行，Aspose.Page 僅專注於 PostScript 與 EPS 檔案。

**Q: Aspose.Page for Java 有提供免費試用嗎？**  
A: 有，您可於 **[此處](https://releases.aspose.com/)** 探索免費試用。

**Q: 我可以在哪裡找到更多協助與討論？**  
A: 前往 **[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)** 取得社群支援。

**Q: 如何取得臨時授權？**  
A: 您可於 **[此處](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

**Q: 有提供範例專案嗎？**  
A: 有，請參閱文件 **[此處](https://reference.aspose.com/page/java/)**。

---

**最後更新：** 2025-12-02  
**測試環境：** Aspose.Page for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}