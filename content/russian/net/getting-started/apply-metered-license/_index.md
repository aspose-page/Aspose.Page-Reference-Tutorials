---
title: Примените дозированную лицензию с помощью Aspose.Page для .NET
linktitle: Применить лимитную лицензию
second_title: Aspose.Page .NET API
description: Изучите плавную интеграцию Aspose.Page для .NET с помощью этого пошагового руководства по применению лимитной лицензии. Оптимизируйте обработку документов без особых усилий.
type: docs
weight: 10
url: /ru/net/getting-started/apply-metered-license/
---
## Введение

Раскройте весь потенциал Aspose.Page для .NET, применив дозированную лицензию. Это руководство проведет вас через процесс настройки и применения дозированной лицензии, обеспечивая плавное и оптимизированное использование этой мощной библиотеки .NET.

## Предварительные условия

Прежде чем приступить к пошаговым действиям, убедитесь, что у вас есть следующие предварительные условия:

-  Действующая лицензия Aspose.Page для .NET: ее можно получить на сайте[Purchase.aspose.com](https://purchase.aspose.com/buy).
-  Установлена библиотека Aspose.Page: см.[документация](https://reference.aspose.com/page/net/) для инструкций по установке.
- Среда разработки .NET. Убедитесь, что на вашем компьютере установлена работающая среда .NET.

## Импортировать пространства имен

В свой проект .NET импортируйте необходимые пространства имен для доступа к функциям Aspose.Page:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## Шаг 1. Установите лимитированные открытые и закрытые ключи

 Инициализируйте`Aspose.Page.Metered` class и установите лимитированные открытый и закрытый ключи. Заменять`<type public key here>` и`<type private key here>` с вашими настоящими ключами.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## Шаг 2. Загрузите файл EPS и создайте документ.

 Укажите путь к вашему EPS-файлу и создайте поток для чтения его содержимого. Затем создайте экземпляр`PsDocument` класс из потока.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Шаг 3. Конвертируйте EPS в PNG-изображение

 Создать`ImageDevice` для преобразования файла EPS в изображение PNG. Сохраните файл EPS как изображение, используя`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## Шаг 4. Получение байтов изображения

Получите байты изображения, где каждый массив байтов представляет одну страницу. В данном случае у нас есть одна страница.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## Шаг 5. Сохраните байты изображения в файл

Сохраните байты изображения в файл, обеспечив успешное преобразование из EPS в PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## Шаг 6. Проверка лимитной лицензии

Визуально проверьте, успешно ли применена лимитная лицензия. Если полученное изображение не содержит красного оценочного сообщения, это означает, что лимитная лицензия применяется без каких-либо проблем.

Теперь вы готовы использовать все возможности Aspose.Page для .NET с дозированной лицензией!

## Заключение

Это пошаговое руководство дало вам знания о том, как легко применить дозированную лицензию с помощью Aspose.Page для .NET. Расширьте свои возможности обработки документов и изучите обширные возможности, предлагаемые этой мощной библиотекой.

## Часто задаваемые вопросы

### Вопрос 1. Как получить дозированную лицензию на Aspose.Page для .NET?

 А1: Посетите[Purchase.aspose.com](https://purchase.aspose.com/buy) получить действующую лицензию.

### Вопрос 2. Где я могу найти документацию по Aspose.Page для .NET?

 A2: См.[Aspose.Page .NET](https://reference.aspose.com/page/net/) для получения полной документации.

### Вопрос 3: Существует ли форум для обсуждения и поддержки Aspose.Page?

 A3: Да, посетите[Форум](https://forum.aspose.com/c/page/39) взаимодействовать с сообществом и обращаться за помощью.

### Вопрос 4: Могу ли я попробовать Aspose.Page для .NET перед покупкой?

 А4: Абсолютно! Получите доступ к бесплатной пробной версии на[здесь](https://releases.aspose.com/).

### Вопрос 5: Как я могу получить временную лицензию на Aspose.Page для .NET?

 А5: Посетите[временная лицензия/](https://purchase.aspose.com/temporary-license/) получить временную лицензию.