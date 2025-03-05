---
title: Простая интеграция дозированных лицензий с Aspose.Page Java
linktitle: Установить лимитную лицензию в Java
second_title: API Aspose.Page Java
description: Узнайте об бесшовной интеграции Aspose.Page с Java. Легко настройте лимитные лицензии и расширьте возможности обработки документов.
type: docs
weight: 10
url: /ru/java/license-management/set-metered-license/
---
## Введение
Добро пожаловать в наше подробное руководство по настройке лимитной лицензии на Java с помощью Aspose.Page. Если вы хотите расширить свои возможности обработки документов и обеспечить плавную интеграцию с Aspose.Page, вы попали по адресу. В этом уроке мы покажем вам весь процесс, разбив каждый шаг на легко усваиваемые части.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
- Базовые знания Java-программирования.
-  Установлена библиотека Aspose.Page. Вы можете скачать его с[здесь](https://releases.aspose.com/page/java/).
- Измеренные открытые и закрытые ключи, которые вы можете получить через свою учетную запись Aspose.
## Импортировать пакеты
Начнем с импорта необходимых пакетов для нашей Java-программы. Убедитесь, что в ваш проект интегрирована библиотека Aspose.Page.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## Шаг 1. Инициализация формата документа и изображения
Первым шагом является настройка документа и определение желаемого формата изображения.
```java
// установить лимитированные открытые и закрытые ключи
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Получите доступ к свойству setMeteredKey и передайте открытый и закрытый ключи в качестве параметров.
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## Шаг 2. Инициализация входного потока PostScript
На этом этапе мы инициализируем входной поток PostScript для обработки.
```java
// Инициализировать входной поток PostScript
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## Шаг 3. Проверьте лицензию документа
Прежде чем продолжить, очень важно проверить, имеет ли документ соответствующую лицензию.
```java
// Проверьте, является ли документ лицензионным
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## Шаг 4. Инициализация параметров и устройства изображения
Теперь давайте инициализируем параметры и устройство изображения с параметрами по умолчанию.
```java
// Инициализируйте объект параметров с параметрами по умолчанию.
ImageSaveOptions options = new ImageSaveOptions();
// Инициализируйте объект ImageDevice с параметрами по умолчанию.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## Шаг 5. Сохраните файл EPS как изображение.
Сохраните файл EPS как изображение, используя определенные параметры и устройство.
```java
// Сохранить файл EPS как изображение
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## Шаг 6: Получите и сохраните байты изображения
Получите байты изображения и сохраните их в файл.
```java
// Получить байты изображений. Массив в один байт для одной страницы. В нашем случае у нас есть одна страница.
byte[][] imagesBytes = device.getImagesBytes();
// Сохранение байтов изображения в файл
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## Заключение
Поздравляем! Вы успешно настроили дозированную лицензию на Java с помощью Aspose.Page. В этом руководстве представлено пошаговое руководство, позволяющее обеспечить плавный процесс интеграции.
## Часто задаваемые вопросы
### Вопрос: Как получить измеренные открытые и закрытые ключи?
Вы можете получить эти ключи через свою учетную запись Aspose.
### Вопрос: Является ли библиотека Aspose.Page бесплатной?
 Aspose.Page предлагает как бесплатную пробную, так и платную версии. Посещать[здесь](https://releases.aspose.com/) на бесплатную пробную версию.
### Вопрос: Могу ли я использовать Aspose.Page для коммерческих проектов?
 Да, Aspose.Page предлагает коммерческие лицензии. Вы можете приобрести их[здесь](https://purchase.aspose.com/buy).
### Вопрос: Где я могу найти дополнительную документацию?
 Обратитесь к документации[здесь](https://reference.aspose.com/page/java/).
### Вопрос: Как я могу получить временные лицензии?
 Временные лицензии можно получить[здесь](https://purchase.aspose.com/temporary-license/).