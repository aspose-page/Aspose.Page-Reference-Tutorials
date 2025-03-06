---
title: Измените значения с помощью Aspose.Page для .NET
linktitle: Менять значения
second_title: Aspose.Page .NET API
description: Научитесь манипулировать файлами EPS с помощью Aspose.Page для .NET. Изменяйте значения метаданных XMP без особых усилий.
weight: 17
url: /ru/net/eps-metadata-management/modify-eps-metadata-change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Измените значения с помощью Aspose.Page для .NET

## Введение

В динамичном мире обработки документов Aspose.Page для .NET выделяется как мощный инструмент, предлагающий разработчикам возможность легко манипулировать файлами EPS. В этом уроке мы углубимся в процесс изменения значений в файлах EPS с помощью Aspose.Page для .NET. Независимо от того, являетесь ли вы опытным разработчиком или любопытным новичком, это пошаговое руководство предоставит вам навыки, необходимые для эффективного изменения метаданных XMP в ваших файлах EPS.

## Предварительные условия

Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:

### 1. Aspose.Page для библиотеки .NET

Убедитесь, что в вашей среде разработки установлена библиотека Aspose.Page для .NET. Если нет, то вы можете скачать его[здесь](https://releases.aspose.com/page/net/).

### 2. Каталог документов

Создайте каталог для своих документов. Это будет место, где будут храниться ваши файлы EPS.

Теперь, когда у нас есть необходимые предпосылки, давайте перейдем к следующим важным шагам.

## Импортировать пространства имен

В любом проекте .NET важно импортировать необходимые пространства имен для использования функций Aspose.Page. Вот как вы можете это сделать:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Шаг 1. Инициализируйте входной поток файла EPS.

```csharp
// Путь к каталогу документов.
string dataDir = "Your Document Directory";
// Инициализировать входной поток файла EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## Шаг 2. Создайте экземпляр PsDocument из потока.

```csharp
//Создать экземпляр PsDocument из потока
PsDocument document = new PsDocument(psStream);
```

Теперь, когда мы подготовили почву, давайте перейдем к сути нашего руководства — изменению значений метаданных XMP в файле EPS.

## Шаг 3. Получите метаданные XMP

```csharp
// Получите метаданные XMP. Если файл EPS не содержит метаданных XMP, мы получаем новый, заполненный значениями из комментариев метаданных PS (%%Creator, %%CreateDate, %%Title и т. д.).
XmpMetadata xmp = document.GetXmpMetadata();
```

## Шаг 4. Измените значения метаданных XMP.

Теперь давайте изменим некоторые ключевые значения в метаданных XMP:

### Шаг 4.1: Измените значение ModifyDate

```csharp
// Изменить значение ModifyDate
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### Шаг 4.2. Измените ценность Создателя

```csharp
// Изменить ценность автора
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Шаг 4.3: Измените значение заголовка

```csharp
// Изменить значение заголовка
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

После внесения этих изменений перейдем к последнему шагу — сохранению измененного файла EPS.

## Шаг 5. Сохраните файл EPS с измененными метаданными XMP.

### Шаг 5.1: Создайте выходной поток

```csharp
// Создать выходной поток
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### Шаг 5.2: Сохраните файл EPS.

```csharp
// Сохранить файл EPS
document.Save(outPsStream);
```

Наконец, закройте входной поток:

```csharp
finally
{
    psStream.Close();
}
```

Поздравляем! Вы успешно изменили значения метаданных XMP в файле EPS с помощью Aspose.Page для .NET.

## Заключение

В этом уроке мы рассмотрели простой процесс изменения значений в файлах EPS с помощью Aspose.Page для .NET. Теперь вы, как разработчик, имеете в своем распоряжении мощный инструмент для эффективного манипулирования документами.

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я использовать Aspose.Page для .NET с файлами других форматов?

A1: Aspose.Page в первую очередь ориентирован на манипулирование файлами EPS. Что касается других форматов, изучите разнообразный ассортимент продуктов Aspose.

### В2: Доступна ли пробная версия?

 О2: Да, вы можете опробовать Aspose.Page для .NET, воспользовавшись бесплатной пробной версией.[здесь](https://releases.aspose.com/).

### В3: Где я могу найти подробную документацию?

 A3: Полную документацию можно найти[здесь](https://reference.aspose.com/page/net/).

### Вопрос 4: Как получить временную лицензию?

 A4: Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).

### Вопрос 5: Могу ли я приобрести Aspose.Page для .NET?

 А5: Абсолютно! Посетите страницу покупки[здесь](https://purchase.aspose.com/buy) для вариантов лицензирования.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
