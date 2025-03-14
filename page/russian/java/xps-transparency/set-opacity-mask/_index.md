---
title: Установите маску непрозрачности в Java XPS
linktitle: Установите маску непрозрачности в Java XPS
second_title: API Aspose.Page Java
description: Откройте для себя возможности настройки масок непрозрачности в Java XPS с помощью Aspose.Page. Следуйте нашему пошаговому руководству, чтобы визуально улучшить работу с документами.
weight: 11
url: /ru/java/xps-transparency/set-opacity-mask/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Установите маску непрозрачности в Java XPS

## Введение
Добро пожаловать в наше подробное руководство по настройке масок непрозрачности в Java XPS с использованием Aspose.Page. В этом уроке мы познакомим вас с процессом создания документа XPS, добавления холста и применения маски непрозрачности к прямоугольнику с использованием мощных функций Aspose.Page для Java.
## Предварительные условия
Прежде чем погрузиться в это руководство, убедитесь, что у вас есть следующее:
- Базовое понимание программирования на Java.
-  Установлена библиотека Aspose.Page для Java. Вы можете скачать его[здесь](https://releases.aspose.com/page/java/).
-  Действующая лицензия для Aspose.Page. Если у вас ее нет, вы можете получить временную лицензию.[здесь](https://purchase.aspose.com/temporary-license/).
- Среда разработки, настроенная для запуска приложений Java.
## Импортировать пакеты
Начните с импорта необходимых пакетов в ваш Java-проект. Убедитесь, что у вас правильно интегрирована библиотека Aspose.Page. Ниже приведен фрагмент, который поможет вам:
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Теперь давайте разобьем пример кода на несколько шагов:
## Шаг 1. Создайте новый документ XPS
```java
// Создайте новый документ XPS.
XpsDocument doc = new XpsDocument();
```
## Шаг 2. Добавьте холст
```java
// Новый холст
XpsCanvas canvas = doc.addCanvas();
```
## Шаг 3. Добавьте прямоугольник с маской непрозрачности
```java
// Прямоугольник в центре слева с непрозрачностью, замаскированной ImageBrush.
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## Шаг 4. Установите маску непрозрачности с помощью ImageBrush
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## Шаг 5. Сохраните полученный документ XPS.
```java
// Сохраните полученный документ XPS.
doc.save(dataDir + "OpacityMask_out.xps"); 
```
Внимательно следуйте этим шагам, чтобы включить маски непрозрачности в документ Java XPS с помощью Aspose.Page.
## Заключение
Поздравляем! Вы успешно научились устанавливать маски непрозрачности в Java XPS с помощью Aspose.Page. Эта функция добавляет визуальную насыщенность вашим документам, делая их более привлекательными и динамичными.
## Часто задаваемые вопросы
### Совместим ли Aspose.Page со всеми средами разработки Java?
Да, Aspose.Page предназначен для бесперебойной работы с различными средами разработки Java.
### Могу ли я использовать Aspose.Page без лицензии?
Хотя вы можете использовать Aspose.Page без лицензии, рекомендуется приобрести ее, чтобы получить полный спектр функций и поддержки.
### Есть ли какие-либо ограничения на пробную версию?
Пробная версия может иметь некоторые ограничения функций. Подробности рекомендуется проверить в документации.
### Как я могу получить поддержку для Aspose.Page?
 Вы можете посетить[Форум Aspose.Page](https://forum.aspose.com/c/page/39) для поддержки сообщества или приобретения лицензии на премиальную помощь.
### Есть ли гарантия возврата денег для Aspose.Page?
 Обратитесь к[страница покупки](https://purchase.aspose.com/buy) для получения информации о политике возврата.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
