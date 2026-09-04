---
date: 2026-06-20
description: Aprende cómo establecer el tamaño de página A4, crear archivos PostScript
  en Java y añadir fuentes personalizadas usando Aspose.Page. ¡Prueba la versión de
  prueba gratuita hoy!
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: Crear documento en Java con PostScript
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: Cómo establecer el tamaño de página A4 y crear PostScript en Java con Aspose.Page
url: /es/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer el tamaño de página A4 y crear PostScript en Java con Aspose.Page

## Introducción
Si necesita **establecer el tamaño de página a4** mientras genera archivos PostScript desde Java, Aspose.Page ofrece una API rápida y confiable que oculta los detalles de bajo nivel. En este tutorial recorreremos todo el flujo de trabajo: crear un documento PostScript, configurar las dimensiones de página A4 y **agregar fuentes personalizadas** cuando sea necesario. Al final tendrá un fragmento de código listo para usar que podrá insertar en cualquier proyecto Java.

## Respuestas rápidas
- **¿Qué biblioteca crea PostScript en Java?** Aspose.Page for Java.  
- **¿Qué tamaño de página aborda esta guía?** A4 (210 mm × 297 mm).  
- **¿Puedo incrustar mis propias fuentes?** Sí – establezca la carpeta de fuentes adicionales en las opciones de guardado.  
- **¿Necesito una licencia para producción?** Se requiere una licencia comercial; hay una prueba gratuita disponible.  
- **¿Qué versiones de Java son compatibles?** Java 8 y posteriores.

## Cómo establecer el tamaño de página a4 y crear postscript en Java
Cargue la biblioteca Aspose.Page, configure `PsSaveOptions` con las constantes A4 y escriba el documento en un archivo, todo en menos de diez líneas de código. Este enfoque directo garantiza las dimensiones correctas de la página y le permite agregar fuentes personalizadas sin configuración adicional.

## ¿Qué es el tamaño A4 en PostScript?
El tamaño A4 de PostScript es el estándar ISO 216 (210 mm × 297 mm) expresado en el lenguaje de descripción de páginas PostScript. Define el área imprimible que las impresoras y visores interpretan, asegurando un diseño consistente en todas las plataformas. Dado que PostScript describe el contenido de la página de forma independiente del dispositivo, usar el tamaño A4 garantiza que el documento se vea igual en cualquier impresora o visor compatible con A4 en todo el mundo.

## ¿Por qué usar Aspose.Page para establecer el tamaño de página PostScript?
Aspose.Page admite **más de 30 operadores PostScript** y puede generar archivos de hasta **500 MB** sin cargar todo el documento en memoria. Esto le brinda un control preciso sobre las dimensiones de la página mientras maneja grandes cargas de trabajo de manera eficiente. La biblioteca también abstrae la sintaxis compleja de PostScript, gestiona recursos automáticamente y ofrece transmisión de alto rendimiento, lo que la hace ideal tanto para folletos simples de una página como para informes complejos de varias páginas.

## Cómo agregar fuentes personalizadas en Java
Incrustar sus propias tipografías garantiza que el documento generado se vea exactamente como se diseñó en cualquier impresora o visor, y Aspose.Page descubre automáticamente las fuentes ubicadas en la carpeta especificada. Al registrar una carpeta de fuentes adicional, puede usar cualquier fuente TrueType u OpenType, evitar sustituciones de respaldo y mantener la consistencia de la marca en todos los dispositivos de salida.

