---
title: Manipulación de texto Java de Aspose.Page
linktitle: Agregar texto en Java PostScript
second_title: API de Java de Aspose.Page
description: Explore el poder de Aspose.Page para Java en nuestro tutorial sobre cómo agregar texto a documentos PostScript. Aprenda a utilizar el sistema y las fuentes personalizadas con facilidad.
type: docs
weight: 10
url: /es/java/postscript-text-manipulation/add-text/
---
## Introducción
Bienvenido a nuestra guía paso a paso sobre cómo agregar texto en Java PostScript usando Aspose.Page para Java. Aspose.Page para Java es una potente biblioteca que permite a los desarrolladores manipular documentos PostScript con facilidad. En este tutorial, lo guiaremos a través del proceso de agregar texto, usar fuentes personalizadas y del sistema, delinear texto e incorporar trazos para obtener un resultado visualmente atractivo.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
- Conocimientos básicos de programación Java.
-  Aspose.Page para la biblioteca Java instalada. Puedes descargarlo desde el[Aspose.Page para la página de descarga de Java](https://releases.aspose.com/page/java/).
-  Fuentes necesarias disponibles en la carpeta especificada. Puede encontrar información adicional en el[Aspose.Page para la documentación de Java](https://reference.aspose.com/page/java/).
## Importar paquetes
En su proyecto Java, importe los paquetes necesarios para Aspose.Page para Java:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```
## Paso 1: configurar el documento
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Crear flujo de salida para un documento PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Crea opciones de guardado con tamaño A4
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// Un texto para escribir en un archivo PS
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Crear un nuevo documento PS de 1 página
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Paso 2: usar la fuente del sistema para completar el texto
```java
// Usar la fuente del sistema para completar el texto
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Rellenar texto con color predeterminado o ya definido (negro)
document.fillText(str, font, 50, 100);
// Rellenar texto con color azul.
document.fillText(str, font, 50, 150, Color.BLUE);
```
## Paso 3: usar una fuente personalizada para completar el texto
```java
// Usar fuente personalizada para completar texto
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Rellenar texto con color predeterminado o ya definido (negro)
document.fillText(str, drFont, 50, 200);
// Rellenar texto con color azul.
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## Paso 4: delinear el texto con la fuente del sistema
```java
// Usar la fuente del sistema para delinear texto
document.outlineText(str, font, 50, 300);
// Delinee el texto con un bolígrafo de 2 puntos de ancho de color azul violeta
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Rellene el texto con color naranja y trace con un bolígrafo azul de 2 puntos de ancho
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## Paso 5: delinear el texto con una fuente personalizada
```java
// Usar fuente personalizada para delinear texto
document.outlineText(str, drFont, 50, 450);
// Delinee el texto con un bolígrafo de 2 puntos de ancho de color azul violeta
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Rellene el texto con color naranja y trace con un bolígrafo azul de 2 puntos de ancho
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## Paso 6: guarde el documento
```java
// Cerrar la página actual
document.closePage();
// guardar el documento
document.save();
```
## Conclusión
¡Felicidades! Ha aprendido con éxito cómo agregar texto en Java PostScript usando Aspose.Page para Java. Experimente con diferentes fuentes, colores y opciones de contorno para mejorar aún más su documento.
## Preguntas frecuentes
### ¿Puedo usar mis propias fuentes personalizadas con Aspose.Page para Java?
 Sí, puede utilizar fuentes personalizadas especificando el nombre y el tamaño de la fuente en el`DrFont` clase.
### ¿Cómo puedo cambiar el color del texto?
 Puede establecer el color deseado utilizando el`Color` clase a la hora de rellenar o delinear el texto.
### ¿Es posible agregar varias páginas a un documento PostScript?
¡Absolutamente! Puede crear varias páginas repitiendo los pasos de creación y guardado del documento.
###  ¿Cuál es el propósito de la`ExternalFontCache` class?
`ExternalFontCache` se utiliza para buscar fuentes personalizadas, asegurando que estén disponibles para la manipulación de texto.
### ¿Puedo aplicar diferentes trazos al texto delineado?
 Sí, puedes personalizar el ancho y el color del trazo usando el`Stroke` clase y`Color` clase, respectivamente.