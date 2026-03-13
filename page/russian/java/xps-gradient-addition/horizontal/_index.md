---
date: 2026-03-13
description: Узнайте, как добавить градиент в XPS‑документы на Java с помощью Aspose.Page
  и как настроить остановки градиента для впечатляющих горизонтальных эффектов.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Как добавить градиент — горизонтальный градиент в Java XPS
url: /ru/java/xps-gradient-addition/horizontal/
weight: 11
---

. Also ensure markdown formatting.

Let's write final.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как добавить градиент – горизонтальный градиент в Java XPS

## Introduction
Welcome to this step‑by‑step guide on **how to add gradient** to an XPS document using Java. In this tutorial you’ll learn how to add a horizontal gradient, why it matters for visual polish, and how to **customize gradient stops** for precise color control. Aspose.Page for Java makes working with XPS (XML Paper Specification) documents straightforward, letting you focus on design rather than low‑level file handling.

## Quick Answers
- **Какая библиотека нужна?** Aspose.Page for Java  
- **Какая версия Java поддерживается?** Any Java 8+ runtime  
- **Нужна ли лицензия?** A free trial works for development; a commercial license is required for production  
- **Можно ли изменить направление градиента?** Yes – just modify the start/end points of the linear brush  
- **Можно ли добавить несколько градиентов?** Absolutely – repeat the path creation steps with different brushes  

## What is a Horizontal Gradient in XPS?
A horizontal gradient is a smooth transition of colors from left to right across a shape. In XPS it is represented by a linear gradient brush that interpolates between defined **gradient stops**. This visual effect is commonly used for banners, buttons, and background fills.

## Why Use Aspose.Page for Java?
- **Full XPS support** – create, edit, and render without third‑party tools.  
- **Simple API** – high‑level objects like `XpsDocument`, `XpsPath`, and `XpsGradientBrush` hide the XML complexity.  
- **Performance** – optimized for large documents and batch processing.  

## Prerequisites
Before you begin, ensure you have:

1. **Среда разработки Java** – Install the latest JDK from [java.com](https://www.java.com).  
2. **Библиотека Aspose.Page for Java** – Download the JAR from the [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  

## Import Packages
Start by importing the necessary classes. These imports give you access to document creation, gradient handling, and basic geometry.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Step 1: Initialize the XPS Document
Create a fresh `XpsDocument` instance and point to the folder where you want to save the result.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Step 2: Create Horizontal Gradient
Define a list of **gradient stops** that control the color and position of each transition point. The example below builds a vibrant rainbow‑like gradient.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### How to customize gradient stops
- **Цвет** – Use `doc.createColor(alpha, red, green, blue)` to set any ARGB value.  
- **Позиция** – The second argument (`float` between `0` and `1`) defines where the stop appears along the gradient line. Adjust these values to shift colors left or right.

## Step 3: Add Path with Gradient
Create a rectangular path, apply a transform if needed, and fill it with the linear gradient brush. The brush uses two points (`(10,0)` to `(228,0)`) to produce a horizontal effect. Because the Y‑coordinates are identical, this brush acts as a **horizontal gradient brush**.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Pro tip:** Re‑using the same `stops` list for multiple paths can improve performance, but remember to `clear()` it before adding new stops.

## Step 4: Save the Document
Persist the XPS file to disk. You can now open it with any XPS viewer to see the horizontal gradient in action.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## How to Apply Multiple Gradients
If you want to **apply multiple gradients** within the same XPS document, simply repeat the “Create Horizontal Gradient” and “Add Path with Gradient” steps for each new shape. Use a fresh list of `XpsGradientStop` objects (or clear the existing list) and assign a new `LinearGradientBrush` with its own start/end points. This approach lets you layer gradients, create complex backgrounds, or highlight different UI elements in a single page.

## Why This Matters – Benefits of the Horizontal Gradient Brush
- **Визуальная глубина:** A horizontal gradient brush adds a subtle three‑dimensional feel without extra images.  
- **Эффективность размера файла:** Gradients are stored as vector definitions, keeping the XPS file lightweight.  
- **Масштабируемость:** Because the gradient is vector‑based, it scales cleanly on high‑resolution displays.  

## Common Issues & Solutions
| Проблема | Причина | Решение |
|----------|---------|----------|
| Градиент выглядит сплошным | Не добавлены градиентные остановки или кисть не установлена | Убедитесь, что `path.setFill(...)` использует `LinearGradientBrush` и что остановки добавляются через `getGradientStops().addAll(stops)`. |
| Цвета выглядят тускло | Неправильное значение альфа (первый параметр) | Используйте `255` для полностью непрозрачных цветов, если только не требуется прозрачность. |
| Размер пути неверен | Значения матрицы трансформации неверны | Отрегулируйте параметры матрицы (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Frequently Asked Questions

**Q: Can I apply multiple gradients in a single XPS document?**  
A: Yes, you can add multiple paths, each with its own gradient brush, to create complex layered designs.

**Q: Is Aspose.Page compatible with the latest Java versions?**  
A: Aspose.Page for Java is regularly updated and works with Java 8 and newer releases.

**Q: Are there other gradient types available in Aspose.Page?**  
A: Besides linear gradients, Aspose.Page also supports radial gradients for circular color transitions.

**Q: Can I customize the colors and positions of gradient stops?**  
A: Absolutely! You have full control over each stop’s ARGB color and its relative position (0‑1 range).

**Q: Is there a community forum for Aspose.Page where I can seek help?**  
A: Yes, you can visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to connect with the community and get assistance.

---

**Last Updated:** 2026-03-13  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}