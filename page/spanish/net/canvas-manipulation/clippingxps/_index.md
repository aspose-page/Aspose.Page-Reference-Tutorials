---
title: Recorte de XPS con Aspose.Page para .NET
linktitle: XPS de recorte
second_title: Aspose.Página .NET API
description: Explore el poder de Aspose.Page para .NET en esta guía paso a paso sobre cómo recortar documentos XPS. Cree, manipule y guarde archivos XPS sin esfuerzo.
weight: 11
url: /es/net/canvas-manipulation/clippingxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Recorte de XPS con Aspose.Page para .NET

## Introducción

¡Bienvenido a este tutorial completo sobre cómo recortar XPS usando Aspose.Page para .NET! En esta guía, lo guiaremos a través del proceso de creación, manipulación y guardado de documentos XPS usando Aspose.Page para .NET. XPS, o Especificación de papel XML, es un formato de documento abierto y estandarizado, y Aspose.Page para .NET proporciona potentes herramientas para trabajar con documentos XPS en sus aplicaciones .NET.

## Requisitos previos

Antes de sumergirnos en el tutorial, asegúrese de tener los siguientes requisitos previos:

- Visual Studio instalado en su máquina.
-  Aspose.Page para la biblioteca .NET agregada a su proyecto. Puedes descargarlo[aquí](https://releases.aspose.com/page/net/).
- Conocimientos básicos del lenguaje de programación C#.

## Importar espacios de nombres

Para utilizar Aspose.Page para las funcionalidades .NET, debe importar los espacios de nombres necesarios a su proyecto. Sigue estos pasos:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Ahora, dividamos el código de ejemplo que proporcionó en varios pasos.

## Paso 1: establezca la ruta del directorio de documentos.

```csharp
string dataDir = "Your Document Directory";
```

Asegúrese de reemplazar "Su directorio de documentos" con la ruta real a su directorio de documentos.

## Paso 2: cree un nuevo documento XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

Esto crea un nuevo documento XPS con el que trabajará.

## Paso 3: crea el lienzo principal.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

Este paso crea el lienzo principal, que es común para todos los elementos de la página.

## Paso 4: establezca los desplazamientos izquierdo y superior en el lienzo principal.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Ajuste los desplazamientos izquierdo y superior según sus requisitos.

## Paso 5: crea una geometría de ruta rectangular.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

Esto crea una geometría de ruta para un rectángulo.

## Paso 6: crea un relleno para rectángulos.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Defina el color de relleno de los rectángulos.

## Paso 7: agregue otro lienzo con clip al lienzo principal.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

Este paso agrega otro lienzo al lienzo principal.

## Paso 8: crea una geometría circular para el clip.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Esto crea una geometría de clip circular y la aplica al segundo lienzo.

## Paso 9: Crea un rectángulo en el segundo lienzo y rellénalo.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Este paso crea un rectángulo en el segundo lienzo y lo rellena.

## Paso 10: agregue el segundo lienzo con un rectángulo trazo al lienzo principal.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

Esto agrega otro lienzo al lienzo principal.

## Paso 11: crea un rectángulo en el tercer lienzo y acarícialo.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

Esto crea un rectángulo en el tercer lienzo y le aplica un trazo.

## Paso 12: guarde el documento XPS resultante.

```csharp
doc.Save(dataDir + "output2.xps");
```

Esto guarda el documento XPS en el directorio especificado.

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo recortar XPS usando Aspose.Page para .NET. Esta guía proporciona un recorrido detallado de los pasos involucrados en el proceso.

## Preguntas frecuentes

### P1: ¿Puedo utilizar Aspose.Page para .NET con otros formatos de documentos?

R1: Aspose.Page para .NET se centra principalmente en documentos XPS, pero Aspose proporciona otras bibliotecas para varios formatos de documentos.

### P2: ¿Aspose.Page para .NET es adecuado para principiantes?

R2: Sí, Aspose.Page para .NET está diseñado para ser fácil de usar y los principiantes pueden comprender rápidamente sus funcionalidades con la documentación adecuada.

### P3: ¿Dónde puedo encontrar más ejemplos y recursos?

 A3: Visita el[documentación](https://reference.aspose.com/page/net/) y[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para obtener amplios recursos y ejemplos.

### P4: ¿Cómo puedo obtener una licencia temporal de Aspose.Page para .NET?

 R4: Puede obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).

### P5: ¿Hay una prueba gratuita disponible para Aspose.Page para .NET?

 R5: Sí, puedes explorar la prueba gratuita[aquí](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
