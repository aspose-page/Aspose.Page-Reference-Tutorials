---
date: 2026-08-23
description: Aprenda cómo usar aspose.page image manipulation java para incrustar
  y rotar imágenes en archivos PostScript con claros ejemplos en Java.
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: Agregar Imagen en Java PostScript
og_description: Aprenda cómo usar aspose.page image manipulation java para incrustar
  y rotar imágenes en archivos PostScript, con ejemplos de código Java step‑by‑step.
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: Cómo usar aspose.page image manipulation java para agregar una imagen
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: Cómo usar aspose.page image manipulation java para agregar una imagen
url: /es/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo usar aspose.page image manipulation java para agregar una imagen

## Introducción
En este tutorial aprenderá cómo **usar aspose.page image manipulation java** para crear archivos PostScript, incrustar imágenes raster y aplicar transformaciones de traslación y rotación. Al final de la guía podrá generar salida PostScript píxel‑perfecta desde Java, ideal para informes automatizados, flujos de impresión o cualquier proceso que requiera una colocación precisa de imágenes dentro de un documento PostScript.

## Respuestas rápidas
- **¿Qué biblioteca se requiere?** Aspose.Page for Java  
- **¿Puedo agregar múltiples imágenes?** Sí – repita los pasos de transformación y dibujo para cada imagen  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia para producción  
- **¿Qué versión de Java es compatible?** Java 8 y posteriores  
- **¿Se admite la rotación de imágenes?** Absolutamente – use `AffineTransform.rotate()`

## ¿Qué es aspose.page image manipulation java?
`aspose.page image manipulation java` es la API Aspose.Page que le permite crear, editar y renderizar documentos PostScript programáticamente desde código Java, incluyendo control total sobre la colocación, escalado y rotación de imágenes. Con esta API evita la sintaxis de PostScript de bajo nivel y permite que la biblioteca maneje la conversión de formatos y la incrustación internamente.

## ¿Por qué usar aspose.page para la manipulación de imágenes?
Aspose.Page ofrece **más de 50 formatos de imagen** (incluidos JPEG, PNG, BMP, TIFF) y puede incrustarlos en PostScript sin cargar todo el documento en memoria, lo que permite procesar archivos con cientos de páginas manteniendo el uso de memoria por debajo de 100 MB en un servidor típico. La API de alto nivel abstrae los complejos comandos de PostScript, de modo que escribe código Java conciso en lugar de operadores PS sin procesar.

## Requisitos previos
- Java Development Kit (JDK) 8 o superior instalado.  
- Biblioteca Aspose.Page for Java – descárguela **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)**.  
- Familiaridad básica con la sintaxis de Java y la programación orientada a objetos.

## ¿Qué es crear PostScript con Java?
Crear un archivo PostScript desde Java significa generar programáticamente un documento `.ps` que describe el diseño de página, gráficos vectoriales e imágenes raster mediante el lenguaje PostScript. Aspose.Page traduce sus llamadas Java en instrucciones PostScript válidas, lo que le permite producir archivos listos para imprimir sin un intérprete PostScript separado.

## Cómo agregar una imagen con traslación y rotación paso a paso

Cargue su imagen, aplique un `AffineTransform` y dibújela en la página. Los siguientes pasos describen la secuencia exacta que debe seguir.

### Paso 1: guardar estado gráfico
Guardar el estado gráfico aísla sus transformaciones para que pueda revertirlas más tarde. Esto equivale al operador `gsave` en PostScript puro.

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Paso 2: trasladar y transformar (trasladar y rotar la imagen)
Primero, cree un `BufferedImage` a partir del archivo fuente, luego construya un `AffineTransform` que traslade la imagen a las coordenadas deseadas y la rote alrededor de su centro. `AffineTransform.rotate` espera un ángulo en radianes, por lo que convierta los grados con `Math.toRadians(degrees)`.

**AffineTransform** es una clase Java que representa una transformación afín 2‑D como traslación, rotación, escalado o sesgado.  
**BufferedImage** es una clase Java que almacena una imagen en memoria como un ráster de píxeles.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

### Paso 3: agregar imagen al documento
Después de configurar la transformación, dibuje la imagen en la página actual. La biblioteca convierte automáticamente el `BufferedImage` en un flujo de imagen PostScript apropiado.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

### Paso 4: restaurar estado gráfico
Llamar a restaurar (`grestore`) devuelve el estado gráfico a como estaba antes del guardado, asegurando que los comandos de dibujo posteriores no se vean afectados por la transformación anterior.

```java
document.drawImage(image, transform, null);
```

### Paso 5: cerrar página actual y guardar
Finalice la página, cierre el documento y escriba el archivo de salida en disco.

```java
document.writeGraphicsRestore();
```

Puede repetir la secuencia anterior para incrustar imágenes adicionales, ajustando las coordenadas de traslación y el ángulo de rotación cada vez.

## Problemas comunes y soluciones
- **FileNotFoundException:** Verifique que `dataDir` termine con un separador de archivos (`/` o `\\`) y que el nombre del archivo de imagen coincida exactamente.  
- **ImageIO.read returns null:** Asegúrese de que el formato de la imagen esté en la lista de formatos compatibles (JPEG, PNG, BMP, GIF, TIFF).  
- **Ángulo de rotación incorrecto:** `AffineTransform.rotate` funciona con radianes; use `Math.toRadians(degrees)` para convertir de grados.  
- **Picos de memoria en páginas grandes:** Use `Document.save` con `saveOptions.setCompress(true)` para reducir la huella de memoria.

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Page for Java con otros lenguajes de programación?**  
R: La biblioteca central es solo Java, pero Aspose ofrece APIs equivalentes para .NET, C++ y Python, cada una adaptada a su plataforma.

**P: ¿Hay una prueba gratuita disponible para Aspose.Page for Java?**  
R: Sí, puede acceder a la prueba gratuita **[Aspose.Page free trial page](https://releases.aspose.com/)**.

**P: ¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?**  
R: Puede obtener una licencia temporal **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

**P: ¿Dónde puedo encontrar soporte comunitario y discusiones relacionadas con Aspose.Page for Java?**  
R: Visite el **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** para obtener ayuda de la comunidad.

**P: ¿Hay recursos adicionales para comprar Aspose.Page for Java?**  
R: Puede comprar la biblioteca **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.

## Conclusión
Ahora tiene un ejemplo completo, de extremo a extremo, de **aspose.page image manipulation java** que crea un archivo PostScript, traslada y rota una imagen, y guarda el resultado. Explore la **[documentation](https://reference.aspose.com/page/java/)** completa para descubrir funciones avanzadas como gráficos vectoriales, tamaños de página personalizados y renderizado de texto.

---

**Última actualización:** 2026-08-23  
**Probado con:** Aspose.Page for Java 23.11  
**Autor:** Aspose  








```java
document.closePage();
document.save();
```

## Tutoriales relacionados

- [Cómo convertir PostScript a PDF usando Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Cómo agregar degradado: Degradado diagonal en Java PostScript usando Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Cómo agregar patrón de trama en Java PostScript con Aspose.Page](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}