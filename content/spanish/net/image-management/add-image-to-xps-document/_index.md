---
title: Agregar imagen a un documento XPS con Aspose.Page para .NET
linktitle: Agregar imagen al documento XPS
second_title: Aspose.Página .NET API
description: Explore la perfecta integración de imágenes en documentos XPS con Aspose.Page para .NET. Siga nuestra guía paso a paso para disfrutar de una experiencia de desarrollo fluida.
type: docs
weight: 11
url: /es/net/image-management/add-image-to-xps-document/
---
## Introducción

En el mundo del desarrollo .NET, incorporar imágenes en documentos XPS es un requisito común. Aspose.Page para .NET simplifica este proceso y ofrece un potente conjunto de herramientas para manipular y mejorar documentos XPS sin esfuerzo. Este tutorial lo guiará a través de los pasos para agregar una imagen a un documento XPS usando Aspose.Page para .NET.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

1.  Aspose.Page para la biblioteca .NET: descargue e instale la biblioteca desde[Documentación de Aspose.Page .NET](https://reference.aspose.com/page/net/).

2. Entorno de desarrollo: configure un entorno de desarrollo .NET, como Visual Studio.

3. Imagen de muestra: tenga un archivo de imagen de muestra (por ejemplo, "QL_logo_color.tif") que desee agregar al documento XPS.

## Importar espacios de nombres

Comience importando los espacios de nombres necesarios a su proyecto .NET. Estos espacios de nombres son vitales para utilizar las funciones proporcionadas por Aspose.Page para .NET.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Paso 1: configurar el directorio de documentos

Comience especificando la ruta a su directorio de documentos. Este paso garantiza que su proyecto sepa dónde ubicar y guardar archivos.

```csharp
// ExInicio:1
string dataDir = "Your Document Directory";
// Fin final: 1
```

## Paso 2: crear un documento XPS

Cree un nuevo documento XPS usando Aspose.Page para .NET.

```csharp
// ExInicio:1
XpsDocument doc = new XpsDocument();
// Fin final: 1
```

## Paso 3: agregar imagen al documento XPS

Ahora, agreguemos la imagen al documento XPS. En este ejemplo, usaremos una imagen de muestra llamada "QL_logo_color.tif".

```csharp
// ExInicio:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// Fin final: 1
```

## Paso 4: guarde el documento XPS resultante

Guarde el documento XPS con la imagen agregada.

```csharp
// ExInicio:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// Fin final: 1
```

¡Ahora ha agregado con éxito una imagen a un documento XPS usando Aspose.Page para .NET!

## Conclusión

En este tutorial, exploramos cómo aprovechar Aspose.Page para .NET para incorporar imágenes sin problemas en documentos XPS. Esta guía paso a paso garantiza un proceso de integración fluido y mejora sus capacidades de desarrollo .NET.

## Preguntas frecuentes

### P1: ¿Aspose.Page para .NET es compatible con las últimas versiones de .NET Framework?

 R1: Aspose.Page para .NET está diseñado para ser compatible con una amplia gama de versiones de .NET framework, incluidas las últimas versiones. Referirse a[documentación](https://reference.aspose.com/page/net/) para detalles específicos.

### P2: ¿Puedo usar Aspose.Page para .NET en entornos Windows y Linux?

R2: Sí, Aspose.Page para .NET es independiente de la plataforma, lo que lo hace adecuado para su uso en entornos Windows y Linux.

### P3: ¿Existen opciones de licencia para Aspose.Page para .NET?

 R3: Sí, puede explorar opciones de licencia y realizar una compra[aquí](https://purchase.aspose.com/buy).

### P4: ¿Hay una prueba gratuita disponible para Aspose.Page para .NET?

 R4: Sí, puedes probar Aspose.Page para .NET de forma gratuita accediendo al[prueba gratis](https://releases.aspose.com/).

### P5: ¿Dónde puedo buscar ayuda o colaborar con la comunidad de Aspose.Page para .NET?

 A5: Visita el[Aspose.Página para el foro .NET](https://forum.aspose.com/c/page/39) para conectarse con la comunidad y obtener apoyo.