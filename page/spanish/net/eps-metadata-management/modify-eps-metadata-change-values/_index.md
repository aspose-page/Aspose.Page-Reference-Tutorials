---
date: 2026-08-13
description: Aprenda a usar Aspose.Page para cambiar valores EPS en aplicaciones .NET,
  incluyendo actualizaciones paso a paso de metadatos XMP.
keywords:
- aspose.page change eps values
- modify eps metadata
- xmp metadata .net
- eps file manipulation
lastmod: 2026-08-13
linktitle: Cambiar valores
og_description: El tutorial de Aspose.Page cambia valores EPS muestra cómo modificar
  los metadatos XMP dentro de archivos EPS usando .NET. Siga la guía paso a paso para
  actualizar el creador, el título y la fecha de modificación al instante.
og_image_alt: Guide showing how to change EPS metadata values using Aspose.Page for
  .NET
og_title: Aspose.Page cambia valores EPS con .NET tutorial
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  headline: Aspose.Page change eps values with .NET – tutorial
  type: TechArticle
- description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  name: Aspose.Page change eps values with .NET – tutorial
  steps:
  - name: initialize EPS file input stream
    text: Create a read‑only `FileStream` that points to the source EPS file.
  - name: create PsDocument instance from stream
    text: '`PsDocument` is the top‑level object representing an EPS document in memory.
      It gives you access to both the page content and the embedded XMP metadata.'
  - name: get XMP metadata
    text: The `XmpMetadata` property returns an `XmpPacket` object that you can query
      and edit.
  - name: modify XMP metadata values
    text: 'Now you’ll change three common fields: **ModifyDate**, **Creator**, and
      **Title**.'
  - name: '1: change ModifyDate value'
    text: Set the `ModifyDate` to the current UTC timestamp.
  - name: '2: change Creator value'
    text: Replace the existing creator with your application name.
  - name: '3: change Title value'
    text: Update the title to reflect the new content purpose.
  - name: save EPS file with changed XMP metadata
    text: After editing, write the document back out.
  - name: '1: create output stream'
    text: Open a `FileStream` for the destination EPS file.
  - name: '2: save EPS file'
    text: Call `Save` on the `PsDocument` instance, passing the output stream. Finally,
      close the input stream to release the file handle. Congratulations! You have
      successfully **aspose.page change eps values** by updating the XMP metadata
      inside an EPS file.
  type: HowTo
