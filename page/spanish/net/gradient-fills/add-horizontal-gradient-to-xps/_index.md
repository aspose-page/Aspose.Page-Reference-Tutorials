---
title: Agregue degradado horizontal a XPS con Aspose.Page para .NET
linktitle: Agregar degradado horizontal a XPS
second_title: Aspose.Página .NET API
description: Aprenda cómo agregar impresionantes gradientes horizontales a sus documentos XPS usando Aspose.Page para .NET. Aumente el atractivo visual sin esfuerzo.
weight: 13
url: /es/net/gradient-fills/add-horizontal-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregue degradado horizontal a XPS con Aspose.Page para .NET

## Introducción

En este tutorial, exploraremos cómo mejorar los documentos XPS agregando un degradado horizontal usando Aspose.Page para .NET. Aspose.Page para .NET es una poderosa biblioteca que proporciona un manejo perfecto de documentos XPS (XML Paper Especificación) en aplicaciones .NET. Agregar degradados puede aportar atractivo visual a sus documentos y esta guía lo guiará a través del proceso paso a paso.

## Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

1.  Biblioteca Aspose.Page para .NET: asegúrese de tener la biblioteca Aspose.Page para .NET instalada en su entorno de desarrollo. Puedes descargarlo desde el[Aspose.Page para la documentación de .NET](https://reference.aspose.com/page/net/).

2. Entorno de desarrollo: configure un entorno de desarrollo adecuado, incluido un editor de código como Visual Studio.

## Importar espacios de nombres

Comience importando los espacios de nombres necesarios a su proyecto. Estos espacios de nombres son esenciales para trabajar con Aspose.Page para .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Ahora, dividamos el ejemplo proporcionado en varios pasos.

## Paso 1: establecer la ruta del directorio de documentos

```csharp
// ExInicio:3
// La ruta al directorio de documentos.
string dataDir = "Your Document Directory";
// Fin final: 3
```

## Paso 2: cree un nuevo documento XPS

```csharp
// ExInicio:4
// Crear nuevo documento XPS
XpsDocument doc = new XpsDocument();
// Fin final: 4
```

## Paso 3: inicializar las paradas de degradado

```csharp
// ExInicio:5
// Inicializar lista de XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// Fin final: 5
```

## Paso 4: crea una nueva ruta

```csharp
// ExInicio:6
//Cree una nueva ruta definiendo la geometría en forma de abreviatura
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// Fin final: 6
```

## Paso 5: guarde el documento XPS resultante

```csharp
// ExInicio:7
// Guarde el documento XPS resultante
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// Fin final: 7
```

Ahora, ha agregado con éxito un degradado horizontal a su documento XPS usando Aspose.Page para .NET.

## Conclusión

Mejorar sus documentos XPS con degradados no sólo mejora su atractivo visual sino que también proporciona una experiencia de usuario más atractiva. Aspose.Page para .NET simplifica este proceso y le permite lograr resultados profesionales sin esfuerzo.

## Preguntas frecuentes

### P1: ¿Dónde puedo encontrar la documentación de Aspose.Page para .NET?

 A1: Puedes encontrar la documentación.[aquí](https://reference.aspose.com/page/net/).

### P2: ¿Cómo descargo Aspose.Page para .NET?

 A2: Puede descargar la biblioteca desde[Aspose.Page para la página de descarga de .NET](https://releases.aspose.com/page/net/).

### P3: ¿Dónde puedo comprar Aspose.Page para .NET?

 R3: Puede comprar Aspose.Page para .NET desde el[pagina de compra](https://purchase.aspose.com/buy).

### P4: ¿Hay una prueba gratuita disponible?

 R4: Sí, puedes obtener una prueba gratuita desde[aquí](https://releases.aspose.com/).

### P5: ¿Cómo obtengo una licencia temporal de Aspose.Page para .NET?

 R5: Puede obtener una licencia temporal de[este enlace](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
