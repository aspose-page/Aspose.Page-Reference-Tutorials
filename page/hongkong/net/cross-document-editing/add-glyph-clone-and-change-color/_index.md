---
date: 2026-01-07
description: 學習如何建立 XPS 文件、加入字形複本、使用純色筆刷，並使用 Aspose.Page for .NET 儲存 XPS 檔案。
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
title: 建立 XPS 文件 – 使用 Aspose.Page for .NET 新增字形複本並變更顏色
url: /zh-hant/net/cross-document-editing/add-glyph-clone-and-change-color/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 XPS 文件 – 新增字形複製與變更顏色，使用 Aspose.Page for .NET

## 介紹

歡迎閱讀本步驟指南，向您展示 **如何建立 XPS 文件**、複製字形以及使用 Aspose.Page for .NET 變更其顏色。無論您是建立動態報表、發票或自訂圖形，掌握這些技巧都能讓您在不離開 .NET 生態系統的情況下產生視覺豐富的 XPS 輸出。

## 快速解答
- **主要目標是什麼？** 建立 XPS 文件、加入字形複製，並變更其顏色。  
- **使用哪個函式庫？** Aspose.Page for .NET。  
- **需要授權嗎？** 可取得暫時授權供評估使用；正式環境需購買完整授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **如何儲存結果？** 使用 `Save` 方法將 XPS 檔寫入磁碟。

## 前置條件

在開始本教學之前，請確保您具備以下前置條件：

- 具備 C# 程式語言的基礎了解。  
- 已安裝 Visual Studio 或其他您偏好的 C# 開發環境。  
- Aspose.Page for .NET 函式庫。您可於[此處](https://releases.aspose.com/page/net/)下載。  
- 熟悉 XPS 文件格式。

## 匯入命名空間

開始之前，請在 C# 專案中加入必要的命名空間：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 如何建立 XPS 文件並新增字形複製

### 步驟 1：設定文件目錄

首先設定儲存文件的目錄：

```csharp
string dataDir = "Your Document Directory";
```

### 步驟 2：建立第一個 XPS 文件

現在，讓我們建立第一個 XPS 文件：

```csharp
XpsDocument doc1 = new XpsDocument();
```

### 步驟 3：將字形加入第一個文件

使用指定參數將字形加入第一個文件：

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### 步驟 4：以實心顏色筆刷填充字形

以 **實心顏色筆刷** 為第一個文件中的字形填色，例如綠色：

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### 步驟 5：建立第二個 XPS 文件

現在，建立第二個 XPS 文件：

```csharp
XpsDocument doc2 = new XpsDocument();
```

### 步驟 6：如何將字形複製加入另一個文件

從第一個文件複製字形，並將其加入第二個文件：

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### 步驟 7：如何變更複製字形的顏色

在第二個文件中變更複製字形的顏色，例如改為紅色。此示範 **如何在複製後變更字形顏色**：

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### 步驟 8：儲存 XPS 檔案 – 第一個文件

將第一個 XPS 文件儲存至先前定義的資料夾：

```csharp
doc1.Save(dataDir + "out1.xps");
```

### 步驟 9：儲存 XPS 檔案 – 第二個文件

儲存第二個 XPS 文件：

```csharp
doc2.Save(dataDir + "out2.xps");
```

恭喜！您已成功 **建立 XPS 文件**、加入字形複製，並使用 Aspose.Page for .NET 變更其顏色。

## 為何使用字形複製與顏色變更？

- **可重用性：** 複製現有字形以重用複雜向量形狀，無需重新定義。  
- **效能：** 相較於從頭重新建立字形，可減少處理時間。  
- **設計彈性：** 為同一字形套用不同的 `SolidColorBrush` 實例，以實現多樣的視覺主題。  
- **跨文件編輯：** 在多個 XPS 檔案之間複製字形，確保報表的品牌形象一致。

## 常見問題與疑難排解

| 問題 | 解決方案 |
|-------|----------|
| **Clone 回傳 null** | 確保來源字形 (`glyphs`) 已加入第一個文件後再執行複製。 |
| **顏色未變更** | 在設定 `Color` 屬性之前，先將 `glyphs.Fill` 轉型為 `XpsSolidColorBrush`（如第 7 步所示）。 |
| **檔案未儲存** | 確認 `dataDir` 指向有效且可寫入的資料夾，且您具備相應的檔案系統權限。 |
| **字形尺寸異常** | 調整字型大小參數（`AddGlyphs` 的第二個參數）以正確縮放字形。 |

## 常見問答

**Q1：我可以將 Aspose.Page for .NET 用於其他文件格式嗎？**  
A1：Aspose.Page for .NET 專為 XPS 文件設計。若需處理其他格式，您可以探索針對那些格式的其他 Aspose 函式庫。

**Q2：是否提供 Aspose.Page for .NET 的暫時授權？**  
A2：是的，您可取得暫時授權以進行測試。請前往[此處](https://purchase.aspose.com/temporary-license/)了解更多資訊。

**Q3：我該如何取得支援或尋求協助？**  
A3：歡迎造訪 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 與社群交流並取得協助。

**Q4：免費試用版有什麼限制嗎？**  
A4：免費試用版存在一些限制，建議在使用前先查閱文件以了解詳細資訊。

**Q5：在哪裡可以找到 Aspose.Page for .NET 的完整文件？**  
A5：您可於[此處](https://reference.aspose.com/page/net/)參考文件，取得詳細資訊與範例。

**Q6：如何變更字形的描邊顏色而非填充顏色？**  
A6：使用 `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);` 來設定描邊筆刷。

**Q7：我可以在同一文件中加入多個字形複製嗎？**  
A7：可以，重複呼叫 `doc2.Add(glyphs.Clone());`，並依需求調整位置。

---

**最後更新：** 2026-01-07  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}