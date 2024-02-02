---
title: Agregar patrón de sombreado en Java PostScript
linktitle: Agregar patrón de sombreado en Java PostScript
second_title: API de Java de Aspose.Page
description: Aprenda cómo agregar patrones de sombreado cautivadores a documentos Java PostScript usando Aspose.Page. Eleve su contenido visual sin esfuerzo.
type: docs
weight: 10
url: /es/java/postscript-hatch-patterns/add-hatch-pattern/
---
## Introducción
En el mundo de la programación Java, mejorar los elementos visuales es un requisito común para los desarrolladores. Una mejora visual interesante es la adición de patrones de sombreado a los documentos PostScript. Este tutorial lo guiará a través del proceso de agregar patrones de sombreado usando Aspose.Page para Java.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener la siguiente configuración:
- Entorno de desarrollo Java: asegúrese de tener listo un entorno de desarrollo Java.
-  Biblioteca Aspose.Page para Java: descargue e instale la biblioteca Aspose.Page para Java. Puedes encontrar los archivos necesarios.[aquí](https://releases.aspose.com/page/java/).
## Importar paquetes
Para comenzar, importe los paquetes necesarios a su proyecto Java. Utilice el siguiente fragmento de código:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Paso 1: configurar los parámetros iniciales
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear flujo de salida para un documento PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Crea opciones de guardado con tamaño A4
PsSaveOptions options = new PsSaveOptions();
// Cree un nuevo documento PS con la página abierta
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```
## Paso 2: guardar el estado de los gráficos y traducir
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```
## Paso 3: crea un cuadrado para cada patrón
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```
## Paso 4: configurar el lápiz para el contorno del cuadrado del patrón
```java
BasicStroke stroke = new BasicStroke(2);
```
## Paso 5: iterar a través de patrones de sombreado
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continúa con el código proporcionado)
}
```
## Paso 6: restaurar el estado de los gráficos
```java
document.writeGraphicsRestore();
```
## Paso 7: Rellene el texto con un patrón de sombreado
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```
## Paso 8: delinear el texto con un patrón de sombreado
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```
## Paso 9: cerrar y guardar el documento
```java
document.closePage();
document.save();
```
Siga estos pasos y agregará con éxito patrones de sombreado a su documento Java PostScript usando Aspose.Page.
## Conclusión
La incorporación de elementos visuales como patrones de sombreado puede mejorar significativamente el atractivo de sus aplicaciones Java. Aspose.Page para Java hace que este proceso sea fluido, permitiéndole crear documentos PostScript visualmente impresionantes sin esfuerzo.
## Preguntas frecuentes
### ¿Puedo usar Aspose.Page para Java con otros marcos de Java?
Sí, Aspose.Page para Java está diseñado para integrarse perfectamente con varios marcos de Java.
### ¿Hay una versión de prueba disponible para Aspose.Page para Java?
 Sí, puedes acceder a la prueba gratuita.[aquí](https://releases.aspose.com/).
### ¿Cómo puedo obtener una licencia temporal de Aspose.Page para Java?
 Puedes adquirir una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Dónde puedo encontrar más tutoriales y soporte para Aspose.Page para Java?
 Explorar el[Aspose.Page para el foro de Java](https://forum.aspose.com/c/page/39) para tutoriales y apoyo de la comunidad.
### ¿Existe un recurso de documentación completo para Aspose.Page para Java?
 Sí, consulte la documentación.[aquí](https://reference.aspose.com/page/java/).