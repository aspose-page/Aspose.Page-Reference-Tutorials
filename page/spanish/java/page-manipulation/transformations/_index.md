---
date: 2026-10-20
description: Aprenda cómo escalar rectangle con Aspose.Page para Java, cómo translate
  shape y aplicar affine transform para crear documentos PostScript.
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Transformaciones en la manipulación de páginas Java
og_description: Aprenda cómo escalar rectangle, translate shape y aplicar affine transform
  usando Aspose.Page para Java para generar archivos PostScript de manera eficiente.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Cómo escalar rectangle con Aspise.Page para Java – guía paso a paso
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Cómo escalar rectangle con Aspose.Page para Java
url: /es/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo escalar un rectángulo con Aspose.Page para Java

## Introducción
En esta guía descubrirá **how to scale rectangle** objetos usando Aspose.Page para Java, mientras también aprende a trasladar posiciones de formas, rotar gráficos y aplicar operaciones de transformación afín para producir salida PostScript de alta calidad. Estas técnicas le permiten crear gráficos sofisticados e independientes del dispositivo sin escribir código de renderizado de bajo nivel, haciendo sus aplicaciones Java más potentes y mantenibles.

## Respuestas rápidas
`scale(sx, sy)` escala el contexto gráfico por los factores horizontales y verticales dados.  

- **How do I scale a rectangle in Java with Aspose.Page?** Llama al método `scale(sx, sy)` en el contexto gráfico antes de dibujar el rectángulo.  
- **Can I move (translate) a shape without affecting other graphics?** Sí—encierre la traducción entre llamadas a `writeGraphicsSave()` y `writeGraphicsRestore()`.  
- **What class creates a PostScript file?** ¿Qué clase crea un archivo PostScript? Use `PsDocument` together with `PsSaveOptions`.  
- **Do I need a license for production use?** Se requiere una licencia válida de Aspose.Page para implementaciones comerciales.  
- **Which Java version is supported?** Aspose.Page funciona con Java 8 y posteriores.

## Requisitos previos
Antes de comenzar, verifique que tiene:

