---
date: 2026-07-19
description: Aprenda cómo crear un documento XPS .NET y añadir un rectángulo usando
  Aspose.Page para .NET en una guía concisa paso a paso.
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: Añadir rectángulo al documento XPS
og_description: Cree un documento XPS .NET rápidamente. Este tutorial muestra cómo
  añadir un rectángulo a un archivo XPS usando Aspose.Page para .NET, con código claro
  y consejos.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: Crear documento XPS .NET – Añadir rectángulo con Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: Crear documento XPS .NET – Añadir rectángulo con Aspose.Page
url: /es/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear documento XPS .NET – Añadir rectángulo con Aspose.Page

## Introducción

En este tutorial aprenderás a **crear documento XPS .NET** y dibujar un rectángulo dentro de él usando Aspose.Page para .NET. Ya sea que estés construyendo un motor de informes, una factura imprimible o una capa gráfica personalizada, la capacidad de generar archivos XPS programáticamente te brinda control total sobre el diseño y la fidelidad. Sigue los pasos a continuación y tendrás un archivo XPS listo para usar en minutos.

## Respuestas rápidas
- **¿Cuál es el objetivo principal?** Crear un documento XPS .NET y añadir una forma de rectángulo.  
- **¿Qué biblioteca se requiere?** Aspose.Page para .NET (descargable desde el sitio oficial).  
- **¿Necesito una licencia para pruebas?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 5‑10 minutos para un rectángulo básico.

## ¿Qué es Aspose.Page para .NET?
Aspose.Page para .NET es una API de alto rendimiento, totalmente gestionada, que permite a los desarrolladores crear, editar y renderizar documentos XPS (XML Paper Specification) de forma programática sin depender de componentes externos. Ofrece un modelo de objetos rico para dibujar formas, texto e imágenes, y soporta funciones avanzadas como gestión de color, compresión y conversión a PDF, lo que lo hace adecuado para una amplia gama de escenarios de generación de documentos.

## ¿Por qué usar Aspose.Page para crear documento XPS .NET?
Aspose.Page soporta **más de 30 funciones XPS**—incluyendo gráficos vectoriales, diseño de texto y gestión de color—y puede generar archivos de hasta **500 MB** sin cargar todo el documento en memoria. Esta capacidad cuantificada garantiza un rendimiento fluido incluso para trabajos de impresión a gran escala.

## Requisitos previos

Antes de comenzar con este tutorial, asegúrate de contar con los siguientes requisitos:

1. Biblioteca Aspose.Page para .NET: Verifica que tienes la biblioteca Aspose.Page para .NET instalada en tu entorno de desarrollo. Puedes descargarla [aquí](https://releases.aspose.com/page/net/).

2. Directorio de documentos: Configura un directorio donde deseas almacenar tus documentos XPS.

## Importar espacios de nombres

En tu aplicación .NET, incluye los espacios de nombres necesarios para usar las funcionalidades de Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## ¿Cómo añado un rectángulo a un documento XPS en .NET?

Carga el documento XPS, crea un objeto `Graphics`, define un `RectangleF` con el tamaño deseado y llama a `DrawRectangle`. Esta secuencia dibuja un rectángulo en una sola línea de código y maneja automáticamente el escalado DPI. Para páginas de tamaño A4 típicas, un rectángulo de 200 × 100 pt aparece centrado sin cálculos adicionales.

### Paso 1: Establecer el directorio de documentos

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### Paso 2: Crear un nuevo documento XPS

La clase `XpsDocument` representa el archivo XPS que estás construyendo y proporciona métodos para añadir páginas, gráficos y otros recursos.

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### Paso 3: Añadir un rectángulo

`XpsPath` define un objeto de ruta dibujable dentro del documento XPS, permitiéndote establecer geometría, trazo, relleno y otras propiedades visuales.

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### Paso 4: Guardar el documento

El método `Save` escribe el documento XPS construido en la ruta de archivo especificada en disco.

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

¡Felicidades! Has añadido correctamente un rectángulo a un documento XPS usando Aspose.Page para .NET.

## Problemas comunes y consejos

- **Fuentes faltantes:** Asegúrate de que las fuentes que referencias estén instaladas en el servidor; de lo contrario Aspose.Page sustituirá con una fuente predeterminada, lo que puede alterar el diseño.  
- **Documentos grandes:** Al generar archivos mayores de 200 MB, considera establecer `document.SaveOptions.Compress = true` para reducir el uso de memoria.  
- **Sistema de coordenadas:** XPS usa puntos (1/72 pulgada). Recuerda convertir píxeles a puntos si trabajas con dimensiones basadas en pantalla.

## Preguntas frecuentes

**P: ¿Es Aspose.Page compatible con todas las aplicaciones .NET?**  
R: Sí, Aspose.Page funciona sin problemas con aplicaciones de escritorio, web y cloud .NET.

**P: ¿Dónde puedo encontrar la documentación de Aspose.Page para .NET?**  
R: La referencia completa de la API está disponible [aquí](https://reference.aspose.com/page/net/).

**P: ¿Puedo probar Aspose.Page para .NET de forma gratuita antes de comprar?**  
R: Sí, puedes obtener una prueba gratuita [aquí](https://releases.aspose.com/).

**P: ¿Cómo puedo obtener una licencia temporal para Aspose.Page para .NET?**  
R: Visita [este enlace](https://purchase.aspose.com/temporary-license/) para obtener una licencia temporal.

**P: ¿Dónde puedo buscar soporte comunitario o hacer preguntas relacionadas con Aspose.Page para .NET?**  
R: Visita el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para soporte comunitario.

---

**Última actualización:** 2026-07-19  
**Probado con:** Aspose.Page para .NET 24.9  
**Autor:** Aspose

## Tutoriales relacionados

- [Crear documento XPS con Aspose.Page para .NET](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – Dibujar formas](/page/net/drawing-shapes/)
- [Añadir texto a documento XPS con Aspose.Page para .NET](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}