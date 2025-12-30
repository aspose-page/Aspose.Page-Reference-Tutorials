---
date: 2025-12-30
description: Узнайте, как создать XPS‑документ в Java, добавляя прямоугольники с помощью
  Aspose.Page. Следуйте этому пошаговому руководству для беспроблемного управления
  XPS‑документами.
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: Создание XPS‑документа в Java – Добавление прямоугольника с Aspose.Page
url: /ru/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание XPS Document Java – Добавление прямоугольника

## Introduction
В этом полном руководстве вы **создадите XPS Document Java** файлы и научитесь добавлять прямоугольники с помощью библиотеки Aspose.Page. Независимо от того, создаёте ли вы отчёты, счета‑фактуры или пользовательскую графику, освоение создания прямоугольников даёт точный контроль над разметкой XPS. Мы пройдём каждый шаг, объясним причины каждой строки кода и покажем, как настраивать цвета и обводки для профессионального результата.

## Quick Answers
- **What library is recommended?** Aspose.Page for Java  
- **How long does the implementation take?** About 10 minutes for a basic rectangle  
- **Do I need a license?** A free trial works for development; a commercial license is required for production  
- **Which Java version is supported?** Java 8 and later  
- **Can I add multiple shapes?** Yes – repeat the steps for each shape

## Prerequisites
Перед тем как приступить, убедитесь, что у вас есть:

- Базовые знания языка программирования Java.  
- Установлена библиотека Aspose.Page. Если нет, её можно скачать из [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
- Рабочая среда разработки Java (IDE, JDK и Maven/Gradle, если вы их используете).

## Import Packages
Чтобы начать, импортируйте необходимые пакеты в ваш Java‑проект. Убедитесь, что библиотека Aspose.Page правильно добавлена в classpath. Ниже приведён базовый пример:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Теперь разберём пример на несколько шагов, чтобы добавить прямоугольник в Java XPS.

## Step 1: Set the Document Directory
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

Замените `"Your Document Directory"` на путь к папке, в которой вы хотите хранить XPS‑файлы.

## Step 2: Create a New XPS Document
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Эта строка **создаёт** новый XPS‑документ, который позже можно заполнить фигурами, текстом или изображениями.

## Step 3: Add a CMYK Solid Color Stroked Rectangle
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

Этот шаг добавляет обведённый прямоугольник с сплошным цветом CMYK. Вы можете изменить строку геометрии (`"M 20,10 L 220,10 220,100 20,100 Z"`) для изменения размера или положения и скорректировать значения цвета в `createColor` под ваш дизайн.

## Step 4: Save the Resultant XPS Document
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

Наконец, сохраните изменённый XPS‑документ с добавленным прямоугольником в директорию, указанную ранее.

## Common Use Cases
- **Report headers** – Используйте прямоугольники как фоновые блоки для заголовков.  
- **Invoice tables** – Выделяйте ячейки или секции цветными границами.  
- **Custom graphics** – Комбинируйте несколько прямоугольников для создания сложных фигур.

## Troubleshooting Tips
- **File not found error:** Проверьте, что `dataDir` указывает на существующую папку и что ICC‑профиль (`uswebuncoated.icc`) присутствует.  
- **Incorrect colors:** Убедитесь, что ICC‑профиль соответствует цветовой модели, которую вы собираетесь использовать (CMYK vs. RGB).  
- **Unexpected dimensions:** Отрегулируйте строку геометрии, чтобы отразить правильные координаты.

## Conclusion
Поздравляем! Вы успешно научились **создавать XPS Document Java** файлы и добавлять прямоугольники с помощью Aspose.Page. Эта база позволяет создавать более насыщенные XPS‑документы, настраивать графику и интегрировать фигуры в более крупные рабочие процессы.

## FAQs
### Can I add multiple rectangles in a single XPS document?
Да, вы можете добавить столько прямоугольников, сколько потребуется, повторяя шаги, описанные в руководстве.

### How can I change the color of the rectangle?
Измените значения цвета в методе `createColor`, чтобы получить нужный оттенок.

### Is Aspose.Page suitable for handling complex XPS document manipulations?
Определённо! Aspose.Page предоставляет мощный набор функций для работы с различными задачами XPS‑документов.

### Where can I find additional examples and support?
Исследуйте [Aspose.Page forum](https://forum.aspose.com/c/page/39) для получения дополнительных примеров и обратитесь за помощью к сообществу.

### Can I try Aspose.Page before purchasing?
Да, вы можете воспользоваться [free trial](https://releases.aspose.com/) для ознакомления с возможностями Aspose.Page.

## Frequently Asked Questions

**Q: Does this approach work with Java 11 or newer?**  
A: Yes, the Aspose.Page library is compatible with Java 8 and later, including Java 11, 17, and beyond.

**Q: Can I embed images inside the rectangle area?**  
A: You can add an `XpsImage` element and position it over or inside the rectangle using the same geometry coordinates.

**Q: How do I set a fill color instead of just a stroke?**  
A: Call `path.setFill(...)` with a solid color brush created via `doc.createSolidColorBrush(...)`.

**Q: Is it possible to rotate the rectangle?**  
A: Apply a transformation matrix to the path using `path.setTransform(...)` to achieve rotation or scaling.

**Q: What licensing is required for production use?**  
A: A commercial Aspose.Page license is required for deployment; the free trial is limited to evaluation and development.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-30  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

---