---
title: Добавьте метаданные в XMP с помощью Java
linktitle: Добавьте метаданные в XMP с помощью Java
second_title: API Aspose.Page Java
description: Изучите плавную интеграцию Aspose.Page для Java и узнайте, как легко добавлять метаданные XMP в ваши файлы EPS. Улучшите свою игру в управлении документами уже сегодня!
type: docs
weight: 11
url: /ru/java/xmp-metadata-manipulation/add-metadata/
---
## Введение
Вы хотите улучшить метаданные вашего документа, добавив информацию XMP с помощью Java? Не смотрите дальше! Это пошаговое руководство проведет вас через процесс добавления метаданных в файл EPS с помощью библиотеки Aspose.Page для Java. Aspose.Page — мощный инструмент, который упрощает задачи манипулирования документами в приложениях Java.
## Предварительные условия
Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:
- Базовые знания Java-программирования.
-  Установлена библиотека Aspose.Page для Java. Вы можете скачать его[здесь](https://releases.aspose.com/page/java/).
- EPS-файл, который вы хотите изменить.
## Импортировать пакеты
Сначала импортируйте необходимые пакеты в вашу Java-программу:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## Шаг 1. Получите метаданные XMP
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Инициализировать входной поток файлов EPS
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Получите метаданные XMP. Если файл EPS не содержит метаданных XMP, новый создается с использованием значений из комментариев метаданных PS (%%Creator, %%CreateDate, %%Title и т. д.).
XmpMetadata xmp = document.getXmpMetadata();
```
Обязательно замените «Каталог ваших документов» фактическим путем, по которому хранятся ваши документы.

## Шаг 2. Получите значение CreatorTool
```java
// Получить значение «CreatorTool»
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Шаг 3. Получите значение CreateDate
```java
// Получить значение «CreateDate»
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Шаг 4. Получите значение заголовка
```java
// Получить значение «Название»
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## Шаг 5: Получить значение формата
```java
//Получить значение «формата»
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Шаг 6. Получите ценность автора
```java
// Получите ценность «создателя»
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## Шаг 7. Получите значение MetadataDate
```java
// Получить значение «МетаданныеДата»
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## Шаг 8. Сохраните документ с новыми метаданными XMP
```java
// Инициализировать выходной поток файлов EPS
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Сохранить документ с новыми метаданными XMP
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Наконец, не забудьте закрыть входной поток EPS:
```java
// Закрыть входной поток EPS
psStream.close();
```
Теперь вы успешно добавили метаданные в свой EPS-файл с помощью Aspose.Page для Java!
## Заключение
В этом руководстве мы рассмотрели процесс добавления метаданных XMP в файл EPS с использованием библиотеки Aspose.Page для Java. Этот мощный инструмент позволяет беспрепятственно манипулировать документами, улучшая общий опыт управления документами.
## Часто задаваемые вопросы
### Вопрос: Можно ли использовать Aspose.Page для Java бесплатно?
 О: Aspose.Page для Java — это коммерческий продукт. Вы можете изучить его возможности с помощью бесплатной пробной версии.[здесь](https://releases.aspose.com/).
### Вопрос: Где я могу найти документацию по Aspose.Page для Java?
 О: Документация доступна.[здесь](https://reference.aspose.com/page/java/).
### Вопрос: Как я могу получить временную лицензию на Aspose.Page для Java?
 О: Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
### Вопрос: Какие форматы файлов поддерживает Aspose.Page для Java?
О: Aspose.Page для Java поддерживает различные форматы, включая EPS, PDF и XPS.
### Вопрос: Могу ли я приобрести Aspose.Page для Java?
 О: Да, вы можете приобрести Aspose.Page для Java.[здесь](https://purchase.aspose.com/buy).