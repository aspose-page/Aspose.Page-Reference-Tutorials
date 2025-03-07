---
title: Agregar degradado vertical en Java PostScript
linktitle: Agregar degradado vertical en Java PostScript
second_title: API de Java de Aspose.Page
description: Explore la guía paso a paso para agregar degradados verticales en Java PostScript con Aspose.Page para Java. Mejore sus documentos sin esfuerzo con imágenes vibrantes.
weight: 14
url: /es/java/postscript-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar degradado vertical en Java PostScript

## Introducción
Bienvenido a esta guía paso a paso sobre cómo agregar un degradado vertical en Java PostScript usando Aspose.Page para Java. Si desea mejorar su documento con degradados llamativos, este tutorial es para usted. Aspose.Page para Java proporciona potentes herramientas para manipular documentos PostScript sin problemas.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
- Kit de desarrollo de Java (JDK) instalado en su máquina.
-  Aspose.Page para la biblioteca Java. Puedes descargarlo[aquí](https://releases.aspose.com/page/java/).
## Importar paquetes
En su proyecto Java, importe los paquetes necesarios para comenzar:
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
Ahora, dividamos el proceso de agregar un degradado vertical en Java PostScript en varios pasos.
## Paso 1: configure su directorio de documentos
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
```
## Paso 2: crear un flujo de salida para un documento PostScript
```java
// Crear flujo de salida para un documento PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```
## Paso 3: cree opciones para guardar con tamaño A4
```java
// Crea opciones de guardado con tamaño A4
PsSaveOptions options = new PsSaveOptions();
```
## Paso 4: cree un nuevo documento PS
```java
// Cree un nuevo documento PS con la página abierta
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Paso 5: crea un rectángulo
```java
//Crea un rectángulo
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Paso 6: configurar colores y fracciones para el degradado
```java
// Crea matrices de colores y fracciones para el degradado.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```
## Paso 7: crea la transformación de degradado
```java
// Crea la transformación de degradado. Los componentes de escala en la transformación deben ser iguales al ancho y alto del rectángulo.
// Los componentes de traducción son desplazamientos del rectángulo.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Girar el gradiente 90 grados alrededor de un origen.
transform.rotate(90 * (Math.PI / 180));
```
## Paso 8: crear pintura degradada lineal vertical
```java
// Crea pintura degradada lineal vertical.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Paso 9: configure la pintura y rellene el rectángulo
```java
// Establecer pintura
document.setPaint(paint);
// Rellena el rectángulo
document.fill(rectangle);
```
## Paso 10: cierre la página actual y guarde el documento
```java
// Cerrar la página actual
document.closePage();
// guardar el documento
document.save();
```
¡Felicidades! Ha agregado con éxito un degradado vertical a su documento Java PostScript usando Aspose.Page para Java.
## Conclusión
En este tutorial, exploramos el proceso de mejorar sus documentos con vibrantes gradientes verticales usando Aspose.Page para Java. Ahora puede llevar la manipulación de sus documentos al siguiente nivel incorporando imágenes impresionantes.
## Preguntas frecuentes
### ¿Puedo usar Aspose.Page para Java con otras bibliotecas de Java?
Sí, Aspose.Page para Java está diseñado para funcionar perfectamente con otras bibliotecas de Java.
### ¿Hay una prueba gratuita disponible para Aspose.Page para Java?
 Sí, puedes obtener una prueba gratuita.[aquí](https://releases.aspose.com/).
### ¿Dónde puedo encontrar documentación adicional?
 La documentación detallada está disponible.[aquí](https://reference.aspose.com/page/java/).
### ¿Cómo puedo comprar Aspose.Page para Java?
 Puedes comprar Aspose.Page para Java[aquí](https://purchase.aspose.com/buy).
### ¿Existe un foro para discusiones sobre Aspose.Page?
 Sí, puedes unirte al foro de la comunidad.[aquí](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