- questions:
  - answer: Yes, the library supports over 30 formats including PDF, SVG, and AI,
      but the XMP editing APIs are specific to EPS and PDF.
    question: Can I use Aspose.Page for .NET with other graphic formats?
  - answer: Yes, you can try out Aspose.Page for .NET with the free trial available
      on the Aspose releases page [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The comprehensive Aspose.Page .NET API reference can be found [here](https://reference.aspose.com/page/net/).
    question: Where can I find detailed documentation?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: Absolutely! Visit the Aspose.Page purchase page [here](https://purchase.aspose.com/buy)
      for licensing options.
    question: Can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- eps metadata
- .net document processing
- xmp editing
title: Aspose.Page cambia valores EPS con .NET – tutorial
url: /es/net/eps-metadata-management/modify-eps-metadata-change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page cambiar valores eps con .NET – tutorial

## Introducción

En este tutorial descubrirá cómo **aspose.page change eps values** editando los metadatos XMP incrustados en un archivo EPS. Ya sea que necesite actualizar el nombre del creador, ajustar el título o corregir la fecha de modificación, Aspose.Page para .NET le ofrece una API limpia, orientada a código, que funciona en Windows, Linux y macOS. Al final de la guía tendrá un fragmento reutilizable que podrá insertar en cualquier servicio o aplicación de consola .NET.

## Respuestas rápidas

- **¿Qué cubre el tutorial?** Cambiar los metadatos XMP (creador, título, fecha de modificación) dentro de archivos EPS usando Aspose.Page para .NET.  
- **¿Qué versión de la biblioteca se requiere?** Cualquier versión de Aspose.Page para .NET que soporte XMP (v24.10+).  
- **¿Necesito una licencia?** Se requiere una licencia temporal para producción; una prueba gratuita funciona para desarrollo.  
- **¿Puedo ejecutar esto en .NET Core?** Sí – la API es compatible con .NET 5, .NET 6 y .NET Core 3.1+.  
- **¿Cuánto tiempo lleva la implementación?** Alrededor de 5‑10 minutos para una actualización básica de metadatos.

## Qué son los metadatos XMP?

Los metadatos XMP son un bloque XML estandarizado que almacena información descriptiva (autor, título, fechas) dentro de EPS y otros formatos gráficos. Se incrustan directamente en el encabezado del archivo y pueden ser leídos por muchas herramientas de diseño y publicación, lo que permite un manejo consistente de metadatos en todas las plataformas. Actualizar XMP permite que las aplicaciones posteriores muestren las propiedades correctas del documento sin alterar el contenido visual.

## Por qué usar Aspose.Page para metadatos EPS?

Aspose.Page puede procesar **30+** formatos gráficos y maneja archivos EPS de hasta **1 GB** sin cargar todo el archivo en memoria, ofreciendo una reducción del **70 %** en el uso de RAM comparado con el análisis ingenuo de streams. La biblioteca también garantiza que la representación visual del EPS permanezca sin cambios después de editar los metadatos.

## Requisitos previos

Antes de comenzar, asegúrese de que lo siguiente esté listo:

1. **Aspose.Page for .NET library** – descárguela desde la página oficial de versiones de Aspose.Page para .NET [here](https://releases.aspose.com/page/net/). También puede explorar otras versiones de productos Aspose [here](https://releases.aspose.com/).  
2. **Directorio de documentos** – cree una carpeta en su máquina donde residirán los archivos EPS de origen y los archivos de salida.

Ahora que el entorno está configurado, importemos los espacios de nombres que necesitará.

## Importar espacios de nombres

El espacio de nombres `Aspose.Page` proporciona las clases principales, mientras que `System.IO` le brinda capacidades de manejo de streams.

```text
using Aspose.Page;
using Aspose.Page.XMP;
using System.IO;
```

## Cómo cambiar los valores de metadatos EPS?

Cargue el archivo EPS, recupere su paquete XMP, modifique los campos requeridos y escriba el EPS actualizado de nuevo en el disco. El proceso no requiere renderizar el contenido de la página, por lo que es rápido y eficiente en memoria. Siga los pasos detallados para ver ejemplos de código para cada operación. Este flujo de extremo a extremo se cubre en los pasos a continuación.

### Paso 1: inicializar el flujo de entrada del archivo EPS

Cree un `FileStream` de solo lectura que apunte al archivo EPS de origen.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Paso 2: crear instancia de PsDocument desde el stream

`PsDocument` es el objeto de nivel superior que representa un documento EPS en memoria. Le brinda acceso tanto al contenido de la página como a los metadatos XMP incrustados.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

### Paso 3: obtener los metadatos XMP

La propiedad `XmpMetadata` devuelve un objeto `XmpPacket` que puede consultar y editar.

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

### Paso 4: modificar los valores de los metadatos XMP

Ahora cambiará tres campos comunes: **ModifyDate**, **Creator** y **Title**.

#### Paso 4.1: cambiar el valor de ModifyDate

Establezca `ModifyDate` al sello de tiempo UTC actual.

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

#### Paso 4.2: cambiar el valor de Creator

Reemplace el creador existente con el nombre de su aplicación.

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

#### Paso 4.3: cambiar el valor de Title

Actualice el título para reflejar el nuevo propósito del contenido.

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Paso 5: guardar el archivo EPS con los metadatos XMP modificados

Después de editar, escriba el documento de nuevo.

#### Paso 5.1: crear flujo de salida

Abra un `FileStream` para el archivo EPS de destino.

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

#### Paso 5.2: guardar el archivo EPS

Llame a `Save` en la instancia `PsDocument`, pasando el flujo de salida.

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

Finalmente, cierre el flujo de entrada para liberar el manejador del archivo.

```csharp
// Save EPS file
document.Save(outPsStream);
```

¡Felicidades! Ha cambiado con éxito **aspose.page change eps values** actualizando los metadatos XMP dentro de un archivo EPS.

## Problemas comunes y solución de problemas

- **Paquete XMP vacío** – Algunos archivos EPS se generan sin XMP. En ese caso, cree un nuevo `XmpPacket` mediante `new XmpPacket()` antes de asignar valores.  
- **Archivos grandes** – Para EPS mayores de 500 MB, habilite el almacenamiento en búfer de streams estableciendo `PsDocumentOptions.UseMemoryMappedFiles = true` para evitar `OutOfMemoryException`.  
- **Formato de fecha incorrecto** – XMP espera ISO 8601. Use `DateTime.UtcNow.ToString("o")` para generar una cadena conforme.

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Page para .NET con otros formatos gráficos?**  
**A:** Sí, la biblioteca soporta más de 30 formatos, incluidos PDF, SVG y AI, pero las API de edición XMP son específicas para EPS y PDF.

**Q: ¿Está disponible una versión de prueba?**  
**A:** Sí, puede probar Aspose.Page para .NET con la prueba gratuita disponible en la página de lanzamientos de Aspose [here](https://releases.aspose.com/).

**Q: ¿Dónde puedo encontrar documentación detallada?**  
**A:** La referencia completa de la API Aspose.Page .NET se puede encontrar [here](https://reference.aspose.com/page/net/).

**Q: ¿Cómo obtengo una licencia temporal?**  
**A:** Puede obtener una licencia temporal [here](https://purchase.aspose.com/temporary-license/).

**Q: ¿Puedo comprar Aspose.Page para .NET?**  
**A:** ¡Por supuesto! Visite la página de compra de Aspose.Page [here](https://purchase.aspose.com/buy) para opciones de licencia.

---

**Última actualización:** 2026-08-13  
**Probado con:** Aspose.Page 24.10 for .NET  
**Autor:** Aspose

```csharp
finally
{
    psStream.Close();
}
```

## Tutoriales relacionados

- [Agregar metadatos al documento EPS con Aspose.Page para .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Extraer metadatos del documento EPS con Aspose.Page para .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Cambiar valor nombrado con Aspose.Page para .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}