---
date: 2025-12-18
description: Узнайте, как добавить сетку и прозрачный прямоугольник в XPS‑документы
  Java с помощью Aspose.Page. Пошаговое руководство по эффективному сохранению XPS‑документа.
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Как добавить сетку с помощью Visual Brush в Java
url: /ru/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как добавить сетку с помощью Visual Brush в Java

## Введение
Если вы ищете **how to add grid** элементы для ваших генерируемых в Java XPS‑документов, вы попали по адресу. В этом руководстве мы покажем, как добавить сетку с помощью Visual Brush, наложить прозрачный прямоугольник и, наконец, **save XPS document** с использованием Aspose.Page Java API. К концу вы получите отшлифованное изображение, которое можно повторно использовать в отчетах, счетах‑фактурах или любом приложении, работающем с документами.

## Быстрые ответы
- **What does a Visual Brush do?** Он закрашивает определённую область переиспользуемым визуальным контентом, идеально подходит для повторяющихся узоров, таких как сетки.  
- **Can I change the grid color?** Да — измените настройки сплошного цвета кисти.  
- **How do I add a transparent rectangle on top of the grid?** Используйте `setOpacity` для пути, заполненного сплошным цветом.  
- **What method saves the file?** `doc.save(...)` записывает XPS‑файл на диск.  
- **Do I need a license?** Для использования в продакшене требуется временная или полная лицензия.

## Что такое Visual Brush Grid?
Visual Brush позволяет определить небольшую визуальную часть (шаблон сетки) и затем заполнять ею большую область. Такой подход более экономичен по памяти, чем рисовать каждую линию отдельно, и обеспечивает пиксель‑точное повторение.

## Почему использовать Aspose.Page для этой задачи?
- **Cross‑platform** – Работает на любой ОС, поддерживающей Java.  
- **High‑fidelity rendering** – Точный контроль над цветами, непрозрачностью и заполнением.  
- **No external dependencies** – Всё обрабатывается через библиотеку Aspose.Page.

## Предварительные требования
Прежде чем мы начнём, убедитесь, что у вас есть:

- Базовые знания программирования на Java.  
- Установленная библиотека Aspose.Page – её можно скачать из [документации Aspose.Page для Java](https://reference.aspose.com/page/java/).  
- JDK 8 или новее, установленный на вашей машине разработки.

## Импорт пакетов
Сначала импортируйте необходимые классы, чтобы компилятор знал, где искать используемые типы:

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## Пошаговое руководство

### Шаг 1: Настройте ваш проект
Создайте новый экземпляр `XpsDocument` и укажите папку, в которой будет сохранён выходной файл.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Шаг 2: Создайте визуальную кисть сетки Magenta
Мы определяем небольшую форму magenta, которая будет заполнять область сетки.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Шаг 3: Определите геометрию для кисти сетки
Настройте прямоугольную область, которая будет принимать заполняемый визуальный шаблон.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Шаг 4: Создайте новый холст для документа
Добавьте холст в документ и разместите его там, где будет отображаться сетка.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Шаг 5: Добавьте сетку на холст
Примените визуальную кисть к геометрии, включив заполнение.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Шаг 6: Добавьте прозрачный красный прямоугольник (вторичная функция)
Здесь мы демонстрируем **add transparent rectangle** поверх сетки для акцента.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Шаг 7: Сохраните полученный XPS‑документ
Наконец, запишите документ на диск — это шаг **save XPS document**.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

Следуйте этим шагам, и у вас будет профессионально выглядящая сетка с прозрачным наложением, полностью сгенерированная программно.

## Распространённые проблемы и советы
- **Incorrect tile size:** Убедитесь, что `Rectangle2D`, используемый для кисти, соответствует требуемому размеру повторения; иначе узор может растянуться.  
- **Opacity not applied:** Не забудьте вызвать `setOpacity` для пути, который должен быть прозрачным; это не повлияет на саму кисть.  
- **File not saved:** Проверьте, что `dataDir` указывает на существующую папку и что ваше приложение имеет права записи.

## Часто задаваемые вопросы

**Q: Подходит ли Aspose.Page для профессиональной генерации документов?**  
A: Да, Aspose.Page — надёжная библиотека, разработанная для создания XPS и PDF высокого качества на Java.

**Q: Можно ли настроить цвета сетки с помощью Visual Brush?**  
A: Конечно! Измените параметры `createColor` в вызове `setFill` кисти на любые нужные вам значения RGBA.

**Q: Где я могу найти дополнительную поддержку для Aspose.Page?**  
A: Посетите [форум Aspose.Page](https://forum.aspose.com/c/page/39) для помощи сообщества и официальных ответов.

**Q: Доступна ли бесплатная пробная версия Aspose.Page?**  
A: Да, вы можете воспользоваться [бесплатной пробной версией](https://releases.aspose.com/), чтобы изучить все функции перед покупкой.

**Q: Как получить временную лицензию для тестирования?**  
A: Получите [временную лицензию](https://purchase.aspose.com/temporary-license/), которая подходит для разработки и оценки.

---

**Последнее обновление:** 2025-12-18  
**Тестировано с:** Aspose.Page for Java 23.12 (latest)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}