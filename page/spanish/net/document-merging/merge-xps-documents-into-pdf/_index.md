---
title: Fusione documentos XPS en PDF con Aspose.Page para .NET
linktitle: Fusionar documentos XPS en PDF
second_title: Aspose.Página .NET API
description: Combine sin esfuerzo documentos XPS en archivos PDF de alta calidad utilizando Aspose.Page para .NET. Siga nuestra guía paso a paso para disfrutar de una experiencia de conversión de documentos sin problemas.
weight: 11
url: /es/net/document-merging/merge-xps-documents-into-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fusione documentos XPS en PDF con Aspose.Page para .NET

## Introducción

En el panorama en constante evolución del procesamiento de documentos, Aspose.Page para .NET surge como una poderosa herramienta para fusionar sin problemas documentos XPS en formato PDF. Este tutorial lo guiará a través del proceso, desglosando cada paso para garantizar una ejecución fluida y efectiva.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

-  Aspose.Page para .NET: asegúrese de tener instalada la biblioteca Aspose.Page. Puedes descargarlo desde[aquí](https://releases.aspose.com/page/net/).

- Archivos de documentos: tenga el documento XPS (`input.xps`) listo en su directorio especificado.

## Importar espacios de nombres

En su proyecto .NET, incluya los espacios de nombres necesarios para trabajar con Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Este paso garantiza que tenga acceso a las clases y métodos necesarios para la conversión del documento.

## Paso 1: inicializar transmisiones

```csharp
// ExInicio:3
// La ruta al directorio de documentos.
string dataDir = "Your Document Directory";
// Inicializar flujo de salida de PDF
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Inicializar el flujo de entrada XPS
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// Fin final: 3
```

Este paso implica configurar los flujos de entrada y salida para los archivos XPS y PDF. Asegúrese de que se utilicen las rutas y los nombres de archivos correctos.

## Paso 2: cargar el documento XPS

```csharp
// ExInicio:4
// Cargar documento XPS desde la secuencia
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// o cargue el documento XPS directamente desde el archivo. Entonces no se necesita xpsStream.
//Documento XpsDocument = nuevo XpsDocument(inputFileName, nuevo XpsLoadOptions());
// Fin final: 4
```

 Aquí, cargamos el documento XPS en el`XpsDocument` objeto, preparándolo para su posterior procesamiento.

## Paso 3: Inicializar las opciones de guardar

```csharp
// ExInicio:5
// Inicialice el objeto de opciones con los parámetros necesarios.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// Fin final: 5
```

 Personaliza el`PdfSaveOptions` objeto según sus preferencias, especificando parámetros como compresión de imágenes, compresión de texto y números de página.

## Paso 4: crear un dispositivo de renderizado

```csharp
// ExInicio:6
// Crear dispositivo de renderizado para formato PDF
PdfDevice device = new PdfDevice(pdfStream);
// Fin final: 6
```

 El`PdfDevice` es la herramienta responsable de convertir el documento XPS en formato PDF.

## Paso 5: guarde el documento

```csharp
// ExInicio:7
document.Save(device, options);
// Fin final: 7
```

Finalmente, guarde el documento usando el dispositivo de renderizado y las opciones especificadas.

## Conclusión

¡Felicidades! Ha fusionado con éxito documentos XPS en PDF utilizando Aspose.Page para .NET. Este proceso continuo garantiza la preservación de la calidad y el formato del documento.

## Preguntas frecuentes

### P1: ¿Puedo combinar varios archivos XPS en un solo PDF?

 R1: Sí, puedes. Simplemente ajuste el`PageNumbers` parámetro en el`PdfSaveOptions` para incluir las páginas deseadas de diferentes archivos XPS.

### P2: ¿Hay una licencia temporal disponible para Aspose.Page para .NET?

 R2: Sí, puedes obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/) con fines de prueba.

### P3: ¿Existe alguna limitación en el tamaño del archivo al utilizar Aspose.Page para la conversión de documentos?

R3: Aspose.Page para .NET no impone limitaciones estrictas en el tamaño de los archivos, pero se logra un rendimiento óptimo con tamaños de archivos razonables.

### P4: ¿Puedo personalizar aún más el PDF de salida, como agregar marcas de agua o anotaciones?

R4: Sí, Aspose.Page para .NET proporciona amplias funciones para la manipulación de PDF. Consulte la documentación para conocer las opciones de personalización avanzadas.

### P5: ¿Aspose.Page para .NET admite el desarrollo multiplataforma?

R5: Sí, Aspose.Page para .NET está diseñado para funcionar sin problemas en varias plataformas.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
