---
date: 2026-04-24
description: Узнайте, как создать XPS‑документ на Java с эллипсом радиального градиента.
  Этот пошаговый гид показывает, как задать толщину линии и определить геометрию пути
  с помощью Aspose.Page.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: Добавить эллипс в Java XPS
second_title: Aspose.Page Java API
title: Создание XPS‑документа в Java – добавление эллипса с радиальным градиентом
url: /ru/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить эллипс с радиальным градиентом с помощью Aspose.Page

## Введение
В этом руководстве вы узнаете, как **create XPS document Java** с красивым эллипсом, обведённым радиальным градиентом, используя Aspose.Page for Java. Aspose.Page — надёжная библиотека, которая абстрагирует детали низкоуровневого XPS, позволяя сосредоточиться на дизайне, а не на тонкостях формата файла. К концу этого руководства у вас будет готовый XPS‑файл, который можно встроить в отчёты, счета или любой процесс генерации документов.

## Быстрые ответы
- **Что делает этот код?** Одностраничный XPS‑файл, содержащий эллипс, обведённый многокрасочным радиальным градиентом.  
- **Какой основной API используется?** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, etc.).  
- **Нужна ли лицензия для запуска примера?** Временная лицензия подходит для оценки; полная лицензия требуется для продакшн.  
- **Какие ключевые свойства мы задаём?** Кисть обводки (радиальный градиент), метод распространения, остановки градиента и толщина обводки.  
- **Можно ли изменить размер эллипса?** Да — измените строку геометрии пути или координаты кисти градиента.

## Что такое “create XPS document Java”?
Создание XPS‑документа в Java означает программную генерацию файла XML Paper Specification (XPS) — формата фиксированного макета, похожего на PDF — непосредственно из Java‑кода. Aspose.Page предоставляет высокоуровневую объектную модель (`XpsDocument`, `XpsCanvas` и т.д.), которая абстрагирует XML‑разметку, делая процесс таким же простым, как работа со стандартными объектами Java.

## Почему использовать эллипс с радиальным градиентом?
Радиальный градиент создаёт ощущение трёхмерности, идеально подходит для визуальных акцентов, логотипов или декоративных элементов в отчётах. По сравнению с обводкой сплошного цвета, градиент добавляет глубину без значительного увеличения размера файла, а формат XPS сохраняет векторное качество при любом масштабировании.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующие требования:
- Java Development Kit (JDK), установленный на вашем компьютере.
- Библиотека Aspose.Page for Java загружена. Вы можете получить её [здесь](https://releases.aspose.com/page/java/).
- Редактор кода по вашему выбору (Eclipse, IntelliJ и т.д.) для написания и выполнения Java‑кода.

## Импорт пакетов
Убедитесь, что необходимые пакеты импортированы в ваш Java‑проект для использования Aspose.Page. Добавьте следующие операторы импорта в начало вашего Java‑файла:

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```

## Шаг 1: Настройка каталога документа
Определите путь к каталогу, где будет сохранён XPS‑документ:

```java
String dataDir = "Your Document Directory";
```

## Шаг 2: Создание XPS‑документа
Инициализируйте новый XPS‑документ, используя следующий код:

```java
XpsDocument doc = new XpsDocument();
```

## Шаг 3: Определение остановок радиального градиента
Создайте список остановок градиента для эллипса, обведённого радиальным градиентом:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## Шаг 4: Создание геометрии пути
Определите эллипс с радиальным градиентом, используя геометрию пути:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## Шаг 5: Добавление холста и пути
Добавьте новый холст в документ и присоедините путь с определённой геометрией:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## Шаг 6: Установка обводки и градиента
Настройте обводку пути с помощью кисти радиального градиента:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## Шаг 7: Установка толщины обводки
Укажите **set stroke thickness** пути:

```java
path.setStrokeThickness(12f);
```

## Шаг 8: Сохранение документа
Сохраните полученный XPS‑документ:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

Поздравляем! Вы успешно добавили эллипс с радиальным градиентом, одновременно **creating an XPS document Java** с Aspose.Page.

## Распространённые проблемы и решения
| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| **Эллипс выглядит плоским** | Используется `XpsSpreadMethod.Pad` вместо `Reflect` | Измените метод распространения на `XpsSpreadMethod.Reflect`, как показано в Шаге 6. |
| **Отсутствует файл вывода** | `dataDir` указывает на несуществующую папку | Убедитесь, что каталог существует, или используйте абсолютный путь. |
| **Цвета градиента выглядят некорректно** | Неправильный порядок остановок градиента | Проверьте, что значения `offset` (0 → 1) увеличиваются монотонно. |
| **Ошибки компиляции** | Отсутствуют JAR‑файлы Aspose.Page в classpath | Добавьте `aspose-page-xx.jar` в зависимости вашего проекта. |

## Часто задаваемые вопросы

**В: Можно ли использовать Aspose.Page for Java с другими Java‑библиотеками?**  
Да, Aspose.Page for Java можно бесшовно интегрировать с другими Java‑библиотеками.

**В: Подходит ли Aspose.Page для масштабной обработки документов?**  
Абсолютно! Aspose.Page разработан для эффективной обработки документов в больших масштабах.

**В: Где я могу найти больше учебных материалов и примеров для Aspose.Page for Java?**  
Посетите [документацию Aspose.Page for Java](https://reference.aspose.com/page/java/) для получения полных учебных материалов и примеров.

**В: Как получить временную лицензию для Aspose.Page for Java?**  
Вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).

**В: Есть ли форумы сообщества для обсуждения Aspose.Page?**  
Да, присоединяйтесь к [форуму сообщества Aspose.Page](https://forum.aspose.com/c/page/39), чтобы общаться с другими разработчиками и получать помощь.

---

**Последнее обновление:** 2026-04-24  
**Тестировано с:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}