---
date: 2026-02-07
description: 了解如何在 Java 中調整 EPS 檔案大小，並使用 Aspose.Page 更改 EPS 尺寸。本分步指南將向您展示如何使用點、英吋、毫米或百分比來調整
  EPS 大小。
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: 如何在 Java 中使用 Aspose.Page 調整 EPS 檔案大小
url: /zh-hant/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.Page 調整 EPS 檔案大小

## 介紹
如果你正在尋找一種可靠的 **how to resize EPS** 檔案的程式化方式，你來對地方了。在本教學中，我們將示範如何使用 Aspose.Page 函式庫在 Java 中調整 EPS 圖片的大小。無論你需要將尺寸加倍、縮小至特定尺寸，或是以百分比方式調整，下列步驟都能讓你完整掌控輸出尺寸。了解 **how to resize eps** 在需要為不同列印版面或螢幕解析度調整圖形時相當重要。

## 快速回答
- **需要哪個函式庫？** Aspose.Page for Java  
- **可以使用點、英吋或毫米來調整大小嗎？** 可以——API 支援這三種單位以及百分比。  
- **開發時需要授權嗎？** 免費試用版可用於測試；正式上線需購買授權。  
- **需要哪個 Java 版本？** Java 8 或更新版本。  
- **程式碼是執行緒安全的嗎？** 每個 `PsDocument` 實例彼此獨立，可平行處理檔案。  

## EPS 是什麼，為什麼要調整它？
Encapsulated PostScript (EPS) 是出版與印刷常用的向量圖形格式。有時原始 EPS 檔的尺寸與目標輸出不符——例如，設計為 72 pts 的商標可能需要在較大的宣傳冊中使用 144 pts。了解 **how to resize eps** 能讓你在保持向量品質的同時，依工作流程調整尺寸。

## 為什麼選擇 Aspose.Page 來調整 EPS？
- **完整單位控制**——點、英吋、毫米或百分比。  
- **無外部相依性**——純 Java API，無需本機函式庫。  
- **高效能**——適合在伺服器上批次處理。  
- **保留向量忠實度**——輸出仍保持可縮放，無光柵化。

## 前置條件
在開始撰寫程式碼之前，請確保已具備以下項目：

- 已在電腦上安裝 Java Development Kit (JDK)。  
- Aspose.Page for Java 函式庫。你可以在 **[此處](https://releases.aspose.com/page/java/)** 下載。  
- 基本的 Java 程式設計概念。  

## 匯入套件
在 Java 專案中加入必要的匯入，以便使用 Aspose.Page 物件與標準 I/O 串流。

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## 如何以不同單位變更 EPS 尺寸
函式庫允許你 **change eps dimensions**，只要選擇適當的 `Units` 列舉即可。以下示範點、英吋、毫米與百分比的相同五步驟模式。唯一需要變更的，就是傳遞給 `resizeEps` 的單位。

## 如何使用點 (Points) 調整 EPS 大小
以下是一個完整的逐步範例，示範如何以點為測量單位將 EPS 檔案大小加倍。

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

### 步驟 4：為調整後的檔案建立輸出串流
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### 步驟 5：使用點單位調整大小並儲存 EPS
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## 如何使用英吋 (Inches) 調整 EPS 大小
相同的五步驟模式仍然適用，只要將 `Units.Points` 改為 `Units.Inches`，並將縮放因子調整為目標英吋值即可。

## 如何使用毫米 (Millimeters) 調整 EPS 大小
同樣遵循上述步驟，將單位換成 `Units.Millimeters`。這在需要以公制單位進行列印工作流程時相當方便。

## 如何使用百分比 (Percent) 調整 EPS 大小
若以百分比方式縮放，保持單位為 `Units.Percent`。將原始寬高乘以所需的百分比（例如 `0.5` 代表縮小 50 %）。

## 常見問題與技巧
- **務必關閉串流**——在正式程式碼中，使用 try‑with‑resources 包裝串流，以避免檔案被鎖定。  
- **保持長寬比**——除非刻意要變形，否則寬度與高度應使用相同的縮放因子。  
- **檢查 DPI**——調整大小不會改變 DPI；若需不同 DPI，請在調整後另行設定。  
- **執行緒安全**——每個執行緒建立自己的 `PsDocument`；共用同一實例可能導致不可預期的結果。  

## 常見問答

**Q: 這個函式庫可以用於其他影像格式嗎？**  
A: 不行，Aspose.Page 僅專注於 PostScript 與 EPS 檔案。

**Q: Aspose.Page for Java 有提供免費試用嗎？**  
A: 有，你可以在 **[此處](https://releases.aspose.com/)** 取得免費試用版。

**Q: 哪裡可以找到更多協助與討論？**  
A: 前往 **[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)** 取得社群支援。

**Q: 如何取得臨時授權？**  
A: 你可以在 **[此處](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

**Q: 有範例專案可以參考嗎？**  
A: 有，請參閱文件 **[此處](https://reference.aspose.com/page/java/)**。

---

**最後更新日期：** 2026-02-07  
**測試環境：** Aspose.Page for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}