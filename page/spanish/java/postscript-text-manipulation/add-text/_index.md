---
date: 2025-12-14
description: Aprende cómo establecer el color del texto en Java usando Aspose.Page
  para Java, agregar texto a PostScript y aplicar trazo al texto para un estilo de
  documento enriquecido.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Establecer color de texto en Java con Aspose.Page – Guía de manipulación de
  texto
url: /es/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Establecer color de texto Java con Aspose.Page – Guía de manipulación de texto

## Introducción
Bienvenido a nuestra guía paso a paso sobre **set text color java** mientras trabajas con archivos PostScript usando Aspose.Page para Java. Aspose.Page para Java es una biblioteca poderosa que permite a los desarrolladores crear y **generate postscript file** documentos, manipular fuentes y dar estilo al texto con precisión. En este tutorial aprenderás a agregar texto, cambiar su color, ajustar el tamaño e incluso **apply stroke text** para obtener un aspecto pulido.

## Respuestas rápidas
- **¿Qué biblioteca me permite establecer el color del texto en Java?** Aspose.Page for Java.
- **¿Puedo usar fuentes del sistema y fuentes personalizadas?** Sí, ambas son compatibles.
- **¿Cómo cambio el tamaño del texto?** Especificando el tamaño de la fuente al crear el `Font` o `DrFont`.
- **¿Es posible delinear y rellenar texto al mismo tiempo?** Absolutamente – usa `fillAndStrokeText`.
- **¿Qué formato de salida produce este tutorial?** Un documento PostScript (`.ps`).

## ¿Qué es “set text color java”?
Establecer el color del texto en Java significa definir el objeto `Color` que el motor de renderizado (aquí, Aspose.Page) utiliza al dibujar caracteres en una página. Esta operación es esencial para crear documentos visualmente distintos, especialmente al generar **postscript documents** de forma programada.

## ¿Por qué usar Aspose.Page para Java?
- **Control total** sobre la generación de PostScript sin necesidad de un intérprete nativo de PostScript.
- **Compatibilidad con fuentes del sistema y externas**, lo que te permite incrustar cualquier tipografía que necesites.
- **API fácil** para rellenar, delinear y **fill and stroke text**, brindándote flexibilidad en el estilo.
- **Compatibilidad multiplataforma** – escribe una vez, ejecuta donde Java se ejecute.

## Requisitos previos
- Conocimientos básicos de programación en Java.
- Biblioteca Aspose.Page para Java instalada. Puedes descargarla desde la [Aspose.Page for Java download page](https://releases.aspose.com/page/java/).
- Fuentes necesarias disponibles en la carpeta especificada. Detalles adicionales están en la [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).

## Importar paquetes
En tu proyecto Java, importa los paquetes necesarios para Aspose.Page para Java:

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

## Paso 1: Configurar el documento
Primero, creamos un nuevo **PostScript document** y configuramos las opciones de salida.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Cómo establecer color de texto Java usando fuente del sistema
Ahora demostramos **set text color java** con una fuente proporcionada por el sistema.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Consejo:** El método `fillText` usa automáticamente el color actual si no pasas un argumento `Color`, que por defecto es negro.

## Uso de fuente personalizada y cambio de tamaño de texto
También puedes **change text size** y usar una fuente personalizada almacenada en tu carpeta de fuentes.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Delineado (Stroke) de texto – Aplicar Stroke Text
Delimitar el texto le da un borde nítido. Aquí **apply stroke text** usando un `BasicStroke`.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## Delineado de texto con fuente personalizada
La misma técnica funciona con fuentes personalizadas.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Paso 6: Guardar el documento
Finalmente, cierra la página y escribe el archivo en disco.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| **Font not found** | Asegúrate de que el archivo de fuente esté colocado en `necessary_fonts` y que la ruta de la carpeta se haya añadido correctamente mediante `options.setAdditionalFontsFolders`. |
| **Color not applied** | Verifica que estés llamando a la sobrecarga de `fillText` o `outlineText` que incluye un argumento `Color`. |
| **Stroke appears too thin** | Incrementa el ancho de `BasicStroke` (p.ej., `new BasicStroke(3)`). |
| **Document not opening** | Confirma que el archivo `.ps` generado se guarde con la extensión correcta y que tu visor soporte PostScript. |

## Preguntas frecuentes

**Q:** ¿Puedo usar mis propias fuentes personalizadas con Aspose.Page para Java?  
A: Sí, puedes usar fuentes personalizadas especificando el nombre y tamaño de la fuente en la clase `DrFont`.

**Q:** ¿Cómo puedo cambiar el color del texto?  
A: Puedes establecer el color deseado usando la clase `Color` al rellenar o delinear el texto.

**Q:** ¿Es posible agregar múltiples páginas a un documento PostScript?  
A: ¡Absolutamente! Puedes crear varias páginas repitiendo los pasos de creación y guardado del documento.

**Q:** ¿Cuál es el propósito de la clase `ExternalFontCache`?  
A: `ExternalFontCache` se utiliza para obtener fuentes personalizadas, asegurando que estén disponibles para la manipulación de texto.

**Q:** ¿Puedo aplicar diferentes trazos al texto delineado?  
A: Sí, puedes personalizar el ancho y el color del trazo usando la clase `Stroke` y la clase `Color`, respectivamente.

## Conclusión
¡Felicidades! Ahora sabes cómo **set text color java**, cambiar tamaños de fuente, **apply stroke text**, y **create postscript document** usando Aspose.Page para Java. Experimenta con diferentes fuentes, colores y estilos de contorno para producir salida PostScript de aspecto profesional.

---

**Última actualización:** 2025-12-14  
**Probado con:** Aspose.Page for Java 23.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}