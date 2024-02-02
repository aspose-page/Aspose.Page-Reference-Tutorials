---
title: Agregue degradado vertical a XPS con Aspose.Page para .NET
linktitle: Agregar degradado vertical a XPS
second_title: Aspose.Página .NET API
description: Aprenda cómo mejorar documentos XPS con degradados verticales usando Aspose.Page para .NET. Siga nuestra guía paso a paso para una integración perfecta.
type: docs
weight: 15
url: /es/net/gradient-fills/add-vertical-gradient-to-xps/
---
## Introducción

Bienvenido a este tutorial paso a paso sobre cómo agregar un degradado vertical a un documento XPS usando Aspose.Page para .NET. Aspose.Page es una API potente que le permite trabajar con archivos XPS (especificación de papel XML) en sus aplicaciones .NET. En este tutorial, lo guiaremos a través del proceso de crear un nuevo documento XPS, agregar un degradado vertical a una ruta y guardar el resultado.

## Requisitos previos

Antes de sumergirnos en el tutorial, asegúrese de tener los siguientes requisitos previos:

-  Biblioteca Aspose.Page para .NET: asegúrese de tener la biblioteca Aspose.Page para .NET instalada en su entorno de desarrollo. Puedes descargarlo[aquí](https://releases.aspose.com/page/net/).

- Entorno de desarrollo: configure un entorno de desarrollo .NET con su IDE preferido, como Visual Studio.

Ahora, comencemos agregando un degradado vertical a un documento XPS usando Aspose.Page para .NET.

## Importar espacios de nombres

En su aplicación .NET, incluya los espacios de nombres necesarios para acceder a las clases y métodos de Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Paso 1: configure su directorio de documentos

Antes de comenzar, establezca la ruta al directorio de documentos donde desea guardar el documento XPS resultante.

```csharp
// ExInicio:3
string dataDir = "Your Document Directory";
// Fin final: 3
```

## Paso 2: cree un nuevo documento XPS

Inicialice un nuevo documento XPS usando el siguiente código:

```csharp
// ExInicio:4
XpsDocument doc = new XpsDocument();
// Fin final: 4
```

## Paso 3: definir paradas de degradado

Cree una lista de paradas de degradado, especificando el color y la posición de cada parada. En este ejemplo, definimos un gradiente vertical con cinco paradas.

```csharp
// ExInicio:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// Fin final: 5
```

## Paso 4: crea un camino con degradado

Defina un trazado especificando su geometría y aplíquele un pincel de degradado lineal.

```csharp
// ExInicio:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// Fin final: 6
```

## Paso 5: guarde el documento XPS resultante

Guarde el documento XPS modificado en su directorio especificado.

```csharp
// ExInicio:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// Fin final: 7
```

¡Felicidades! Ha agregado con éxito un degradado vertical a un documento XPS usando Aspose.Page para .NET.

## Conclusión

En este tutorial, exploramos cómo aprovechar Aspose.Page para .NET para mejorar documentos XPS con degradados verticales. Aspose.Page simplifica las tareas complejas y proporciona a los desarrolladores una manera perfecta de manipular archivos XPS en sus aplicaciones .NET.

## Preguntas frecuentes

### P1: ¿Aspose.Page es compatible con Visual Studio 2019?

R1: Sí, Aspose.Page es compatible con Visual Studio 2019. Asegúrese de tener instalada la versión correcta de la biblioteca.

### P2: ¿Puedo utilizar Aspose.Page para proyectos comerciales?

 R2: Sí, Aspose.Page se puede utilizar para proyectos comerciales. Visita[aquí](https://purchase.aspose.com/buy) para explorar opciones de licencia.

### P3: ¿Hay una prueba gratuita disponible?

 R3: Sí, puede obtener una prueba gratuita de Aspose.Page[aquí](https://releases.aspose.com/).

### P4: ¿Dónde puedo encontrar la documentación de Aspose.Page?

 A4: La documentación está disponible[aquí](https://reference.aspose.com/page/net/).

### P5: ¿Cómo puedo obtener asistencia o hacer preguntas?

 A5: Visita el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para el apoyo de la comunidad.