---
title: Convierta XPS a PDF con Aspose.Page para .NET
linktitle: Convertir XPS a PDF
second_title: Aspose.Página .NET API
description: Convierta XPS a PDF en .NET sin esfuerzo con Aspose.Page. Descargue la biblioteca, explore la documentación y obtenga una prueba gratuita.
type: docs
weight: 11
url: /es/net/document-conversion/convert-xps-to-pdf/
---
## Introducción

En este tutorial, profundizaremos en el proceso de conversión de documentos XPS (Especificación de papel XML) a PDF (Formato de documento portátil) utilizando la potente biblioteca Aspose.Page para .NET. Aspose.Page para .NET proporciona un sólido conjunto de funciones para trabajar con archivos XPS, lo que permite a los desarrolladores convertirlos sin problemas a formato PDF con varias opciones de personalización.

## Requisitos previos

Antes de embarcarnos en este viaje de conversión, asegúrese de cumplir con los siguientes requisitos previos:

-  Biblioteca Aspose.Page para .NET: asegúrese de tener la biblioteca Aspose.Page para .NET instalada en su entorno de desarrollo. Puedes descargarlo desde el[Documentación de Aspose.Page](https://reference.aspose.com/page/net/).

- Entorno de desarrollo: configure un entorno de desarrollo .NET con Visual Studio o cualquier otro IDE compatible.

- Documento XPS: prepare el documento XPS que desea convertir a PDF. Este podría ser su archivo XPS de muestra almacenado en un directorio designado.

## Importar espacios de nombres

Antes de profundizar en el código, importemos los espacios de nombres necesarios para que las funcionalidades de Aspose.Page para .NET sean accesibles en nuestro código:

```csharp
using Aspose.Page.XPS;
```

## Paso 1: inicializar el directorio de documentos

```csharp
string dataDir = "Your Document Directory";
```

Reemplace "Su directorio de documentos" con la ruta al directorio que contiene su documento XPS.

## Paso 2: Inicializar transmisiones PDF y XPS

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Abra secuencias tanto para el archivo PDF de salida como para el archivo XPS de entrada. Asegúrese de tener configuradas las rutas de archivo adecuadas.

## Paso 3: cargar el documento XPS

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Cargue el documento XPS utilizando la biblioteca Aspose.Page para .NET.

## Paso 4: Inicialice las opciones de guardado de PDF

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

Configure las opciones de guardado de PDF, incluidos parámetros como el nivel de calidad JPEG, compresión de imágenes, compresión de texto y números de página específicos para incluir.

## Paso 5: crear un dispositivo de procesamiento de PDF

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

Cree un dispositivo de representación para el formato PDF utilizando la biblioteca Aspose.Page para .NET.

## Paso 6: guarde el documento en PDF

```csharp
document.Save(device, options);
```

Guarde el documento XPS en PDF utilizando las opciones y el dispositivo de renderizado especificados.

## Conclusión

¡Felicidades! Ha convertido con éxito un documento XPS a PDF usando Aspose.Page para .NET. Esta biblioteca versátil proporciona a los desarrolladores un potente conjunto de herramientas para manejar varios formatos de documentos sin esfuerzo.

## Preguntas frecuentes

### P1: ¿Puedo convertir varios archivos XPS a un solo PDF usando Aspose.Page para .NET?

R1: Sí, puede recorrer varios archivos XPS y seguir los mismos pasos para fusionarlos en un solo PDF.

### P2: ¿Existen otros formatos de salida compatibles con Aspose.Page para .NET?

R2: Sí, Aspose.Page para .NET admite varios formatos de salida, incluidos TIFF, JPEG, PNG y más.

### P3: ¿Cómo puedo personalizar la apariencia del documento PDF convertido?

R3: Puede modificar los parámetros del objeto de opciones, como la compresión de imágenes y la compresión de texto, para lograr la apariencia deseada.

### P4: ¿Existe una versión de prueba disponible de Aspose.Page para .NET?

 R4: Sí, puede explorar las capacidades de Aspose.Page para .NET obteniendo una prueba gratuita de[aquí](https://releases.aspose.com/).

### P5: ¿Dónde puedo obtener soporte comunitario para Aspose.Page para .NET?

 A5: Visita el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para discusiones y apoyo de la comunidad.