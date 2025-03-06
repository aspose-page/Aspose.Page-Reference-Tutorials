---
title: Agregar degradado horizontal en Java PostScript
linktitle: Agregar degradado horizontal en Java PostScript
second_title: API de Java de Aspose.Page
description: Aprenda cómo agregar un degradado horizontal en Java PostScript con Aspose.Page para Java. Cree documentos visualmente impresionantes sin esfuerzo.
weight: 11
url: /es/java/postscript-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar degradado horizontal en Java PostScript

## Introducción
Bienvenido a este tutorial completo sobre cómo agregar un degradado horizontal en Java PostScript usando Aspose.Page para Java. Aspose.Page es una potente biblioteca Java que permite a los desarrolladores trabajar con PostScript y otros formatos de documentos. En este tutorial, lo guiaremos a través del proceso de creación de un documento PostScript con un degradado horizontal usando ejemplos paso a paso.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
- Kit de desarrollo de Java (JDK) instalado en su máquina.
- Aspose.Page para la biblioteca Java. Puedes descargarlo desde el[Documentación Java de Aspose.Page](https://reference.aspose.com/page/java/).
## Importar paquetes
Comience importando los paquetes necesarios en su proyecto Java. Estos paquetes son cruciales para trabajar con Aspose.Page.
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## Paso 1: crea un rectángulo
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear flujo de salida para un documento PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Crea opciones de guardado con tamaño A4
PsSaveOptions options = new PsSaveOptions();
// Cree un nuevo documento PS con la página abierta
PsDocument document = new PsDocument(outPsStream, options, false);
//Crea un rectángulo
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Paso 2: crear pintura degradada lineal horizontal
```java
// Crea pintura degradada lineal horizontal. Los componentes de escala en la transformación deben ser iguales al ancho y alto del rectángulo.
// Los componentes de traducción son desplazamientos del rectángulo.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Establecer pintura
document.setPaint(paint);
```
## Paso 3: llena el rectángulo
```java
// Rellena el rectángulo
document.fill(rectangle);
```
## Paso 4: rellena un texto con el degradado
```java
// Rellenar un texto con el degradado.
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## Paso 5: Traza un texto con el degradado
```java
// Trazar un texto con el degradado
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Conclusión
¡Felicidades! Ha agregado con éxito un degradado horizontal en Java PostScript usando Aspose.Page para Java. Este tutorial le proporciona una guía detallada paso a paso para ayudarle a crear documentos PostScript visualmente atractivos.
## Preguntas frecuentes
### ¿Puedo utilizar Aspose.Page para Java en proyectos comerciales?
Sí, Aspose.Page para Java se puede utilizar en proyectos comerciales. Para obtener detalles sobre la licencia, visite[Aspose.Comprar](https://purchase.aspose.com/buy).
### ¿Hay una prueba gratuita disponible?
 Sí, puedes acceder a una prueba gratuita de Aspose.Page para Java[aquí](https://releases.aspose.com/).
### ¿Dónde puedo encontrar documentación y soporte adicionales?
 Visita el[Documentación Java de Aspose.Page](https://reference.aspose.com/page/java/) para recursos integrales. Para obtener apoyo de la comunidad, consulte el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39).
### ¿Cómo puedo obtener una licencia temporal?
 Puede obtener una licencia temporal de[Aspose.Comprar](https://purchase.aspose.com/temporary-license/).
### ¿Cuáles son los requisitos del sistema para Aspose.Page para Java?
 Referirse a[documentación](https://reference.aspose.com/page/java/) para conocer los requisitos detallados del sistema.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
