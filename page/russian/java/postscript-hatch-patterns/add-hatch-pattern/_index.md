---
date: 2025-12-08
description: Изучите, как добавлять штриховки в документы Java PostScript с помощью
  Aspose.Page Java. Это пошаговое руководство покажет, как эффективно добавлять графику
  с штриховкой.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: Добавить штриховой узор в Java PostScript'
url: /ru/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавление штриховки в Java PostScript

## Введение
Если вы работаете с **Aspose.Page Java** и хотите обогатить вывод PostScript текстурированными графическими элементами, штриховка — быстрый и гибкий способ. В этом руководстве мы пройдемся по **как добавить штриховку** в документ PostScript, объясним, почему она полезна, и предоставим полностью готовый к запуску пример кода. К концу вы сможете создавать визуально привлекательные фигуры и текст, заполненные штриховкой, всего несколькими строками Java.

## Быстрые ответы
- **Какая библиотека нужна?** Aspose.Page for Java (SDK “aspose page java”).  
- **Какой визуальный эффект мы добавляем?** Штриховка (например, диагональные линии, перекрестная штриховка).  
- **Нужна ли лицензия для запуска примера?** Бесплатная пробная версия подходит для разработки; для продакшна требуется лицензия.  
- **Сколько строк кода?** Около 70 строк, разбитых на понятные шаги.  
- **Можно ли использовать тот же подход для PDF?** Да — Aspose.Page поддерживает несколько форматов вывода, включая PDF.

## Требования
- **Среда разработки Java** — JDK 8 или выше и IDE по вашему выбору.  
- **Библиотека Aspose.Page for Java** — Скачайте последнюю JAR с официального сайта [here](https://releases.aspose.com/page/java/).  
- **Права записи** в папку, где будет сохранён сгенерированный файл PostScript.

## Импорт пакетов
Сначала подключите необходимые классы к вашему проекту. Эти импорты дают доступ к примитивам рисования, работе с цветом и API Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Шаг 1: Настройка начальных параметров
Создайте поток вывода, задайте размер страницы (A4) и определите несколько переменных макета, которые будут переиспользоваться при рисовании каждого квадрата, заполненного штриховкой.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Шаг 2: Сохранение состояния графики и трансляция
Сохранение состояния графики позволяет позже вернуться к исходной системе координат, а `translate` перемещает начало координат в удобную стартовую точку.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Шаг 3: Создание квадрата для каждого шаблона
Определите переиспользуемый прямоугольник, который будет представлять каждую ячейку, заполненную штриховкой.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Шаг 4: Настройка пера для контура квадратов шаблона
`BasicStroke` толщиной 2 пункта обеспечивает чёткий контур вокруг каждого квадрата.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Шаг 5: Итерация по шаблонам штриховки
Переберите все значения перечисления `HatchStyle`, заполните каждый квадрат соответствующей текстурой и затем нарисуйте его контур. Это ядро функции **добавления штриховки**.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Шаг 6: Восстановление состояния графики
Вернитесь к исходной системе координат после завершения рисования сетки квадратов.

```java
document.writeGraphicsRestore();
```

 Шаг 7: Заполнение текста штриховкой
Здесь мы демонстрируем, как закрасить текст с помощью текстуры штриховки. Пример заполняет слово «ABC» диагонально‑перекрестным шаблоном.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Шаг 8: Обводка текста штриховкой
Теперь мы обводим тот же текст, но уже используя стиль штриховки 70 % и более толстый штрих.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Шаг 9: Закрытие и сохранение документа
Завершите страницу, запишите файл на диск и освободите ресурсы.

```java
document.closePage();
document.save();
```

Следуйте этим шагам, и у вас получится файл PostScript, демонстрирующий полный набор штриховок, применённых как к фигурам, так и к тексту — всё это работает на базе **aspose page java**.

## Почему использовать штриховку с Aspose.Page Java?
- **Визуальное различие** — Штриховка работает даже при ограничениях принтеров до монохромного вывода.  
- **Производительность** — Текстуры генерируются «на лету», поэтому вы избегаете больших файлов изображений.  
- **Поддержка кросс‑форматов** — Тот же код может генерировать PDF, EPS или SVG с минимальными изменениями.

## Распространённые подводные камни и советы
- **Ошибки пути к файлам** — Убедитесь, что `dataDir` заканчивается правильным разделителем (`/` или `\`).  
- **Неподдерживаемые цвета** — Некоторые старые интерпретаторы PostScript могут не обрабатывать определённые цветовые пространства; используйте базовый RGB для максимальной совместимости.  
- **Предупреждения о лицензии** — Запуск примера без действующей лицензии добавит водяной знак в результат.

## Заключение
Внедрение штриховки может значительно улучшить читаемость и эстетический вид технических чертежей, карт или любой графики, генерируемой на Java. С **Aspose.Page Java** вы получаете лаконичное API, которое абстрагирует низкоуровневые команды PostScript, позволяя сосредоточиться на дизайне, а не на особенностях формата файла.

## Часто задаваемые вопросы

**Q: Можно ли использовать Aspose.Page Java с другими Java‑фреймворками?**  
A: Да, библиотека независима от фреймворков и работает с Spring, Jakarta EE, Android (ограниченно) и обычным Java SE.

**Q: Доступна ли пробная версия Aspose.Page Java?**  
A: Абсолютно. Скачайте бесплатную 30‑дневную пробную версию [here](https://releases.aspose.com/).

**Q: Как получить временную лицензию для разработки?**  
A: Запросите временную лицензию [here](https://purchase.aspose.com/temporary-license/). Она удалит водяные знаки оценки.

**Q: Где можно найти больше руководств и поддержку сообщества?**  
A: Посетите официальный форум [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) для дополнительных примеров и вопросов‑ответов.

**Q: Есть ли полная документация по всем классам и методам?**  
A: Да, полная ссылка на API доступна [here](https://reference.aspose.com/page/java/).

---

**Последнее обновление:** 2025-12-08  
**Тестировано с:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Автор:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
