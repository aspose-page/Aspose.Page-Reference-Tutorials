---
title: Agregue Circle Ellipse al documento XPS con Aspose.Page para .NET
linktitle: Agregar círculo elipse al documento XPS
second_title: Aspose.Página .NET API
description: Mejore los documentos XPS con vibrantes degradados radiales utilizando Aspose.Page para .NET. Siga nuestra guía paso a paso para obtener impresionantes efectos visuales.
type: docs
weight: 11
url: /es/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---
## Introducción

La creación de documentos XPS visualmente atractivos es un requisito común en diversas aplicaciones. Aspose.Page para .NET proporciona un potente conjunto de funciones para manipular documentos XPS de manera eficiente. En este tutorial, nos centraremos en agregar una elipse circular a un documento XPS usando Aspose.Page para .NET. Siga los pasos a continuación para mejorar sus documentos XPS con vibrantes degradados radiales.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

-  Se instaló Aspose.Page para la biblioteca .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/page/net/).
- Un entorno de desarrollo, preferiblemente Visual Studio o cualquier otra herramienta de desarrollo .NET.
- Conocimientos básicos de programación en C#.

## Importar espacios de nombres

Para comenzar, incluya los espacios de nombres necesarios en su código C#:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Ahora, dividamos el ejemplo en varios pasos:

## Paso 1: configurar el documento

```csharp
// ExInicio:1
// La ruta al directorio de documentos.
string dataDir = "Your Document Directory";
// Crear nuevo documento XPS
XpsDocument doc = new XpsDocument();
```

Aquí, inicializamos un nuevo documento XPS usando Aspose.Page para .NET.

## Paso 2: definir la elipse de gradiente radial

```csharp
// Elipse con trazo de gradiente radial en la parte inferior izquierda
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

Este paso implica definir una elipse de degradado radial con varias paradas de color.

## Paso 3: configurar el pincel de degradado radial

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

Aquí, configuramos el trazo de la elipse en un pincel de degradado radial, proporcionándole los parámetros necesarios.

## Paso 4: ajustar el grosor del trazo

```csharp
path.StrokeThickness = 12f;
```

Este paso implica ajustar el grosor del trazo para una mejor visualización.

## Paso 5: guarde el documento XPS resultante

```csharp
// Guarde el documento XPS resultante
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// Fin final: 1
```

Finalmente, guarde el documento XPS modificado en la ubicación deseada.

## Conclusión

¡Felicidades! Ha agregado con éxito una elipse circular con degradados radiales a su documento XPS usando Aspose.Page para .NET. Experimente con diferentes parámetros y colores para lograr los efectos visuales deseados en sus documentos.

## Preguntas frecuentes

### P1: ¿Puedo utilizar Aspose.Page para .NET con otros formatos de documentos?

R1: Aspose.Page para .NET se ocupa específicamente de la manipulación de documentos XPS. Para otros formatos, considere usar bibliotecas Aspose relacionadas.

### P2: ¿Hay una licencia temporal disponible para fines de prueba?

 R2: Sí, puede obtener una licencia temporal para realizar pruebas visitando[este enlace](https://purchase.aspose.com/temporary-license/).

### P3: ¿Dónde puedo encontrar ayuda y debates adicionales?

 A3: Visita el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para apoyo y debates de la comunidad.

### P4: ¿Hay algún documento de muestra disponible como referencia?

 A4: Explora el[documentación](https://reference.aspose.com/page/net/) para obtener ejemplos y directrices completos.

### P5: ¿Puedo comprar Aspose.Page para .NET?

 R5: Sí, puedes comprar la biblioteca.[aquí](https://purchase.aspose.com/buy).