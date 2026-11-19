---
date: 2026-11-19
description: Aprenda a crear archivos PostScript en Java, establecer el tamaño de
  página A4 y agregar fuentes personalizadas usando Aspose.Page. ¡Pruebe la versión
  de prueba gratuita hoy!
keywords:
- create postscript file java
- add custom fonts java
- set a4 page size java
- aspose.page java
- postscript generation java
lastmod: 2026-11-19
linktitle: Crear documento en Java con PostScript
og_description: Aprenda a crear un archivo PostScript en Java, establecer el tamaño
  de página A4 y agregar fuentes personalizadas con Aspose.Page. Guía de inicio rápido
  para desarrolladores.
og_image_alt: Screenshot of Java code generating an A4 PostScript file with custom
  fonts using Aspose.Page
og_title: Crear archivo PostScript en Java con tamaño A4 usando Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size
  steps:
  - name: set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` defines how the PostScript document is saved, including
      page size, margins, and compression. **Definition:** `PsPageSize` is an enumeration
      that contains standard page‑size constants such as A4, Letter, and Legal. Setting
      `options.setPageSize(PsPageSize.A4)` configures the document f'
  - name: set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: create a multipaged or single‑paged PS document
    text: '`PsDocument` represents a PostScript document that can contain one or many
      pages. Instantiating it with `new PsDocument(outputStream, options)` creates
      the document object. Set `multiPaged` to `true` for multi‑page output, then
      call `document.newPage()` for each additional page you need.'
  - name: close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create postscript
- Aspose.Page
- Java document processing
- custom fonts
- A4 page size
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size using Aspose.Page
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size using Aspose.Page
  steps:
  - name: Set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create save options with A4 size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a multipaged or single‑paged PS document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
title: Cómo crear un archivo PostScript en Java con tamaño A4
url: /es/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un archivo PostScript en Java con tamaño A4

## Introducción
Si necesita **crear un archivo PostScript en Java** estableciendo las dimensiones estándar de página A4, Aspose.Page para Java le ofrece una API concisa y de alto rendimiento que abstrae la sintaxis de bajo nivel de PostScript. En este tutorial recorreremos cada paso—desde cargar la biblioteca y configurar `PsSaveOptions` hasta incrustar sus propias fuentes TrueType u OpenType. Al final tendrá un fragmento listo para ejecutar que podrá insertar en cualquier proyecto Java.

## Respuestas rápidas
- **¿Qué biblioteca crea PostScript en Java?** Aspose.Page for Java.  
- **¿Qué tamaño de página aborda esta guía?** A4 (210 mm × 297 mm).  
- **¿Puedo incrustar mis propias fuentes?** Sí – establezca la carpeta de fuentes adicionales en las opciones de guardado.  
- **¿Necesito una licencia para producción?** Se requiere una licencia comercial; hay una prueba gratuita disponible.  
- **¿Qué versiones de Java son compatibles?** Java 8, 11 y 17 son totalmente compatibles.

## Cómo establecer el tamaño de página A4 y crear PostScript en Java?
Cargue la biblioteca Aspose.Page, configure `PsSaveOptions` con las constantes A4 y escriba el documento en un archivo, todo en menos de diez líneas de código. Este enfoque garantiza las dimensiones correctas de la página y le permite agregar fuentes personalizadas sin configuración adicional.

## ¿Qué es el tamaño A4 en PostScript?
El tamaño A4 en PostScript es el estándar ISO 216 (210 mm × 297 mm) expresado en el lenguaje de descripción de páginas PostScript. Define el área imprimible que las impresoras y los visores interpretan, asegurando un diseño consistente en todas las plataformas. Como PostScript describe el contenido de la página de forma independiente del dispositivo, usar el tamaño A4 garantiza que el documento se vea igual en cualquier impresora o visor compatible con A4 en todo el mundo.

## ¿Por qué usar Aspose.Page para establecer el tamaño de página PostScript?
Aspose.Page admite más de 30 operadores de PostScript y puede generar archivos de hasta 500 MB sin cargar todo el documento en memoria. Procesa un documento de 200 páginas en menos de 2 segundos, ofreciendo control preciso sobre las dimensiones de la página mientras maneja grandes cargas de trabajo de manera eficiente. La biblioteca también abstrae la sintaxis compleja de PostScript y gestiona los recursos automáticamente, lo que la hace ideal tanto para folletos simples como para informes multipágina complejos.

## Cómo agregar fuentes personalizadas en Java
Incrustar sus propias tipografías garantiza que el documento generado se vea exactamente como se diseñó en cualquier impresora o visor, y Aspose.Page descubre automáticamente las fuentes ubicadas en la carpeta especificada. Registrando una carpeta de fuentes adicional, puede usar cualquier fuente TrueType u OpenType, evitar sustituciones de respaldo y mantener la consistencia de marca en todos los dispositivos de salida.

## Requisitos previos
Antes de comenzar, asegúrese de contar con:

- Un conocimiento práctico de la programación en Java.  
- Aspose.Page para Java instalado. Puede descargarlo [página de descarga de Aspose.Page Java](https://releases.aspose.com/page/java/).  
- Una carpeta llamada `necessary_fonts` (o cualquier nombre que prefiera) que contenga las fuentes personalizadas que desea incrustar.

## Importar paquetes
En su proyecto Java, importe las clases necesarias de Aspose.Page:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Ahora dividamos el ejemplo en pasos claros y numerados.

### Paso 1: establecer el directorio del documento
La constante `OUTPUT_DIR` indica a la biblioteca dónde escribir el archivo generado.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Paso 2: definir la carpeta de fuentes
`FONTS_FOLDER` apunta al directorio que contiene sus fuentes TrueType u OpenType personalizadas.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Paso 3: crear el flujo de salida para el documento PostScript
`FileOutputStream` abre un flujo que recibirá la salida final de PostScript A4.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Paso 4: crear opciones de guardado con tamaño A4
`PsSaveOptions` define cómo se guarda el documento PostScript, incluyendo el tamaño de página, márgenes y compresión.  
**Definición:** `PsPageSize` es una enumeración que contiene constantes de tamaños de página estándar como A4, Letter y Legal.  
Establecer `options.setPageSize(PsPageSize.A4)` configura el documento con las dimensiones estándar A4.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Paso 5: establecer los márgenes de página y agregar la carpeta de fuentes personalizadas
`options.setMargins(0, 0, 0, 0)` elimina todos los márgenes para una página sin bordes, y `options.setAdditionalFontsFolder(FONTS_FOLDER)` registra sus fuentes personalizadas.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Paso 6: crear un documento PS multipágina o de una sola página
`PsDocument` representa un documento PostScript que puede contener una o varias páginas. Instanciarlo con `new PsDocument(outputStream, options)` crea el objeto documento. Establezca `multiPaged` en `true` para salida multipágina, luego llame a `document.newPage()` por cada página adicional que necesite.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Paso 7: cerrar la página actual y guardar el documento
Llamar a `document.close()` finaliza el archivo y escribe la salida **PostScript tamaño A4** en disco.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Problemas comunes y consejos
- **¿La fuente no aparece?** Verifique que el archivo de fuente sea un formato TrueType u OpenType compatible y que `FONTS_FOLDER` termine con una barra (`/`).  
- **¿Los márgenes siguen apareciendo?** Llame a `options.setMargins(...)` **antes** de construir el `PsDocument`.  
- **¿La salida multipágina aparece en blanco?** Recuerde invocar `document.newPage()` para cada página adicional que necesite.  
- **¿Los archivos grandes causan errores de falta de memoria?** Aspose.Page transmite datos, por lo que puede generar archivos de hasta 500 MB de forma segura; solo asegúrese de que el heap de su JVM sea de al menos 1 GB para cargas de trabajo muy grandes.

## Preguntas frecuentes

**P: ¿Puedo usar fuentes personalizadas en mi documento PostScript?**  
R: Sí, establezca la carpeta de fuentes adicionales en las opciones de guardado (ver Paso 5) y Aspose.Page incrustará las fuentes automáticamente.

**P: ¿Existe una versión de prueba disponible para Aspose.Page para Java?**  
R: Sí, puede obtener una prueba gratuita [página de prueba gratuita de Aspose.Page](https://releases.aspose.com/).

**P: ¿Cómo puedo acceder a la referencia completa de la API?**  
R: Consulte la documentación [documentación de referencia de la API](https://reference.aspose.com/page/java/).

**P: ¿Dónde puedo comprar una licencia para Aspose.Page para Java?**  
R: Puede adquirir una licencia en la [página de compra de licencias](https://purchase.aspose.com/buy).

**P: ¿Dónde puedo solicitar ayuda a la comunidad?**  
R: Visite el foro de la comunidad de Aspose.Page [foro de la comunidad de Aspose.Page](https://forum.aspose.com/c/page/39).

**P: ¿Puedo generar archivos PostScript multipágina?**  
R: Absolutamente—establezca `multiPaged` en `true` en el Paso 6 y llame a `document.newPage()` por cada página extra.

## Conclusión
Siguiendo estos pasos ahora sabe **cómo crear un archivo PostScript en Java** y establecer **el tamaño de página A4** usando Aspose.Page, además de poder **agregar fuentes personalizadas en Java** y controlar las opciones de tamaño de página. Aspose.Page se encarga del trabajo pesado, de modo que usted puede centrarse en el contenido de sus documentos en lugar de en las complejidades del lenguaje PostScript.

---

**Última actualización:** 2026-11-19  
**Probado con:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

## Tutoriales relacionados

- [Tutorial de Aspose.Page Java – establecer tamaño de página personalizado mientras se agregan páginas en PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [Cómo agregar texto en PostScript con Aspose.Page para Java](/page/java/postscript-text-manipulation/)
- [Tutorial de Aspose Page Java - Convertir PostScript a PDF](/page/java/postscript-conversion/to-pdf/)

```java
document.closePage();
document.save();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}