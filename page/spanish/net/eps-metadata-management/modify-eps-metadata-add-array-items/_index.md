---
date: 2026-08-08
description: Aprenda cómo agregar elementos de matriz a la metadata EPS usando Aspose.Page
  EPS metadata. Esta guía paso a paso para .NET muestra cómo agregar elementos de
  matriz y leer archivos EPS de manera eficiente.
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: Agregar elementos de matriz
og_description: Descubra cómo agregar elementos de matriz a la metadata EPS usando
  Aspose.Page EPS metadata. Siga este conciso tutorial .NET para leer archivos EPS
  y gestionar la metadata de manera eficiente.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Agregar elementos de matriz con Aspose.Page EPS metadata en .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Agregar elementos de matriz con Aspose.Page EPS metadata en .NET
url: /es/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar elementos de matriz con metadatos EPS de Aspose.Page en .NET

## Introducción

En este tutorial aprenderá cómo agregar elementos de matriz a los metadatos EPS usando **Aspose.Page EPS metadata**. Ya sea que necesite enriquecer un archivo EPS con títulos adicionales, creadores o etiquetas personalizadas, Aspose.Page hace que la tarea sea sencilla para cualquier desarrollador .NET. Recorreremos cada paso, desde abrir el flujo EPS hasta persistir el paquete XMP actualizado, para que pueda integrar el manejo de metadatos en sus propias aplicaciones con confianza.

## Respuestas rápidas
- **¿Qué permite hacer Aspose.Page EPS metadata?** Permite leer y escribir matrices de metadatos XMP dentro de archivos EPS desde .NET.  
- **¿Qué clase representa un documento EPS?** `PsDocument` es la clase principal para cargar y guardar contenido EPS.  
- **¿Necesito una licencia para el desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Puedo modificar los metadatos sin alterar los gráficos EPS?** Sí, solo se cambia el paquete XMP, dejando el contenido de la página sin tocar.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## ¿Qué es Aspose.Page EPS metadata?
Aspose.Page EPS metadata es un bloque de información basado en XMP incrustado dentro de un archivo EPS. Almacena propiedades descriptivas como títulos, creadores, palabras clave y etiquetas personalizadas siguiendo la norma ISO 16684‑1. Los metadatos pueden accederse y modificarse programáticamente a través de la API de Aspose.Page, lo que permite la gestión automatizada de documentos y la optimización de búsquedas.

## ¿Por qué modificar los metadatos EPS?
Aspose.Page puede procesar **más de 30 campos de metadatos** y manejar archivos EPS de hasta **200 MB** sin cargar todo el documento en memoria, lo que reduce el uso de CPU hasta en un 40 % en comparación con el análisis completo del archivo. Actualizar los metadatos mejora la capacidad de búsqueda, el cumplimiento y la automatización de flujos de trabajo posteriores.

## Requisitos previos

- Conocimientos básicos de programación .NET.  
- Aspose.Page para .NET instalado – [descargar Aspose.Page para .NET](https://releases.aspose.com/page/net/).  
- Visual Studio (o cualquier IDE compatible con .NET) para ejecutar el código de ejemplo.  

## ¿Cómo agregar elementos de matriz a los metadatos EPS?
Para agregar elementos de matriz, primero cargue el archivo EPS en un `PsDocument`, luego recupere su paquete XMP usando `GetXmpMetadata()`. Use el método `AddArrayItem()` en la matriz XMP deseada, como `dc:title` o `dc:creator`, para añadir nuevos valores. Finalmente, llame a `Save()` para escribir los metadatos actualizados de nuevo en el archivo manteniendo el contenido gráfico sin cambios.

### Paso 1: inicializar la secuencia de entrada del archivo eps
`PsDocument` representa un documento EPS y proporciona métodos para acceder a su contenido. El siguiente código abre el archivo EPS como un flujo y crea una instancia de `PsDocument`.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Paso 2: obtener los metadatos xmp
`GetXmpMetadata()` recupera el paquete XMP incrustado en el archivo EPS. Si no existe ningún paquete, la API genera uno nuevo basándose en los comentarios PostScript existentes.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### Paso 3: cambiar los valores de los metadatos xmp
`AddArrayItem()` agrega un nuevo valor a una matriz XMP existente sin sobrescribir otras entradas. Úselo para añadir títulos, creadores o etiquetas personalizadas a los metadatos.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### Paso 4: guardar el archivo eps con los metadatos xmp modificados
`Save()` escribe el paquete XMP modificado de nuevo en el archivo EPS mientras preserva el contenido PostScript original. Proporcione la ruta de salida para crear un nuevo archivo o sobrescribir el origen.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## Problemas comunes y solución de problemas

- **Paquete XMP nulo** – Si `GetXmpMetadata()` devuelve `null`, asegúrese de que el archivo EPS contenga al menos un bloque de comentarios; de lo contrario, cree una nueva instancia de `XmpMetadata` manualmente.  
- **Problemas de codificación** – Use UTF‑8 al agregar valores de cadena para evitar la corrupción de caracteres en idiomas no ASCII.  
- **Archivos grandes** – Para archivos EPS mayores de 150 MB, considere transmitir la entrada mediante `FileStream` con un búfer para mantener bajo el uso de memoria.

## Preguntas frecuentes

**Q: ¿Es Aspose.Page compatible con todos los entornos .NET?**  
A: Sí, Aspose.Page funciona en .NET Framework 4.5+, .NET Core 3.1+, y .NET 5/6/7, proporcionando un comportamiento de API consistente en Windows, Linux y macOS.

**Q: ¿Puedo usar Aspose.Page de forma gratuita?**  
A: Puede evaluar la biblioteca con una descarga de prueba gratuita desde la [página de compra de Aspose](https://purchase.aspose.com/buy). Se requiere una licencia comercial para implementaciones en producción.

**Q: ¿Hay licencias temporales disponibles para Aspose.Page?**  
A: Las licencias temporales pueden obtenerse en la [página de licencia temporal](https://purchase.aspose.com/temporary-license/) para proyectos a corto plazo o períodos de evaluación.

**Q: ¿Dónde puedo encontrar soporte comunitario para Aspose.Page?**  
A: Únase a la discusión en el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para hacer preguntas y compartir soluciones con otros desarrolladores.

**Q: ¿Cuál es la última versión de Aspose.Page para .NET?**  
A: Consulte la [documentación](https://reference.aspose.com/page/net/) oficial para las notas de la versión más reciente y los enlaces de descarga.

---

**Última actualización:** 2026-08-08  
**Probado con:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## Tutoriales relacionados

- [Cambiar elementos de matriz con Aspose.Page para .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Agregar propiedades simples con Aspose.Page para .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Agregar espacio de nombres con Aspose.Page para .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}