## Requisitos previos
- Conocimientos prácticos de programación Java.  
- Aspose.Page para Java instalado. Puede descargarlo [aquí](https://releases.aspose.com/page/java/).  
- Una carpeta llamada `necessary_fonts` (o cualquier nombre que prefiera) que contenga las fuentes personalizadas que desea incrustar.

## Importar paquetes
En su proyecto Java, importe las clases necesarias de Aspose.Page:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Ahora vamos a dividir el ejemplo en pasos claros y numerados.

### Paso 1: Establecer el directorio del documento
La constante `OUTPUT_DIR` indica a la biblioteca dónde escribir el archivo generado.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Paso 2: Definir la carpeta de fuentes
`FONTS_FOLDER` apunta al directorio que contiene sus fuentes TrueType u OpenType personalizadas.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Paso 3: Crear el flujo de salida para el documento PostScript
`FileOutputStream` abre un flujo que recibirá la salida final de PostScript A4.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Paso 4: Crear opciones de guardado con tamaño A4
`PsSaveOptions` le permite especificar el tamaño de página objetivo.  
**Definición:** `PsPageSize` es una enumeración que contiene constantes de tamaños de página estándar como A4, Letter y Legal.  
Establecer `options.setPageSize(PsPageSize.A4)` configura el documento con dimensiones estándar A4.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Paso 5: Establecer márgenes de página y agregar la carpeta de fuentes personalizadas
`options.setMargins(0, 0, 0, 0)` elimina todos los márgenes para una página sin bordes, y `options.setAdditionalFontsFolder(FONTS_FOLDER)` registra sus fuentes personalizadas.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Paso 6: Crear un documento PS multipágina o de una sola página
`PsDocument document = new PsDocument(outputStream, options)` crea el documento. `PsDocument` representa un documento PostScript que puede contener una o varias páginas. Establezca `multiPaged` en `true` para salida multipágina.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Paso 7: Cerrar la página actual y guardar el documento
Llamar a `document.close()` finaliza el archivo y escribe la salida de **tamaño PostScript A4** en el disco.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Problemas comunes y consejos
- **¿La fuente no aparece?** Verifique que el archivo de fuente sea un formato TrueType u OpenType compatible y que `FONTS_FOLDER` termine con una barra (`/`).  
- **¿Los márgenes siguen apareciendo?** Llame a `options.setMargins(...)` **antes** de construir el `PsDocument`.  
- **¿La salida multipágina se ve en blanco?** Recuerde invocar `document.newPage()` para cada página adicional que necesite.

## Preguntas frecuentes

**Q: ¿Puedo usar fuentes personalizadas en mi documento PostScript?**  
A: Sí, establezca la carpeta de fuentes adicionales en las opciones de guardado (ver Paso 5) y Aspose.Page incrustará las fuentes automáticamente.

**Q: ¿Hay una versión de prueba disponible para Aspose.Page para Java?**  
A: Sí, puede obtener una prueba gratuita [aquí](https://releases.aspose.com/).

**Q: ¿Cómo puedo acceder a la referencia completa de la API?**  
A: Consulte la documentación [aquí](https://reference.aspose.com/page/java/).

**Q: ¿Dónde puedo comprar una licencia para Aspose.Page para Java?**  
A: Puede comprar una licencia [aquí](https://purchase.aspose.com/buy).

**Q: ¿Dónde puedo preguntar a la comunidad para obtener ayuda?**  
A: Visite el foro de Aspose.Page [forum](https://forum.aspose.com/c/page/39).

**Q: ¿Puedo generar archivos PostScript multipágina?**  
A: Absolutamente—establezca `multiPaged` en `true` en el Paso 6 y llame a `document.newPage()` para cada página extra.

## Conclusión
Al seguir estos pasos ahora sabe **cómo establecer el tamaño de página a4** y crear archivos **PostScript** en Java con Aspose.Page, además de poder **agregar fuentes personalizadas en Java** y controlar las opciones de tamaño de página. Aspose.Page se encarga del trabajo pesado, para que pueda centrarse en el contenido de sus documentos.

---

**Última actualización:** 2026-06-20  
**Probado con:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Tutorial de Aspose.Page Java – establecer tamaño de página personalizado mientras se agregan páginas en PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [Cómo agregar texto en PostScript con Aspose.Page para Java](/page/java/postscript-text-manipulation/)
- [Tutorial de Aspose Page Java - Convertir PostScript a PDF](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```