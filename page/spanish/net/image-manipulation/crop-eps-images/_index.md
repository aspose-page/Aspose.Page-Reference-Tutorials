---
title: Recortar imágenes EPS con Aspose.Page para .NET
linktitle: Recortar imágenes EPS
second_title: Aspose.Página .NET API
description: Explore el perfecto mundo de la manipulación de imágenes EPS en .NET con Aspose.Page. Recorta y cambia el tamaño de las imágenes sin esfuerzo para obtener resultados sorprendentes.
type: docs
weight: 10
url: /es/net/image-manipulation/crop-eps-images/
---
## Introducción

¿Tiene dificultades para manipular imágenes EPS en sus aplicaciones .NET? ¡No busque más! En este tutorial, lo guiaremos a través del proceso de recortar imágenes EPS utilizando la poderosa biblioteca Aspose.Page para .NET. Ya sea que sea un desarrollador experimentado o recién esté comenzando, esta guía paso a paso lo ayudará a lograr un recorte de imágenes preciso y sin esfuerzo.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

- Un conocimiento práctico del desarrollo .NET.
-  Aspose.Page para la biblioteca .NET instalada. Si no, puedes descargarlo.[aquí](https://releases.aspose.com/page/net/).
- Una imagen EPS de muestra (reemplace "input.eps" en el código con su archivo real).

## Importar espacios de nombres

Comencemos importando los espacios de nombres necesarios para que nuestro código se ejecute sin problemas. 

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

Ahora, dividamos el tutorial en varios pasos.

## Paso 1: Inicializar PsDocument

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

 Inicializar un`PsDocument` objeto con el flujo EPS de entrada.

## Paso 2: extraer el cuadro delimitador

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

Recupere el cuadro delimitador inicial de la imagen EPS.

## Paso 3: crear flujo de salida

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Cree un flujo de salida para la imagen EPS recortada.

## Paso 4: definir un nuevo cuadro delimitador

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Defina un nuevo cuadro delimitador para recortar. Asegúrese de que los nuevos valores estén dentro del cuadro delimitador inicial.

## Paso 5: recortar y guardar

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Recorta la imagen EPS usando el nuevo cuadro delimitador y guárdala en el flujo de salida.

Repita estos pasos para diferentes escenarios de cambio de tamaño.

## Cambiar el tamaño de las imágenes EPS

### Cambiar tamaño en pulgadas

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

Cambie el tamaño de la imagen EPS y guárdela con las dimensiones especificadas en pulgadas.

### Cambiar tamaño en milímetros

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

Cambie el tamaño de la imagen EPS y guárdela con las dimensiones especificadas en milímetros.

### Cambiar el tamaño en porcentajes

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Cambie el tamaño de la imagen EPS y guárdela con las dimensiones especificadas en porcentajes.

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo recortar y cambiar el tamaño de imágenes EPS utilizando Aspose.Page para .NET. Ahora, mejore sus capacidades de manipulación de imágenes y lleve sus aplicaciones .NET al siguiente nivel.

## Preguntas frecuentes

### P1: ¿Puedo usar Aspose.Page para .NET con otros formatos de imagen?

R1: Aspose.Page se centra principalmente en imágenes EPS, pero Aspose proporciona varias bibliotecas para diferentes formatos. Consulte su documentación para conocer formatos específicos.

### P2: ¿Cómo puedo obtener una licencia temporal de Aspose.Page para .NET?

 A2: Visita[este enlace](https://purchase.aspose.com/temporary-license/) para obtener una licencia temporal para realizar pruebas.

### P3: ¿Existe alguna limitación en el tamaño de la imagen que puedo procesar con Aspose.Page para .NET?

A3: Aspose.Page está diseñado para manejar imágenes de varios tamaños. Sin embargo, el rendimiento puede variar según la complejidad de la imagen.

### P4: ¿Existe un foro comunitario para discusiones sobre Aspose.Page?

 R4: Sí, puedes interactuar con la comunidad Aspose.Page[aquí](https://forum.aspose.com/c/page/39).

### P5: ¿Dónde puedo encontrar documentación detallada de Aspose.Page para .NET?

 A5: consulte la documentación[aquí](https://reference.aspose.com/page/net/).