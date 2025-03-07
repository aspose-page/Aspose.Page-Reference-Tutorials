---
title: Добавьте простые свойства в XMP с помощью Java
linktitle: Добавьте простые свойства в XMP с помощью Java
second_title: API Aspose.Page Java
description: Раскройте потенциал Aspose.Page для Java с помощью нашего руководства по добавлению свойств к метаданным XMP в файлах EPS. Улучшите обработку документов без особых усилий!
weight: 14
url: /ru/java/xmp-metadata-manipulation/add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавьте простые свойства в XMP с помощью Java

## Введение
В постоянно меняющемся мире обработки документов эффективное управление метаданными имеет решающее значение. Aspose.Page для Java позволяет разработчикам беспрепятственно манипулировать данными расширяемой платформы метаданных (XMP). В этом руководстве мы рассмотрим процесс добавления простых свойств в XMP с помощью Java, предоставив вам подробное пошаговое руководство.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
- Базовые знания Java-программирования.
-  Установлена библиотека Aspose.Page для Java. Вы можете скачать его[здесь](https://releases.aspose.com/page/java/).
- Пример файла EPS, содержащего метаданные. Если у вас его нет, используйте предоставленный файл «xmp3.eps».
## Импортировать пакеты
Убедитесь, что вы импортировали необходимые пакеты для запуска проекта:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## Шаг 1. Получите метаданные XMP
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Инициализировать входной поток файлов EPS
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Получите метаданные XMP. Если файл EPS не содержит метаданных XMP, мы получаем новый, заполненный значениями из комментариев метаданных PS (%%Creator, %%CreateDate, %%Title и т. д.).
XmpMetadata xmp = document.getXmpMetadata();
```
## Шаг 2. Добавьте свойство даты
```java
// Добавьте значение свойства даты «xmp:Date1».
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## Шаг 3. Добавьте целочисленное свойство
```java
// Добавить значение целочисленного свойства «xmp:Intg1».
xmp.put("xmp:Intg1", new XmpValue(111));
```
## Шаг 4. Добавьте двойное свойство
```java
// Добавьте значение двойного свойства «xmp:Double1».
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## Шаг 5. Добавьте строковое свойство
```java
// Добавить значение свойства строки «xmp:String1»
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## Шаг 6: Сохранить документ
```java
// Инициализировать выходной поток файлов EPS
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//Сохранить документ с измененными метаданными XMP
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Шаг 7: Закройте потоки
```java
// Закрыть входной поток EPS
psStream.close();
```
## Заключение
Aspose.Page для Java упрощает процесс управления метаданными XMP в файлах EPS. Следуя этому пошаговому руководству, вы сможете легко добавлять простые свойства для улучшения метаданных вашего документа.
## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Page для Java с другими языками программирования?
Aspose.Page в основном поддерживает Java, но существуют версии и для других языков, например .NET.
### Доступна ли бесплатная пробная версия Aspose.Page для Java?
 Да, вы можете изучить возможности Aspose.Page, получив бесплатную пробную версию.[здесь](https://releases.aspose.com/).
### Где я могу найти подробную документацию по Aspose.Page для Java?
 Документация доступна[здесь](https://reference.aspose.com/page/java/).
### Как я могу получить временную лицензию на Aspose.Page для Java?
 Временную лицензию можно получить[здесь](https://purchase.aspose.com/temporary-license/).
### Где я могу приобрести Aspose.Page для Java?
 Вы можете приобрести товар[здесь](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
