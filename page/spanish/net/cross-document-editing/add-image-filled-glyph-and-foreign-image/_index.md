---
date: 2026-01-07
description: Aprenda a crear documentos XPS en .NET usando Aspose.Page. Esta guía
  muestra cómo agregar glifos rellenados con imágenes e imágenes externas para obtener
  visuales de documento más ricos.
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: Crear documento XPS .NET con Aspose.Page – Glifo rellenado con imagen e imagen
  externa
url: /es/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear documento XPS .NET con Aspose.Page – Glifo rellenado con imagen e imagen externa

## Introducción

Si necesitas **crear documento XPS .NET** en aplicaciones que luzcan pulidas y profesionales, Aspose.Page te brinda las herramientas para incrustar imágenes directamente en glifos y reutilizar recursos gráficos entre documentos. En este tutorial recorreremos la creación de dos archivos XPS, rellenando glifos con un pincel de imagen y luego reutilizando ese pincel en un segundo documento. Al final comprenderás por qué este enfoque ahorra memoria, simplifica el estilo y abre posibilidades creativas para informes, facturas o cualquier contenido imprimible.

## Respuestas rápidas
- **¿Qué cubre este tutorial?** Añadir glifos rellenados con imagen y reutilizarlos en documentos XPS con Aspose.Page para .NET.  
- **¿Qué palabra clave principal se apunta?** `create xps document .net`.  
- **¿Requisitos previos?** Entorno de desarrollo .NET, Aspose.Page para .NET y una carpeta para tus archivos XPS.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un prototipo funcional.  
- **¿Puedo usar otros formatos de imagen?** Sí – cualquier formato compatible con `System.Drawing.Image` de .NET.

## Requisitos previos

Antes de sumergirte en el código, asegúrate de tener lo siguiente listo:

- **Aspose.Page para .NET** – descarga la última biblioteca desde [aquí](https://releases.aspose.com/page/net/).  
- **Entorno de desarrollo** – Visual Studio 2022 (o cualquier IDE que soporte .NET 6+).  
- **Directorio de documentos** – crea una carpeta en tu máquina que contendrá las imágenes de entrada y los archivos XPS generados; la llamaremos **Your Document Directory** en los fragmentos.

## Importar espacios de nombres

Comienza importando los espacios de nombres necesarios para trabajar con objetos XPS y utilidades de dibujo.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Guía paso a paso

### Paso 1: Crear el primer documento XPS

Instanciamos un documento XPS vacío que alojará el glifo rellenado con imagen.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### Paso 2: Añadir glifos al primer documento

A continuación, añadimos un glifo (un carácter de texto) que más tarde rellenaremos con un pincel de imagen.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Paso 3: Rellenar glifos con un pincel de imagen

Aquí creamos un `ImageBrush` a partir de un archivo TIFF ubicado en nuestro directorio de datos y lo aplicamos al glifo. El pincel se configura en modo mosaico para que la imagen se repita si el área del glifo supera el tamaño de la imagen.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### Paso 4: Crear el segundo documento XPS

Ahora generamos un segundo documento XPS que reutilizará el estilo de glifo y el pincel de imagen del primero.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### Paso 5: Añadir glifos con la fuente del primer documento

Añadimos un glifo al segundo documento, reutilizando el mismo objeto de fuente del primer documento. Esto garantiza consistencia visual entre ambos archivos.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### Paso 6: Crear un pincel de imagen a partir del relleno del primer documento

En lugar de cargar la imagen nuevamente, clonamos el pincel de `glyphs1` y lo asignamos a `glyphs2`. Esto demuestra cómo puedes **crear documento XPS .NET** con flujos de trabajo que comparten recursos de manera eficiente.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### Paso 7: Guardar los documentos

Finalmente, persistimos ambos archivos XPS en disco. Ahora puedes abrirlos con cualquier visor XPS para ver el efecto del glifo rellenado con imagen.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## ¿Por qué usar glifos rellenados con imagen al crear documento XPS .NET?

- **Impacto visual** – Transforma texto plano en elementos ricos en gráficos sin rasterizar toda la página.  
- **Reuso de recursos** – Comparte pinceles y fuentes entre varios documentos, reduciendo la huella de memoria.  
- **Flexibilidad** – Mosaica, estira o rota el pincel de imagen para lograr patrones personalizados o branding.

## Problemas comunes y consejos

- **Errores de ruta de archivo** – Asegúrate de que `dataDir` termine con un separador de ruta (`\` o `/`) apropiado para tu SO.  
- **Formatos de imagen no compatibles** – Aspose.Page funciona mejor con TIFF, PNG y JPEG. Convierte otros formatos antes de usarlos.  
- **TileMode no se aplica** – Verifica que realices un cast a `XpsImageBrush` antes de establecer `TileMode`; de lo contrario, la propiedad se ignora.

## Preguntas frecuentes

### Q1: ¿Puedo usar diferentes formatos de imagen para rellenar glifos?

**A:** Sí, Aspose.Page admite TIFF, PNG, JPEG, BMP y GIF. Simplemente proporciona la extensión de archivo correcta en la llamada a `CreateImageBrush`.

### Q2: ¿Cómo puedo personalizar más la apariencia de los glifos?

**A:** Explora propiedades adicionales en `XpsGlyphs` como `Opacity`, `RenderTransform` y `Stroke` para afinar la renderización.

### Q3: ¿Es Aspose.Page adecuado para manejar grandes conjuntos de documentos?

**A:** Absolutamente. La biblioteca está optimizada para escenarios de alto rendimiento y puede procesar miles de archivos XPS en trabajos por lotes.

### Q4: ¿Puedo aplicar estilos diferentes a glifos individuales?

**A:** Sí. Cada instancia de `XpsGlyphs` puede tener su propio relleno, trazo y transformación, dándote control granular.

### Q5: ¿Cuáles son los beneficios de usar Aspose.Page sobre otras herramientas de procesamiento de documentos?

**A:** Aspose.Page ofrece una API completa, sin necesidad de licencias, para creación, manipulación y conversión de XPS, con documentación extensa y soporte 24/7.

---

**Última actualización:** 2026-01-07  
**Probado con:** Aspose.Page 24.12 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}