---
title: Получить метаданные из XMP с помощью Java
linktitle: Получить метаданные из XMP с помощью Java
second_title: API Aspose.Page Java
description: Раскройте возможности Aspose.Page для Java, чтобы легко извлекать метаданные XMP. Усовершенствуйте анализ документов с помощью нашего пошагового руководства!
type: docs
weight: 18
url: /ru/java/xmp-metadata-manipulation/get-metadata/
---
## Введение
Добро пожаловать в наше пошаговое руководство по использованию Aspose.Page для Java для извлечения метаданных из файлов XMP. XMP (Расширяемая платформа метаданных) обеспечивает стандартизированный способ хранения метаданных в файлах. В этом руководстве основное внимание уделяется получению важной информации из XMP с использованием Java, что дает представление о деталях документа.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
- Комплект разработки Java (JDK): убедитесь, что на вашем компьютере установлена Java.
-  Aspose.Page для Java: загрузите и установите библиотеку Aspose.Page, которую вы можете найти[здесь](https://releases.aspose.com/page/java/).
## Импортировать пакеты
В свой Java-проект импортируйте необходимые пакеты:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Шаг 1. Инициализация входного файлового потока EPS
Начните с установки пути к каталогу вашего документа и инициализации входного потока файлов EPS.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```
## Шаг 2. Получите метаданные XMP
Получите метаданные XMP из файла EPS. Если в файле отсутствуют метаданные XMP, будет создан новый файл со значениями из комментариев метаданных PS.
```java
XmpMetadata xmp = document.getXmpMetadata();
```
## Шаг 3. Извлеките информацию CreatorTool
Проверьте и распечатайте значение «CreatorTool» из метаданных XMP.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Шаг 4. Извлеките информацию CreateDate
Проверьте и распечатайте значение «CreateDate» из метаданных XMP.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Шаг 5. Получите ширину миниатюры
Если миниатюры существуют, извлеките и распечатайте ширину первой миниатюры.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```
## Шаг 6: Извлеките информацию о формате
Проверьте и распечатайте значение «формата» из метаданных XMP.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Шаг 7: Получите DocumentID
Проверьте и распечатайте значение «DocumentID» из метаданных XMP.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```
## Заключение
Поздравляем! Вы успешно научились извлекать метаданные XMP с помощью Aspose.Page для Java. В этом руководстве представлен всесторонний обзор процесса, гарантирующий, что вы сможете эффективно извлекать важную информацию из ваших документов.
## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Page для Java с другими языками программирования?
 Да, Aspose.Page поддерживает несколько языков, включая Java, .NET и другие. Проверить[документация](https://reference.aspose.com/page/java/) для получения подробной информации.
### Доступна ли бесплатная пробная версия Aspose.Page для Java?
 Да, вы можете получить доступ к бесплатной пробной версии[здесь](https://releases.aspose.com/).
### Где я могу найти поддержку Aspose.Page для Java?
 Посетить[Форум Aspose.Page](https://forum.aspose.com/c/page/39) для поддержки сообщества.
### Как получить временную лицензию на Aspose.Page для Java?
 Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
### Существуют ли дополнительные ресурсы для Aspose.Page для Java?
 Исследуйте полную[документация](https://reference.aspose.com/page/java/) и скачайте библиотеку[здесь](https://releases.aspose.com/page/java/).