---
title: Cambiar el tamaño de las imágenes EPS con Aspose.Page para .NET
linktitle: Cambiar el tamaño de las imágenes EPS
second_title: Aspose.Página .NET API
description: Explore el sencillo proceso de cambiar el tamaño de imágenes EPS en .NET utilizando Aspose.Page. Logre precisión en puntos, pulgadas, milímetros y porcentajes sin esfuerzo.
type: docs
weight: 11
url: /es/net/image-manipulation/resize-eps-images/
---
## Introducción

¿Está buscando cambiar el tamaño de las imágenes EPS sin problemas usando Aspose.Page para .NET? Este tutorial es su guía completa para manipular sin esfuerzo el tamaño de imágenes EPS en varias unidades, como puntos, pulgadas, milímetros y porcentajes. Aspose.Page para .NET proporciona un potente conjunto de herramientas y, en este tutorial, lo guiaremos a través del proceso paso a paso.

## Requisitos previos

Antes de sumergirse en la magia del cambio de tamaño, asegúrese de cumplir con los siguientes requisitos previos:

-  Aspose.Page para la biblioteca .NET: asegúrese de tener instalada la biblioteca Aspose.Page para .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/page/net/).

- Directorio de documentos: cree un directorio donde almacenará su archivo EPS de entrada y los archivos redimensionados de salida.

Ahora que tienes todo configurado, procedamos a importar los espacios de nombres necesarios y profundicemos en la guía paso a paso.

## Importar espacios de nombres

En su proyecto .NET, comience importando los espacios de nombres necesarios para trabajar con Aspose.Page. Agregue el siguiente código al comienzo de su archivo:

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

## Paso 1: Cambiar el tamaño en puntos

Comencemos cambiando el tamaño de una imagen EPS en puntos. Los puntos son una unidad de medida estándar en la industria de la impresión.

```csharp
public static void ResizeInPoints()
{
    // Su directorio de documentos
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## Paso 2: Cambiar el tamaño en pulgadas

Ahora, cambiemos el tamaño de una imagen EPS en pulgadas, una unidad común utilizada en diseño gráfico.

```csharp
public static void ResizeInInches()
{
    // Su directorio de documentos
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## Paso 3: cambiar el tamaño en milímetros

Ahora, cambiemos el tamaño de una imagen EPS a milímetros, otra unidad muy utilizada en diseño e impresión.

```csharp
public static void ResizeInMillimeters()
{
    // Su directorio de documentos
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## Paso 4: cambiar el tamaño en porcentajes

Finalmente, cambiemos el tamaño de una imagen EPS usando porcentajes, proporcionando un enfoque flexible para ajustar el tamaño de la imagen.

```csharp
public static void ResizeInPercents()
{
    // Su directorio de documentos
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

Siéntete libre de integrar estos métodos en tu proyecto y cambiarás el tamaño de las imágenes EPS sin esfuerzo. Experimente con diferentes unidades para lograr las dimensiones deseadas.

## Conclusión

¡Felicidades! Ha dominado el arte de cambiar el tamaño de imágenes EPS con Aspose.Page para .NET. Esta poderosa biblioteca abre un mundo de posibilidades para manipular gráficos vectoriales. Ya sea que esté diseñando para medios impresos o digitales, Aspose.Page le permite lograr resultados precisos y personalizados.

## Preguntas frecuentes

### P1: ¿Puedo cambiar el tamaño de varias imágenes EPS simultáneamente?

R1: Sí, puede recorrer una colección de archivos EPS y aplicar los métodos de cambio de tamaño en consecuencia.

### P2: ¿Aspose.Page es compatible con otros formatos de imagen?

A2: Aspose.Page se centra principalmente en los formatos PostScript y EPS. Para otros formatos de imagen, considere usar Aspose.Imaging.

### P3: ¿Existen consideraciones de licencia para proyectos comerciales?

 R3: Sí, asegúrese de tener una licencia válida. Visita[aquí](https://purchase.aspose.com/buy) para obtener detalles sobre la licencia.

### P4: ¿Puedo probar Aspose.Page antes de comprar?

 R4: ¡Absolutamente! Puedes obtener una prueba gratuita[aquí](https://releases.aspose.com/).

### P5: ¿Dónde puedo buscar ayuda adicional o discutir problemas?

 A5: Visita el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para conectarse con la comunidad y obtener ayuda.