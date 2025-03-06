---
title: Agregue glifo relleno de imagen e imagen extranjera con Aspose.Page .NET
linktitle: Agregar glifo relleno de imagen e imagen extranjera
second_title: Aspose.Página .NET API
description: Libere el poder del procesamiento de documentos en .NET con Aspose.Page. Agrega glifos llenos de imágenes sin esfuerzo. Mejore las imágenes y agilice su flujo de trabajo.
weight: 11
url: /es/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregue glifo relleno de imagen e imagen extranjera con Aspose.Page .NET

## Introducción

En el mundo del desarrollo .NET, Aspose.Page se destaca como un poderoso conjunto de herramientas para manejar tareas de procesamiento de documentos. Este tutorial lo guiará a través del proceso de agregar glifos llenos de imágenes e incorporar imágenes extrañas usando Aspose.Page para .NET. Al final de esta guía, tendrá una comprensión sólida de cómo mejorar sus capacidades de procesamiento de documentos.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

-  Aspose.Page para .NET: asegúrese de tener instalada la biblioteca Aspose.Page. Puedes descargarlo desde[aquí](https://releases.aspose.com/page/net/).

- Entorno de desarrollo: configure un entorno de desarrollo .NET que funcione con Visual Studio o cualquier otro IDE preferido.

- Directorio de documentos: cree un directorio donde almacenará sus documentos. Esto se denominará "Su directorio de documentos" en los ejemplos de código.

## Importar espacios de nombres

En su aplicación .NET, comience importando los espacios de nombres necesarios para acceder a las clases y métodos proporcionados por Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Paso 1: cree el primer documento XPS

Comience creando el primer documento XPS usando Aspose.Page. Este documento servirá como base para agregar glifos llenos de imágenes.

```csharp
// ExInicio:1
// La ruta al directorio de documentos.
string dataDir = "Your Document Directory";

// Cree el primer documento XPS
XpsDocument doc1 = new XpsDocument();
```

## Paso 2: agregue glifos al primer documento

Agregue glifos al primer documento, especificando la fuente, el tamaño, el estilo y la posición.

```csharp
// Agregar glifos al primer documento
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Paso 3: rellenar glifos con un pincel de imagen

Rellena los glifos con un pincel de imagen, utilizando una imagen de tu directorio de datos.

```csharp
// Rellena los glifos con un pincel de imagen.
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Paso 4: cree el segundo documento XPS

Ahora, cree el segundo documento XPS que incorporará glifos del primer documento.

```csharp
// Cree el segundo documento XPS
XpsDocument doc2 = new XpsDocument();
```

## Paso 5: agregue glifos con la fuente del primer documento

Agregue glifos al segundo documento, usando la fuente del primer documento.

```csharp
// Agregue glifos con la fuente del primer documento al segundo documento
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Paso 6: cree un pincel de imagen a partir del relleno del primer documento

Cree un pincel de imagen a partir del relleno del primer documento y utilícelo para rellenar los glifos del segundo documento.

```csharp
// Cree un pincel de imagen a partir del relleno del primer documento y rellene glifos en el segundo documento.
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Paso 7: guarde los documentos

Guarde el primer y segundo documento XPS.

```csharp
// Guarde el primer documento XPS
doc1.Save(dataDir + "out1.xps");

// Guarde el segundo documento XPS
doc2.Save(dataDir + "out2.xps");
// Fin final: 1
```

## Conclusión

¡Felicidades! Ha agregado con éxito glifos rellenos de imágenes e incorporado imágenes extrañas usando Aspose.Page para .NET. Este tutorial proporciona una base para mejorar sus capacidades de procesamiento de documentos, abriendo nuevas posibilidades para documentos creativos y visualmente atractivos.

## Preguntas frecuentes

### P1: ¿Puedo utilizar diferentes formatos de imagen para rellenar glifos?

R1: Sí, Aspose.Page admite varios formatos de imagen. Garantizar la compatibilidad con el formato de imagen elegido.

### P2: ¿Cómo puedo personalizar aún más la apariencia de los glifos?

R2: Explore la documentación de Aspose.Page para obtener propiedades y métodos adicionales para ajustar la apariencia de los glifos.

### P3: ¿Aspose.Page es adecuado para manejar grandes conjuntos de documentos?

A3: Aspose.Page está diseñado para manejar conjuntos de documentos grandes y pequeños de manera eficiente.

### P4: ¿Puedo aplicar diferentes estilos a glifos individuales?

R4: Sí, puedes personalizar los estilos para cada glifo de forma independiente, lo que proporciona un alto nivel de flexibilidad.

### P5: ¿Cuáles son los beneficios de utilizar Aspose.Page sobre otras herramientas de procesamiento de documentos?

R5: Aspose.Page ofrece un conjunto completo de funciones, excelente rendimiento y documentación extensa, lo que lo convierte en la opción preferida de muchos desarrolladores.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