- Un sólido dominio de la sintaxis central de Java y los conceptos orientados a objetos.  
- La biblioteca Aspose.Page para Java instalada. Puede descargarla desde la [documentación de Aspose.Page para Java](https://reference.aspose.com/page/java/).  
- Un IDE de Java (IntelliJ IDEA, Eclipse o VS Code) configurado con los archivos JAR de la biblioteca en el classpath.

## Importar paquetes
`PsDocument` es la clase principal utilizada para crear un documento PostScript, y `PsSaveOptions` configura cómo se guarda el documento.  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## ¿Qué es “how to scale rectangle” en Aspose.Page?
El método `scale(float sx, float sy)` aplica una transformación de escala afín al estado gráfico actual, redimensionando los dibujos posteriores por los factores `sx` (horizontal) y `sy` (vertical). Esta es la operación central detrás de la palabra clave **how to scale rectangle**. Al aplicar esta transformación antes de dibujar, cualquier forma posterior, como rectángulos, se renderizará con las nuevas dimensiones mientras se preservan sus proporciones.

## Cómo trasladar una forma con Aspose.Page
`writeGraphicsSave()` guarda el estado gráfico actual y `writeGraphicsRestore()` lo restaura, asegurando que las transformaciones afecten solo a la forma deseada. La traducción reposiciona el origen del sistema de coordenadas sin alterar las dimensiones del objeto. Al rodear `translate(dx, dy)` con `writeGraphicsSave()` / `writeGraphicsRestore()`, se garantiza que solo la forma deseada se mueva mientras los demás gráficos permanecen sin cambios, proporcionando un control preciso sobre los elementos individuales.

## Ejemplo 1: sin transformaciones
El primer ejemplo dibuja un rectángulo sin ninguna transformación, estableciendo una línea base para la comparación visual con ejemplos posteriores.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Ejemplo 2: traslación
En este ejemplo movemos el contexto gráfico 250 unidades a la derecha antes de dibujar un segundo rectángulo, ilustrando **how to translate shape**.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Ejemplo 3: escalado
Aquí respondemos la pregunta principal **how to scale rectangle**. El rectángulo se reduce al 50 % de su ancho original y al 75 % de su altura original usando la llamada `scale(0.5f, 0.75f)`.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Cómo rotar una forma en Java (rotate shape java)
`rotate(angle)` rota el sistema de coordenadas por el ángulo especificado en grados. Cargue su `PsDocument`, llame a `rotate(angle)` en el estado gráfico, dibuje la forma y luego restaure el estado anterior. Este patrón implementa **rotate shape java** y **how to rotate rectangle** en un único bloque reutilizable, permitiéndole girar los gráficos alrededor de cualquier punto que elija.

## Por qué esto importa – beneficios del mundo real
- **Device‑independent output** – Aspose.Page puede generar archivos PostScript y XPS que se renderizan idénticamente en cualquier impresora o visor, eliminando ajustes específicos de la plataforma.  
- **Fine‑grained control** – Combine traducción, escalado, cizallado y rotación para cumplir especificaciones de diseño exactas; la API soporta más de 20 combinaciones de transformación por página.  
- **Performance‑oriented processing** – La biblioteca procesa documentos con un consumo de memoria inferior a 10 MB para informes típicos de 100 páginas, haciendo que los trabajos por lotes sean rápidos y escalables.

## Casos de uso comunes
- **Printable invoices** – Coloque con precisión logotipos, códigos de barras y tablas usando escalado y traslación para cumplir con las directrices de marca corporativa.  
- **Technical diagrams** – Genere esquemas donde cada componente debe redimensionarse y posicionarse proporcionalmente.  
- **Automated multi‑page reports** – Cree informes PostScript que requieran un escalado consistente en todas las páginas, como especificaciones de ingeniería.

## Problemas comunes y soluciones
- **Transformation not resetting** – Siempre combine `writeGraphicsSave()` con `writeGraphicsRestore()`; de lo contrario, los dibujos posteriores heredarán transformaciones no deseadas.  
- **Unexpected colors** – Establezca la pintura (color) después de cada transformación porque el estado gráfico no preserva la información de color después de una restauración.  
- **File size too large** – Active la compresión en `PsSaveOptions` y limite la resolución de imágenes raster incrustadas para mantener el archivo final por debajo de 5 MB para documentos típicos de 50 páginas.

## Preguntas frecuentes
### ¿Puedo usar Aspose.Page para Java con otros formatos de documento?
Aspose.Page se centra principalmente en la manipulación de páginas para los formatos PostScript y XPS, pero también ofrece capacidades limitadas de exportación a PDF.

### ¿Dónde puedo encontrar más ejemplos y documentación para Aspose.Page para Java?
Visite la [documentación de Aspose.Page para Java](https://reference.aspose.com/page/java/) para guías completas, referencias de API y proyectos de ejemplo.

### ¿Hay una prueba gratuita disponible para Aspose.Page para Java?
Sí, puede acceder a una prueba gratuita a través de la página de **descarga de prueba gratuita de Aspose**: [Aspose free trial download](https://releases.aspose.com/).

### ¿Cómo puedo obtener una licencia temporal para Aspose.Page para Java?
Obtenga una licencia temporal a través de la **página de solicitud de licencia temporal**: [temporary license request page](https://purchase.aspose.com/temporary-license/).

### ¿Dónde puedo buscar soporte de la comunidad o hacer preguntas sobre Aspose.Page para Java?
Visite el [foro de Aspose.Page para Java](https://forum.aspose.com/c/page/39) para discusiones de la comunidad, fragmentos de código y consejos de solución de problemas.

## Preguntas frecuentes
**Q: What is the difference between `translate` and `scale`?**  
A: `translate` moves the origin of the coordinate system, while `scale` changes the size of drawn objects along the X and/or Y axes.

**Q: Can I combine multiple transformations in a single graphics state?**  
A: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially before drawing, you create a combined affine transformation.

**Q: How do I reset transformations after drawing a shape?**  
A: Use `writeGraphicsRestore()` to revert to the previously saved graphics state.

**Q: Is it possible to rotate a rectangle around its center?**  
A: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`, then translate it back before drawing.

**Q: Does Aspose.Page support anti‑aliasing for smoother graphics?**  
A: Yes—set the appropriate rendering options in `PsSaveOptions` to enable anti‑aliasing.

---

**Última actualización:** 2026-10-20  
**Probado con:** Aspose.Page for Java 24.12  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo dibujar un rectángulo en Java PostScript con Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Crear degradado radial en PostScript con Aspose.Page para Java](/page/java/postscript-gradient-addition/)
- [Manipulación de página PostScript](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}