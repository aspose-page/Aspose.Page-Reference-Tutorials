---
date: 2026-03-03
description: 'Aprende a redimensionar imágenes EPS en .NET con Aspose.Page: una guía
  paso a paso sobre cómo cambiar el tamaño de EPS usando puntos, pulgadas, milímetros
  o porcentajes.'
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: Cómo redimensionar imágenes EPS con Aspose.Page para .NET
url: /es/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo redimensionar imágenes EPS con Aspose.Page para .NET

## Introducción

¿Busca **cómo redimensionar EPS** imágenes sin problemas usando Aspose.Page para .NET? Este tutorial es su guía completa para manipular fácilmente el tamaño de imágenes EPS en varias unidades como puntos, pulgadas, milímetros y porcentajes. Aspose.Page para .NET ofrece un conjunto potente de herramientas, y en este tutorial le guiaremos paso a paso.

## Respuestas rápidas
- **¿Qué biblioteca maneja el redimensionado de EPS?** Aspose.Page for .NET  
- **¿Qué unidades son compatibles?** Points, Inches, Millimeters, and Percents  
- **¿Necesito una licencia para producción?** Yes – a commercial license is required  
- **¿Puedo redimensionar varios archivos a la vez?** Absolutely – just loop through the files  
- **¿Se admite .NET Core?** Yes, the API works with .NET Framework and .NET Core  

## Qué es el redimensionado de EPS?

Encapsulated PostScript (EPS) es un formato gráfico basado en vectores que se usa comúnmente en flujos de trabajo de impresión y diseño. Redimensionar un archivo EPS cambia su caja delimitadora sin rasterizar la obra, preservando la nitidez a cualquier escala.

## ¿Por qué redimensionar imágenes EPS?

- **Mantener la calidad de impresión:** El escalado vectorial mantiene los bordes nítidos.  
- **Ajustar a los requisitos de diseño:** Ajuste las dimensiones para que coincidan con el tamaño de la página o del lienzo.  
- **Automatizar trabajos por lotes:** Redimensione programáticamente decenas de archivos en segundos.  

## Requisitos previos

Antes de sumergirse en la magia del redimensionado, asegúrese de que tiene los siguientes requisitos preparados:

- Aspose.Page for .NET Library: Asegúrese de que tiene la biblioteca Aspose.Page for .NET instalada. Puede descargarla desde [here](https://releases.aspose.com/page/net/).

- Document Directory: Cree un directorio donde almacenará su archivo EPS de entrada y los archivos redimensionados de salida.

Ahora que tiene todo configurado, procedamos a importar los espacios de nombres necesarios y profundizar en la guía paso a paso.

## Importar espacios de nombres

En su proyecto .NET, comience importando los espacios de nombres necesarios para trabajar con Aspose.Page. Añada el siguiente código al principio de su archivo:

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

## Cómo redimensionar EPS en puntos

Los puntos son una unidad de medida estándar en la industria de la impresión. El ejemplo a continuación duplica el ancho y la altura originales.

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
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

## Cómo redimensionar EPS en pulgadas

Las pulgadas se utilizan frecuentemente por los diseñadores gráficos al preparar recursos para impresión.

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
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

## Cómo redimensionar EPS en milímetros

Los milímetros son comunes en regiones que utilizan el sistema métrico.

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
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

## Cómo redimensionar EPS usando porcentajes

El redimensionado basado en porcentajes le permite escalar la imagen en relación con su tamaño original.

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
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

Siéntase libre de integrar estos métodos en su proyecto, y redimensionará imágenes EPS sin esfuerzo. Experimente con diferentes unidades para lograr las dimensiones deseadas.

## Problemas comunes y soluciones
- **Archivo no encontrado:** Verifique que `dataDir` apunte a la carpeta correcta y que `input.eps` exista.  
- **Tamaño inesperado:** Recuerde que `Units.Percents` espera valores como 150 para el 150 % del tamaño original.  
- **Excepción de licencia:** Si ve un error de licencia, asegúrese de que se cargue un archivo de licencia válido de Aspose.Page antes de crear `PsDocument`.

## Conclusión

¡Felicidades! Ha dominado **cómo redimensionar EPS** imágenes con Aspose.Page para .NET. Esta poderosa biblioteca abre un mundo de posibilidades para manipular gráficos vectoriales. Ya sea que diseñe para impresión o medios digitales, Aspose.Page le permite lograr resultados precisos y personalizados.

## Preguntas frecuentes

### P1: ¿Puedo redimensionar múltiples imágenes EPS simultáneamente?

A1: Sí, puede iterar a través de una colección de archivos EPS, aplicando los métodos de redimensionado según corresponda.

### P2: ¿Aspose.Page es compatible con otros formatos de imagen?

A2: Aspose.Page se centra principalmente en los formatos PostScript y EPS. Para otros formatos de imagen, considere usar Aspose.Imaging.

### P3: ¿Hay consideraciones de licencia para proyectos comerciales?

A3: Sí, asegúrese de tener una licencia válida. Visite [here](https://purchase.aspose.com/buy) para obtener detalles de la licencia.

### P4: ¿Puedo probar Aspose.Page antes de comprar?

A4: ¡Absolutamente! Puede obtener una prueba gratuita [here](https://releases.aspose.com/).

### P5: ¿Dónde puedo buscar ayuda adicional o discutir problemas?

A5: Visite el [Aspose.Page forum](https://forum.aspose.com/c/page/39) para conectarse con la comunidad y obtener asistencia.

## Preguntas frecuentes

**Q: Does this code work with .NET Core 6?**  
A: Yes. The API is compatible with .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, and .NET 6+.

**Q: How can I preserve the original color profile?**  
A: The `ResizeEps` method does not alter color data; it only changes the bounding box.

**Q: Is it possible to resize an EPS without loading the entire file into memory?**  
A: Using a stream as shown keeps memory usage low; the document is processed on‑the‑fly.

**Q: Can I chain multiple resizing operations?**  
A: Absolutely. Call `ResizeEps` sequentially on the same `PsDocument` instance.

**Q: What happens to embedded images inside the EPS?**  
A: They are scaled proportionally with the vector content, preserving quality.

**Última actualización:** 2026-03-03  
**Probado con:** Aspose.Page 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}