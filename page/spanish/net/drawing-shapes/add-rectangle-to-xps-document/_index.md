---
title: Agregue un rectángulo al documento XPS con Aspose.Page para .NET
linktitle: Agregar rectángulo al documento XPS
second_title: Aspose.Página .NET API
description: Mejore la creación de documentos con Aspose.Page para .NET. Aprenda cómo agregar rectángulos a documentos XPS en este tutorial paso a paso.
weight: 13
url: /es/net/drawing-shapes/add-rectangle-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregue un rectángulo al documento XPS con Aspose.Page para .NET

## Introducción

Aspose.Page para .NET es una potente biblioteca que proporciona una variedad de funciones para trabajar con documentos XPS (XML Paper Especificación) en aplicaciones .NET. En este tutorial, nos centraremos en agregar un rectángulo a un documento XPS usando Aspose.Page para .NET. Siga esta guía paso a paso para mejorar su proceso de creación de documentos.

## Requisitos previos

Antes de comenzar con este tutorial, asegúrese de cumplir con los siguientes requisitos previos:

1.  Biblioteca Aspose.Page para .NET: asegúrese de tener la biblioteca Aspose.Page para .NET instalada en su entorno de desarrollo. Puedes descargarlo[aquí](https://releases.aspose.com/page/net/).

2. Directorio de documentos: configure un directorio donde desee almacenar sus documentos XPS.

## Importar espacios de nombres

En su aplicación .NET, incluya los espacios de nombres necesarios para utilizar las funcionalidades de Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Paso 1: configurar el directorio de documentos

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

## Paso 3: agrega un rectángulo

```csharp
// ExInicio:5
// Rectángulo con trazos de color sólido CMYK (azul) en la parte inferior izquierda
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// Fin final: 5
```

## Paso 4: guarde el documento

```csharp
// ExInicio:6
// Guarde el documento XPS resultante
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// Fin final: 6
```

¡Felicidades! Ha agregado con éxito un rectángulo a un documento XPS usando Aspose.Page para .NET.

## Conclusión

Aspose.Page para .NET simplifica las tareas de manipulación de documentos, permitiendo a los desarrolladores crear y modificar documentos XPS sin esfuerzo. Esta guía paso a paso demuestra cómo agregar un rectángulo a su documento XPS, proporcionando una base sólida para una mayor exploración.

## Preguntas frecuentes

### P1: ¿Aspose.Page es compatible con todas las aplicaciones .NET?

R1: Sí, Aspose.Page está diseñado para funcionar perfectamente con todas las aplicaciones .NET.

### P2: ¿Dónde puedo encontrar la documentación de Aspose.Page para .NET?

 A2: La documentación está disponible.[aquí](https://reference.aspose.com/page/net/).

### P3: ¿Puedo probar Aspose.Page para .NET gratis antes de comprarlo?

 R3: Sí, puedes obtener una prueba gratuita[aquí](https://releases.aspose.com/).

### P4: ¿Cómo puedo obtener una licencia temporal de Aspose.Page para .NET?

 A4: Visita[este enlace](https://purchase.aspose.com/temporary-license/) para obtener una licencia temporal.

### P5: ¿Dónde puedo buscar soporte de la comunidad o hacer preguntas relacionadas con Aspose.Page para .NET?

 A5: Visita el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para el apoyo de la comunidad.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
