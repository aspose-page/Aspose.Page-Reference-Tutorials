---
date: 2026-02-25
description: Узнайте, как создать градиент XPS с горизонтальной заливкой, используя
  Aspose.Page для .NET. Легко повышайте визуальную привлекательность ваших документов.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'Создание градиента XPS: горизонтальное заполнение с Aspose.Page для .NET'
url: /ru/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание градиента XPS – Добавление горизонтального градиента в XPS с помощью Aspose.Page для .NET

## Введение

В этом руководстве вы **создадите градиентные заливки XPS**, которые будут проходить горизонтально по вашим страницам. Добавление горизонтального градиента мгновенно делает документ XPS более изысканным и привлекательным, особенно для отчетов, брошюр или любого визуально‑насыщенного вывода. Мы пройдем весь процесс с использованием Aspose.Page для .NET, от настройки окружения до сохранения готового файла XPS.

## Быстрые ответы
- **Что покрывает это руководство?** Добавление горизонтального градиента в документ XPS с помощью Aspose.Page для .NET.  
- **Какая библиотека требуется?** Aspose.Page для .NET (любая актуальная версия).  
- **Нужна ли лицензия?** Для разработки подходит пробная версия; для продакшн‑использования требуется коммерческая лицензия.  
- **Сколько времени займет реализация?** Около 5–10 минут для базового градиента.  
- **Можно ли изменить направление градиента?** Да – измените начальные/конечные точки `LinearGradientBrush`.

## Как создать градиент XPS с Aspose.Page для .NET

Ниже представлено пошаговое руководство, которое объясняет **почему** каждая строка кода существует, а не только **что** она делает. Смело следуйте вместе с Visual Studio или вашим любимым .NET‑редактором.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

1. Библиотека Aspose.Page для .NET: Убедитесь, что библиотека Aspose.Page для .NET установлена в вашей среде разработки. Скачать её можно из [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

2. Среда разработки: Настройте подходящую среду разработки, включая редактор кода, например Visual Studio.

## Импорт пространств имён

Начните с импорта необходимых пространств имён в ваш проект. Эти пространства имён необходимы для работы с Aspose.Page для .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Теперь разберём предоставленный пример на несколько шагов.

## Шаг 1: Установите путь к каталогу документов

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Шаг 2: Создайте новый документ XPS

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Шаг 3: Инициализируйте остановки градиента

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Шаг 4: Создайте новый путь

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Шаг 5: Сохраните полученный документ XPS

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Теперь вы успешно добавили горизонтальный градиент в ваш документ XPS с помощью Aspose.Page для .NET.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|----------|----------|
| Градиент выглядит сплошным цветом | Остановки градиента добавлены неверно | Убедитесь, что `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` выполнено после установки кисти. |
| Сохранённый файл пустой | `dataDir` указывает на несуществующую папку | Проверьте, существует ли папка, или используйте абсолютный путь. |
| Ошибка компиляции на `PointF` | Отсутствует ссылка `System.Drawing` | Добавьте ссылку на `System.Drawing.Common` (для .NET Core/5+). |

## Часто задаваемые вопросы

### Q1: Где можно найти документацию Aspose.Page для .NET?

A1: Документацию можно найти [здесь](https://reference.aspose.com/page/net/).

### Q2: Как скачать Aspose.Page для .NET?

A2: Библиотеку можно скачать со [страницы загрузки Aspose.Page для .NET](https://releases.aspose.com/page/net/).

### Q3: Где можно приобрести Aspose.Page для .NET?

A3: Приобрести Aspose.Page для .NET можно на [странице покупки](https://purchase.aspose.com/buy).

### Q4: Есть ли бесплатная пробная версия?

A4: Да, бесплатную пробную версию можно получить [здесь](https://releases.aspose.com/).

### Q5: Как получить временную лицензию для Aspose.Page для .NET?

A5: Временную лицензию можно получить по [этой ссылке](https://purchase.aspose.com/temporary-license/).

## Часто задаваемые вопросы

**В: Можно ли использовать эту технику градиента с документами XPS, которые уже содержат изображения?**  
О: Абсолютно. Градиент применяется к слою пути, поэтому существующие изображения остаются нетронутыми.

**В: Возможно ли создать вертикальный градиент вместо горизонтального?**  
О: Да. Измените начальные и конечные точки `LinearGradientBrush`, задав разные координаты Y при фиксированном X.

**В: Поддерживает ли Aspose.Page .NET Core?**  
О: Библиотека полностью совместима с .NET Core, .NET 5 и более новыми версиями.

**В: Как переиспользовать один и тот же градиент на нескольких страницах?**  
О: Создайте `XpsLinearGradientBrush` один раз, сохраните его в переменной и назначайте её путям на каждой странице.

## Заключение

Улучшение ваших документов XPS с помощью градиентов не только повышает визуальную привлекательность, но и делает взаимодействие с пользователем более захватывающим. С Aspose.Page для .NET вы можете **создавать градиентные заливки XPS** быстро и надёжно, придавая вашим отчетам, брошюрам или электронным книгам профессиональный вид.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Последнее обновление:** 2026-02-25  
**Тестировано с:** Aspose.Page for .NET 24.11  
**Автор:** Aspose  

---