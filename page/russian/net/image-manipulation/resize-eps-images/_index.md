---
date: 2026-03-03
description: Узнайте, как изменять размер EPS‑изображений в .NET с помощью Aspose.Page
  — пошаговое руководство по изменению размера EPS с использованием пунктов, дюймов,
  миллиметров или процентов.
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: Как изменить размер EPS‑изображений с помощью Aspose.Page для .NET
url: /ru/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как изменить размер EPS‑изображений с помощью Aspose.Page для .NET

## Введение

Ищете **как изменить размер EPS**‑изображений без проблем, используя Aspose.Page для .NET? Этот учебник — ваш всесторонний гид по простому управлению размерами EPS‑изображений в различных единицах измерения: пунктах, дюймах, миллиметрах и процентах. Aspose.Page для .NET предоставляет мощный набор инструментов, и в этом руководстве мы пошагово пройдём процесс.

## Быстрые ответы
- **Какая библиотека обрабатывает изменение размера EPS?** Aspose.Page для .NET  
- **Какие единицы поддерживаются?** Пункты, Дюймы, Миллиметры и Проценты  
- **Нужна ли лицензия для продакшн?** Да — требуется коммерческая лицензия  
- **Можно ли изменять размер нескольких файлов одновременно?** Конечно — просто пройдитесь циклом по файлам  
- **Поддерживается ли .NET Core?** Да, API работает с .NET Framework и .NET Core  

## Что такое изменение размера EPS?
Encapsulated PostScript (EPS) — это векторный графический формат, широко используемый в полиграфии и дизайне. Изменение размера EPS‑файла меняет его ограничивающий прямоугольник без растрирования рисунка, сохраняя чёткость при любом масштабе.

## Почему изменять размер EPS‑изображений?
- **Сохранение качества печати:** Векторное масштабирование сохраняет резкость краёв.  
- **Соответствие требованиям макета:** Подгоняйте размеры под страницу или холст.  
- **Автоматизация пакетных задач:** Программно изменяйте размер десятков файлов за секунды.  

## Требования

Прежде чем приступить к магии изменения размеров, убедитесь, что у вас есть следующие предварительные условия:

- Библиотека Aspose.Page для .NET: Убедитесь, что библиотека Aspose.Page для .NET установлена. Вы можете скачать её [here](https://releases.aspose.com/page/net/).

- Каталог документов: Создайте каталог, где будете хранить входной EPS‑файл и выходные файлы с изменённым размером.

Теперь, когда всё готово, перейдём к импорту необходимых пространств имён и пошаговому руководству.

## Импорт пространств имён

В вашем .NET‑проекте начните с импорта необходимых пространств имён для работы с Aspose.Page. Добавьте следующий код в начало файла:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## Как изменить размер EPS в пунктах

Пункты — стандартная единица измерения в полиграфии. Пример ниже удваивает исходную ширину и высоту.

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## Как изменить размер EPS в дюймах

Дюймы часто используют графические дизайнеры при подготовке материалов к печати.

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## Как изменить размер EPS в миллиметрах

Миллиметры распространены в регионах, использующих метрическую систему.

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## Как изменить размер EPS с помощью процентов

Изменение размера на основе процентов позволяет масштабировать изображение относительно его оригинального размера.

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

Не стесняйтесь интегрировать эти методы в свой проект, и вы будете менять размер EPS‑изображений без труда. Экспериментируйте с различными единицами, чтобы достичь нужных размеров.

## Распространённые проблемы и решения
- **Файл не найден:** Убедитесь, что `dataDir` указывает на правильную папку и что `input.eps` существует.  
- **Неожиданный размер:** Помните, что `Units.Percents` ожидает значения вроде 150 для 150 % от оригинального размера.  
- **Исключение лицензии:** Если появляется ошибка лицензирования, убедитесь, что действительный файл лицензии Aspose.Page загружен до создания `PsDocument`.

## Заключение

Поздравляем! Вы освоили **как изменить размер EPS**‑изображений с помощью Aspose.Page для .NET. Эта мощная библиотека открывает мир возможностей для работы с векторной графикой. Независимо от того, разрабатываете ли вы печатные материалы или цифровые медиа, Aspose.Page позволяет достичь точных и индивидуальных результатов.

## Часто задаваемые вопросы

### Q1: Можно ли изменять размер нескольких EPS‑изображений одновременно?

A1: Да, вы можете пройтись циклом по коллекции EPS‑файлов, применяя методы изменения размера соответственно.

### Q2: Совместима ли Aspose.Page с другими форматами изображений?

A2: Aspose.Page в основном ориентирована на форматы PostScript и EPS. Для других форматов рассмотрите использование Aspose.Imaging.

### Q3: Есть ли лицензионные нюансы для коммерческих проектов?

A3: Да, убедитесь, что у вас есть действующая лицензия. Посетите [here](https://purchase.aspose.com/buy) для деталей лицензирования.

### Q4: Можно ли попробовать Aspose.Page перед покупкой?

A4: Абсолютно! Вы можете получить бесплатную пробную версию [here](https://releases.aspose.com/).

### Q5: Где можно получить дополнительную помощь или обсудить проблемы?

A5: Посетите [Aspose.Page forum](https://forum.aspose.com/c/page/39), чтобы связаться с сообществом и получить поддержку.

## Часто задаваемые вопросы

**Q: Работает ли этот код с .NET Core 6?**  
A: Да. API совместим с .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ и .NET 6+.

**Q: Как сохранить оригинальный цветовой профиль?**  
A: Метод `ResizeEps` не изменяет цветовые данные; он лишь меняет ограничивающий прямоугольник.

**Q: Можно ли изменить размер EPS без загрузки всего файла в память?**  
A: Использование потока, как показано, снижает потребление памяти; документ обрабатывается «на лету».

**Q: Можно ли цепочкой выполнять несколько операций изменения размера?**  
A: Конечно. Вызывайте `ResizeEps` последовательно для одного и того же экземпляра `PsDocument`.

**Q: Что происходит с внедрёнными изображениями внутри EPS?**  
A: Они масштабируются пропорционально векторному содержимому, сохраняя качество.

---

**Последнее обновление:** 2026-03-03  
**Тестировано с:** Aspose.Page 24.12 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}