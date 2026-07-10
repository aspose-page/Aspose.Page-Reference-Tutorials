---
date: 2026-07-10
description: Aprenda cómo crear documentos XPS con aspose.page usando Aspose.Page
  para .NET – una guía paso a paso para generar archivos XPS de alta calidad.
keywords:
- aspose.page create xps
- XPS document generation
- Aspose.Page .NET
lastmod: 2026-07-10
linktitle: Crear documento XPS
og_description: aspose.page create xps rápidamente con Aspose.Page para .NET. Siga
  esta guía para producir archivos XPS de alta calidad en menos de 20 líneas de código.
og_image_alt: 'Guide: Create XPS document using Aspose.Page for .NET'
og_title: aspose.page create xps – Generar documentos XPS con .NET
schemas:
- author: Aspose
  dateModified: '2026-07-10'
  description: Learn how to aspose.page create xps documents using Aspose.Page for
    .NET – a step‑by‑step guide to generate high‑quality XPS files.
  headline: aspose.page create xps – Generate XPS Documents with .NET
  type: TechArticle
- questions:
  - answer: Yes. Provide the exact font family name when calling `AddGlyphs`; the
      font must be installed on the runtime machine.
    question: Can I use custom fonts in my XPS document?
  - answer: Absolutely. The library works on .NET Core 3.1, .NET 5, .NET 6 and later,
      enabling cross‑platform XPS generation.
    question: Is Aspose.Page compatible with .NET Core?
  - answer: Use the `AddImage` method of the `XpsPage` class. The API accepts PNG,
      JPEG, BMP, and GIF formats.
    question: How do I add images to an XPS document?
  - answer: Yes. Instantiate multiple `XpsPage` objects, populate each with glyphs
      or images, and then save the document once.
    question: Can I create multi‑page XPS documents?
  - answer: Yes, you can explore the full feature set by downloading the [free trial](https://releases.aspose.com/).
    question: Is there a trial version available?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- create xps
- XPS document
- .NET document generation
title: aspose.page create xps – Generar documentos XPS con .NET
url: /es/net/document-creation/create-xps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page create xps – Crear documento XPS con Aspose.Page para .NET

## Introducción

En este tutorial aprenderás a crear documentos **aspose.page create xps** paso a paso usando la biblioteca Aspose.Page para .NET. Ya sea que estés construyendo un motor de informes, un generador de facturas, o cualquier sistema que necesite documentos electrónicos de alta fidelidad, XPS es un formato confiable basado en XML que preserva el diseño en todas las plataformas. Recorreremos todo, desde los requisitos previos hasta guardar el archivo final, con consejos prácticos que puedes aplicar de inmediato.

## Respuestas rápidas
- **¿Qué biblioteca necesito?** Aspose.Page for .NET  
- **¿Puedo ejecutar esto en .NET Core?** Sí – totalmente compatible con .NET Core 3.1, .NET 5, .NET 6 y versiones posteriores  
- **¿Cuántas líneas de código?** Menos de 20 líneas para un archivo XPS básico de “Hello World”  
- **¿Necesito una licencia para pruebas?** Una prueba gratuita funciona para desarrollo; se requiere una licencia para implementaciones en producción  
- **¿Qué formato tiene la salida?** XPS (XML Paper Specification)  

## ¿Cómo crear un documento XPS con Aspose.Page para .NET?

Carga la biblioteca Aspose.Page, instancia un `XpsDocument`, agrega una sola página con glifos, establece el color de relleno y llama a `Save`. Este flujo de trabajo completo requiere solo unas pocas llamadas a métodos y produce un archivo XPS compatible con los estándares que puede abrirse en Windows Reader, Adobe Acrobat o cualquier visor compatible con XPS. El enfoque funciona en Windows, Linux y macOS sin dependencias adicionales.

## ¿Qué es aspose.page create xps?

`aspose.page create xps` se refiere al proceso de generar un archivo XPS (XML Paper Specification) de forma programática usando la API Aspose.Page para .NET. La API abstrae las estructuras de bajo nivel de PDF/XPS, permitiéndote centrarte en el contenido en lugar de en los detalles del formato de archivo. Soporta la configuración del tamaño de página, fuentes, colores e incrustación de imágenes, lo que permite a los desarrolladores crear documentos ricos e imprimibles directamente desde el código.

## ¿Por qué usar Aspose.Page para la generación de XPS?

Aspose.Page soporta **más de 30 formatos de salida** y puede renderizar archivos XPS de hasta **500 MB** sin cargar todo el documento en memoria, ofreciendo alto rendimiento en cargas de trabajo del lado del servidor. La biblioteca garantiza una fidelidad de diseño pixel‑perfecta, incrustación automática de fuentes y soporte completo de Unicode, eliminando la necesidad de convertidores de terceros.

## Requisitos previos

Antes de sumergirnos en el código, asegúrate de tener lo siguiente:

1. **Aspose.Page for .NET Library** – descárgala desde el [download link](https://releases.aspose.com/page/net/).  
2. **Target Directory** – decide dónde se guardará el archivo XPS generado en tu máquina.  

Ahora que el entorno está listo, importemos los espacios de nombres requeridos.

## Importar espacios de nombres

Para usar Aspose.Page para .NET, necesitas importar los espacios de nombres necesarios en tu proyecto. Sigue estos pasos:

### Paso 1: Añadir referencia a Aspose.Page

En tu proyecto, añade una referencia a la biblioteca Aspose.Page para .NET. Puedes encontrar el DLL necesario en el paquete descargado.

### Paso 2: Importar espacios de nombres

Incluye los siguientes espacios de nombres en tu archivo de código:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Paso 1: Establecer el directorio del documento

La variable `directoryPath` indica a la API dónde escribir el archivo XPS resultante.

```csharp
string dir = "Your Document Directory";
```

Reemplaza `"Your Document Directory"` con la ruta real de la carpeta en tu sistema, por ejemplo, `C:\\Docs\\Output`.

## Paso 2: Crear documento XPS

La clase `XpsDocument` representa el objeto raíz de un archivo XPS.

```csharp
XpsDocument xDocs = new XpsDocument();
```

Inicialízala con el nombre de archivo de destino y se creará automáticamente una nueva página.

## Paso 3: Añadir glifos al documento

El método `AddGlyphs` inserta texto (glifos) en la página actual.

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

Puedes controlar la familia de fuentes, tamaño, estilo y coordenadas exactas para posicionar el texto con precisión.

## Paso 4: Establecer el color de relleno de los glifos

El método `SetFillColor` define el pincel usado para pintar los glifos.

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

En este ejemplo usamos negro (`Color.Black`), pero se admite cualquier color ARGB.

## Paso 5: Guardar el resultado

Llamar a `Save` escribe el documento XPS en el disco.

```csharp
xDocs.Save(dir + "output.xps");
```

El archivo contendrá el texto “Hello World!” que agregaste en los pasos anteriores.

## Consejos comunes y trampas

- **Ruta del directorio** – Usa `Path.Combine(dir, "output.xps")` para evitar la falta de separadores de ruta en Windows, Linux o macOS.  
- **Disponibilidad de fuentes** – La fuente especificada debe estar instalada en la máquina host; de lo contrario Aspose sustituye una fuente de respaldo, lo que puede afectar el diseño.  
- **Múltiples páginas** – Para salida de varias páginas, crea objetos `XpsPage` adicionales, agrega contenido a cada uno y luego llama a `Save` una sola vez.  

## Preguntas frecuentes

**Q: ¿Puedo usar fuentes personalizadas en mi documento XPS?**  
A: Sí. Proporciona el nombre exacto de la familia de fuentes al llamar a `AddGlyphs`; la fuente debe estar instalada en la máquina de ejecución.

**Q: ¿Es Aspose.Page compatible con .NET Core?**  
A: Absolutamente. La biblioteca funciona en .NET Core 3.1, .NET 5, .NET 6 y versiones posteriores, permitiendo la generación de XPS multiplataforma.

**Q: ¿Cómo añado imágenes a un documento XPS?**  
A: Usa el método `AddImage` de la clase `XpsPage`. La API acepta formatos PNG, JPEG, BMP y GIF.

**Q: ¿Puedo crear documentos XPS de varias páginas?**  
A: Sí. Instancia varios objetos `XpsPage`, rellena cada uno con glifos o imágenes, y luego guarda el documento una sola vez.

**Q: ¿Hay una versión de prueba disponible?**  
A: Sí, puedes explorar el conjunto completo de funciones descargando la [free trial](https://releases.aspose.com/).

## Conclusión

Ahora tienes un flujo de trabajo completo y listo para producción de documentos **aspose.page create xps** usando Aspose.Page para .NET. Experimenta con diferentes fuentes, colores y diseños de página para adaptar la salida a las necesidades de tu aplicación. Para escenarios más avanzados —como incrustar gráficos vectoriales o manejar trabajos por lotes grandes— consulta la referencia oficial de la API.

---

**Última actualización:** 2026-07-10  
**Probado con:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Agregar texto al documento XPS con Aspose.Page para .NET](/page/net/text-manipulation/add-text-to-xps-document/)
- [Agregar imagen al documento XPS con Aspose.Page para .NET](/page/net/image-management/add-image-to-xps-document/)
- [Agregar rectángulo al documento XPS con Aspose.Page para .NET](/page/net/drawing-shapes/add-rectangle-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}