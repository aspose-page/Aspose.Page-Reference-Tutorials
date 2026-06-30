---
date: 2026-06-30
description: Aprenda cómo crear un documento XPS .NET y añadir glifos rellenos de
  imagen o imágenes externas usando Aspose.Page para .NET en unos pocos pasos sencillos.
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: Añadir glifo relleno de imagen y imagen externa
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Crear documento XPS .NET – Añadir glifo relleno de imagen y imagen externa
  con Aspose.Page
url: /es/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear documento XPS .NET – Añadir glifo rellenado con imagen e imagen externa con Aspose.Page

## Introducción

En el desarrollo .NET, las tareas de **create XPS document .NET** son comunes cuando necesitas gráficos de alta calidad e independientes de la resolución. Aspose.Page for .NET simplifica esto y te permite enriquecer archivos XPS con glifos rellenados con imágenes o extraer imágenes de otro documento XPS. Al final de este tutorial sabrás cómo crear dos documentos XPS, rellenar glifos con imágenes y reutilizar esas imágenes entre documentos — perfecto para generar facturas, certificados o cualquier salida visualmente rica.

## Respuestas rápidas
- **¿Qué admite Aspose.Page?** Más de 25 formatos de imagen y la capacidad de procesar archivos XPS de hasta 500 MB sin cargar todo en memoria.  
- **¿Cuántas líneas de código se necesitan para añadir un glifo rellenado con imagen?** Sólo dos líneas: crear un `ImageBrush` y asignarlo a un `Glyph`.  
- **¿Necesito una licencia para producción?** Sí, una licencia comercial elimina las marcas de agua de evaluación.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **¿Puedo reutilizar fuentes de otro XPS?** Absolutamente — puedes importar la colección de fuentes del primer documento al segundo.

## ¿Cómo crear un documento XPS usando Aspose.Page .NET?

Carga la biblioteca Aspose.Page, instancia un `XpsDocument`, agrega una página y llama a `Save` — ese es el flujo de trabajo completo en tres declaraciones concisas. La API maneja automáticamente el tamaño de página, DPI y la gestión de recursos, por lo que no necesitas gestionar estructuras XPS de bajo nivel tú mismo. Este enfoque escala desde un folleto de una sola página hasta catálogos de cientos de páginas.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

- **Aspose.Page for .NET** – descárgalo desde [aquí](https://releases.aspose.com/page/net/).  
- **Un IDE .NET** – Visual Studio, Rider o VS Code con la extensión C#.  
- **Una carpeta para tus documentos** – la llamaremos **Your Document Directory** en los fragmentos de código.

## Importar espacios de nombres

El espacio de nombres `Aspose.Page.XPS` proporciona las clases principales de documentos XPS, mientras que `Aspose.Page.XPS.XpsModel` contiene elementos del modelo como glifos y pinceles. Impórtalos al inicio de tu archivo:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## ¿Qué es un glifo rellenado con imagen?

Un glifo es una forma vectorial que puede renderizarse con un color sólido, degradado o un pincel de imagen. Cuando aplicas un `ImageBrush`, el interior del glifo se pinta con la imagen suministrada, lo que permite efectos visuales complejos sin rasterizar toda la página.

## Paso 1: Crear el primer documento XPS

`XpsDocument` representa un paquete XPS y es el punto de entrada para crear y guardar archivos XPS. Comienza creando el primer documento XPS que alojará los glifos rellenados con imágenes.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## Paso 2: Añadir glifos al primer documento

`XpsGlyphs` define una colección de glifos (caracteres de texto) que pueden colocarse en una página. Añade glifos al primer documento, especificando la fuente, tamaño, estilo y posición.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Paso 3: Rellenar glifos con un pincel de imagen

`ImageBrush` pinta un área con una imagen, permitiendo que patrones o fotos llenen formas. Rellena los glifos con un pincel de imagen, utilizando una imagen de tu directorio de datos.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Paso 4: Crear el segundo documento XPS

`XpsDocument` se usa para crear un nuevo archivo XPS que puede contener páginas, recursos y contenido. Ahora, crea el segundo documento XPS que incorporará glifos del primer documento.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## Paso 5: Añadir glifos con la fuente del primer documento

`Font` representa una tipografía utilizada para renderizar texto en un documento XPS. Añade glifos al segundo documento, usando la fuente extraída del primer documento. Al compartir la colección de fuentes, mantienes el tamaño del archivo bajo y aseguras la consistencia visual.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Paso 6: Crear un pincel de imagen a partir del relleno del primer documento

`ImageBrush` puede crearse a partir de un relleno existente para reutilizar la misma imagen en varios documentos. Crea un pincel de imagen a partir del relleno del primer documento y úsalo para rellenar los glifos en el segundo documento. Esta técnica de “imagen externa” te permite reutilizar el arte sin duplicar el archivo fuente.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Paso 7: Guardar los documentos

`Save` escribe el paquete XPS en un archivo, incrustando todos los recursos. Guarda tanto el primer como el segundo documento XPS en la carpeta de salida. El método `Save` escribe el paquete XPS, incrustando todos los recursos y preservando los glifos rellenados con imágenes.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Problemas comunes y soluciones

| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| **La imagen no aparece dentro del glifo** | El `ImageBrush` se creó con una URI incorrecta o el tamaño de la imagen supera los límites del glifo. | Verifica la ruta de la imagen y, opcionalmente, establece `ImageBrush.Stretch = Stretch.Uniform`. |
| **Fuentes faltantes en el segundo documento** | Los recursos de fuentes no se exportaron del primer XPS. | Usa `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` antes de añadir glifos. |
| **Ralentización del rendimiento en archivos grandes** | Cargar imágenes grandes en memoria para cada glifo. | Reutiliza una única instancia de `ImageBrush` para todos los glifos, o reduce la resolución de la imagen antes de usarla. |

## Preguntas frecuentes

### P1: ¿Puedo usar diferentes formatos de imagen para rellenar glifos?

R1: Sí, Aspose.Page admite PNG, JPEG, BMP, GIF, TIFF y más — más de 25 formatos en total.

### P2: ¿Cómo puedo personalizar más la apariencia de los glifos?

R2: Explora propiedades como `Glyph.Stroke`, `Glyph.FillOpacity` y `Glyph.Transform` para ajustar contornos, opacidad y rotación.

### P3: ¿Es Aspose.Page adecuado para manejar grandes conjuntos de documentos?

R3: Absolutamente. La biblioteca procesa archivos XPS de cientos de páginas mediante streaming, manteniendo el uso de memoria por debajo de 100 MB incluso para documentos de 500 páginas.

### P4: ¿Puedo aplicar diferentes estilos a glifos individuales?

R4: Sí, cada instancia de `Glyph` tiene sus propias propiedades `Fill`, `Stroke` y `Transform`, lo que permite estilizar cada glifo individualmente.

### P5: ¿Cuáles son los beneficios de usar Aspose.Page frente a otras herramientas XPS?

R5: Aspose.Page admite más de 25 formatos de imagen, procesa archivos de hasta 500 MB sin cargar todo en memoria y ofrece una API 100 % nativa de .NET, eliminando la necesidad de interop COM o herramientas externas.

---

**Última actualización:** 2026-06-30  
**Probado con:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Crear documento XPS – Aspose.Page for .NET](/page/net/document-creation/)
- [Añadir imagen a documento XPS con Aspose.Page for .NET](/page/net/image-management/add-image-to-xps-document/)
- [Añadir clon de glifo y cambiar color con Aspose.Page for .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}