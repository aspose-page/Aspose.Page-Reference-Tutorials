---
title: Transformaciones XPS con Aspose.Page para .NET
linktitle: Transformaciones XPS
second_title: Aspose.Página .NET API
description: Transforme documentos XPS sin esfuerzo con Aspose.Page para .NET. Siga nuestra guía paso a paso para lograr transformaciones perfectas.
weight: 13
url: /es/net/canvas-manipulation/transformationsxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Transformaciones XPS con Aspose.Page para .NET

## Introducción

Bienvenido al mundo de Aspose.Page para .NET, una potente biblioteca que le permite realizar diversas transformaciones en documentos XPS sin esfuerzo. En este tutorial, profundizaremos en el proceso de transformación de documentos XPS usando Aspose.Page para .NET. Ya sea que sea un desarrollador experimentado o recién esté comenzando, esta guía lo guiará a través de cada paso, asegurándose de que comprenda los conceptos fácilmente.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente en su lugar:

-  Aspose.Page para la biblioteca .NET: descargue e instale la biblioteca desde[Aspose.Page para la documentación de .NET](https://reference.aspose.com/page/net/).

- Entorno de desarrollo: configure un entorno de desarrollo compatible, como Visual Studio o cualquier otra herramienta de desarrollo .NET.

- Su directorio de documentos: reemplace el marcador de posición en el código con la ruta real a su directorio de documentos.

¡Ahora, pasemos al tutorial!

## Importar espacios de nombres

En primer lugar, asegúrese de importar los espacios de nombres necesarios para que las funcionalidades de Aspose.Page para .NET estén disponibles en su código. Agregue los siguientes espacios de nombres al comienzo de su secuencia de comandos:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Paso 1: cree un nuevo documento XPS

```csharp
// ExInicio:1
// La ruta al directorio de documentos.
string dataDir = "Your Document Directory";

// Crear nuevo documento XPS
XpsDocument doc = new XpsDocument();
```

## Paso 2: crea un lienzo principal

```csharp
// Crear lienzo principal, común para todos los elementos de la página.
XpsCanvas canvas1 = doc.AddCanvas();

// Realice desplazamientos hacia la izquierda y hacia arriba en el lienzo principal
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Paso 3: crear una geometría de ruta rectangular

```csharp
// Crear geometría de ruta rectangular
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## Paso 4: agregue un relleno para rectángulos

```csharp
// Crear un relleno para rectángulos
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Paso 5: agregue un nuevo lienzo sin transformaciones

```csharp
// Agregue un nuevo lienzo sin ninguna transformación al lienzo principal
XpsCanvas canvas2 = canvas1.AddCanvas();

// Crea un rectángulo en este lienzo y rellénalo.
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Paso 6: agregue un nuevo lienzo con Translate Transformation

```csharp
// Agregue un nuevo lienzo con transformación de traducción al lienzo principal
XpsCanvas canvas3 = canvas1.AddCanvas();

// Traduce este lienzo para colocar un nuevo rectángulo debajo del rectángulo anterior
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Traduce este lienzo al lado derecho de la página.
canvas3.RenderTransform.Translate(500, 0);

// Crea un rectángulo en este lienzo y rellénalo.
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## Paso 7: agregue un nuevo lienzo con transformación de doble escala

```csharp
//Agregue un nuevo lienzo con transformación de doble escala al lienzo principal
XpsCanvas canvas4 = canvas1.AddCanvas();

// Traduce este lienzo para colocar un nuevo rectángulo debajo del rectángulo anterior
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Escala este lienzo
canvas4.RenderTransform.Scale(2, 2);

// Crea un rectángulo en este lienzo y rellénalo.
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## Paso 8: Agregar un nuevo lienzo con rotación alrededor de una transformación de puntos

```csharp
// Agregue un nuevo lienzo con rotación alrededor de una transformación de puntos al lienzo principal
XpsCanvas canvas5 = canvas1.AddCanvas();

// Traduce este lienzo para colocar un nuevo rectángulo debajo del rectángulo anterior
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Gira este lienzo alrededor de un punto en 45 grados.
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Crea un rectángulo en este lienzo y rellénalo.
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## Paso 9: guarde el documento XPS resultante

```csharp
// Guarde el documento XPS resultante
doc.Save(dataDir + "output1.xps");
// Fin final: 1
```

## Conclusión

¡Felicidades! Ha transformado con éxito un documento XPS utilizando Aspose.Page para .NET. Esta guía cubrió pasos esenciales, desde la configuración de requisitos previos hasta la realización de diversas transformaciones. Experimente con estas técnicas y libere todo el potencial de Aspose.Page para .NET en sus proyectos.

## Preguntas frecuentes

### P1: ¿Aspose.Page para .NET es compatible con todos los entornos de desarrollo .NET?

R1: Sí, Aspose.Page para .NET está diseñado para funcionar perfectamente con varios entornos de desarrollo .NET, incluido Visual Studio.

### P2: ¿Dónde puedo encontrar ejemplos y documentación adicionales para Aspose.Page para .NET?

 A2: Visita el[Aspose.Page para la documentación de .NET](https://reference.aspose.com/page/net/) para documentación completa y ejemplos.

### P3: ¿Puedo probar Aspose.Page para .NET antes de comprarlo?

 R3: Sí, puedes explorar una versión de prueba gratuita visitando[Prueba gratuita de Aspose.Page](https://releases.aspose.com/).

### P4: ¿Cómo puedo obtener una licencia temporal de Aspose.Page para .NET?

 R4: Obtenga una licencia temporal visitando[Licencia Temporal](https://purchase.aspose.com/temporary-license/).

### P5: ¿Dónde puedo comprar Aspose.Page para .NET?

 R5: Compre Aspose.Page para .NET en[Aspose.Página Comprar](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
