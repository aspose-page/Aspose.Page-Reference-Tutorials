---
date: 2026-01-20
description: Agregue fácilmente números de página al PDF mientras fusiona documentos
  XPS en PDFs de alta calidad usando Aspose.Page para .NET. Siga nuestra guía paso
  a paso para convertir XPS a PDF.
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: Agregar números de página PDF – Fusionar XPS a PDF usando Aspose.Page
url: /es/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar números de página PDF – Fusionar XPS a PDF usando Aspose.Page

## Introducción

Si necesita **add page numbers PDF** mientras fusiona archivos XPS, Aspose.Page for .NET hace que el proceso sea sencillo. En este tutorial recorreremos un ejemplo completo y listo para producción que convierte un documento XPS a un PDF de alta calidad, le permite controlar la compresión de imágenes y inserta automáticamente números de página en el PDF final. Al final tendrá un fragmento reutilizable que puede insertar en cualquier proyecto C#.

## Respuestas rápidas
- **¿Puedo agregar números de página al fusionar XPS a PDF?** Sí – la propiedad `PdfSaveOptions.PageNumbers` hace exactamente eso.  
- **¿Qué biblioteca maneja la conversión?** Aspose.Page for .NET.  
- **¿Necesito una licencia para uso en producción?** Se requiere una licencia válida de Aspose.Page; una licencia temporal está disponible para pruebas.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+ y .NET 5/6+.  
- **¿Es posible obtener imágenes de alta calidad?** Absolutamente – establezca `JpegQualityLevel` en 100 y elija `PdfImageCompression.Jpeg`.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de que tiene los siguientes requisitos previos:

- Aspose.Page for .NET: Asegúrese de que tiene la biblioteca Aspose.Page instalada. Puede descargarla [aquí](https://releases.aspose.com/page/net/).
- Document Files: Tenga el documento XPS (`input.xps`) listo en el directorio especificado.

## Importar espacios de nombres

En su proyecto .NET, incluya los espacios de nombres necesarios para trabajar con Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Este paso garantiza que tenga acceso a las clases y métodos requeridos para la conversión del documento.

## Cómo agregar números de página PDF al fusionar documentos XPS

La colección `PdfSaveOptions.PageNumbers` le permite especificar exactamente qué páginas (o rangos de páginas) deben aparecer en el PDF de salida. Al poblarla con los números de página que desea, Aspose.Page inserta automáticamente la numeración correcta.

### Paso 1: Inicializar flujos

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Este paso implica configurar los flujos de entrada y salida para los archivos XPS y PDF. Asegúrese de que se usen las rutas y nombres de archivo correctos.

### Paso 2: Cargar documento XPS

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

Aquí, cargamos el documento XPS en el objeto `XpsDocument`, preparándolo para el procesamiento posterior.

### Paso 3: Inicializar opciones de guardado (fusionar xps a pdf)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

Personalice el objeto `PdfSaveOptions` según sus preferencias, especificando parámetros como compresión de imagen, compresión de texto y los **page numbers** que desea que aparezcan en el PDF final. Establecer `JpegQualityLevel` en 100 garantiza **high quality PDF images**.

### Paso 4: Crear dispositivo de renderizado

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

El `PdfDevice` es la herramienta responsable de renderizar el documento XPS en formato PDF.

### Paso 5: Guardar el documento (c# xps a pdf)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Finalmente, guarde el documento usando el dispositivo de renderizado y las opciones especificadas. El PDF de salida contendrá las páginas seleccionadas con números de página añadidos automáticamente.

## ¿Por qué usar Aspose.Page para esta conversión?

- **Reliability** – Maneja características complejas de XPS sin pérdida de fidelidad.  
- **Performance** – El procesamiento basado en streams evita cargar archivos completos en memoria.  
- **Flexibility** – Control granular sobre la calidad de imagen, compresión y numeración de páginas.  
- **Cross‑platform** – Funciona en Windows, Linux y macOS con .NET Core.

## Problemas comunes y soluciones

| Problema | Solución |
|----------|----------|
| **El PDF de salida está en blanco** | Verifique que la ruta del archivo XPS sea correcta y que el archivo no esté dañado. |
| **Los números de página no aparecen** | Asegúrese de que `PageNumbers` esté configurado con los índices de página basados en cero correctos (p.ej., `new int[] {1,2,6}`). |
| **Imágenes de baja calidad** | Aumente `JpegQualityLevel` y elija `PdfImageCompression.Jpeg`. |
| **Los archivos XPS grandes generan presión de memoria** | Procese el XPS en fragmentos más pequeños o aumente el límite de memoria de la aplicación. |

## Preguntas frecuentes

### Q1: ¿Puedo fusionar varios archivos XPS en un solo PDF?

A1: Sí, puede. Simplemente ajuste el parámetro `PageNumbers` en `PdfSaveOptions` para incluir las páginas deseadas de diferentes archivos XPS, o cargue cada XPS secuencialmente y llame a `document.Save` en el mismo `PdfDevice`.

### Q2: ¿Está disponible una licencia temporal para Aspose.Page for .NET?

A2: Sí, puede obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/) para propósitos de prueba.

### Q3: ¿Existen limitaciones de tamaño de archivo al usar Aspose.Page para la conversión de documentos?

A3: Aspose.Page for .NET no impone limitaciones estrictas de tamaño de archivo, pero el rendimiento óptimo se logra con archivos de tamaño razonable. Para documentos XPS muy grandes, considere procesarlos en streams para reducir el consumo de memoria.

### Q4: ¿Puedo personalizar aún más el PDF de salida, como agregar marcas de agua o anotaciones?

A4: Sí, Aspose.Page for .NET proporciona amplias funciones para la manipulación de PDF. Después de la conversión, puede usar la biblioteca Aspose.PDF para agregar marcas de agua, anotaciones u otras mejoras.

### Q5: ¿Aspose.Page for .NET soporta desarrollo multiplataforma?

A5: Sí, Aspose.Page for .NET está diseñado para funcionar sin problemas en varias plataformas, incluidas Windows, Linux y macOS, cuando se usa con .NET Core o .NET 5/6.

**Última actualización:** 2026-01-20  
**Probado con:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}