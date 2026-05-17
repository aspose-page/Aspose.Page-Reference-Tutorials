---
date: 2026-02-25
description: Mejora los documentos PostScript con un rectángulo de degradado lineal
  usando Aspose.Page para .NET. Sigue nuestra guía paso a paso para aprender a rellenar
  texto con degradado y a aplicar degradado al contorno del texto.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Agregar un rectángulo con degradado lineal a PostScript (PS) con Aspose.Page
url: /es/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Añadir un rectángulo con degradado lineal a PostScript (PS) con Aspose.Page

## Introducción

Bienvenido a este tutorial completo sobre cómo añadir un **rectángulo con degradado lineal** a documentos PostScript (PS) usando Aspose.Page para .NET. Aspose.Page es una biblioteca potente que permite crear, modificar y renderizar documentos en una variedad de formatos, y hoy nos centraremos en cómo incorporar degradados llamativos a tus archivos PS.

### Respuestas rápidas
- **¿Qué hace el rectángulo con degradado lineal?** Rellena un área rectangular con una transición de color suave de un lado al otro.  
- **¿Qué API maneja el texto con relleno degradado?** `LinearGradientBrush` combinado con `SetPaint` y `FillAndStrokeText`.  
- **¿Puedo delinear texto con un degradado?** Sí—utiliza `SetStroke` con un pincel degradado y llama a `OutlineText`.  
- **¿Necesito una licencia para producción?** Se requiere una licencia comercial de Aspose.Page para uso que no sea de evaluación.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

- Biblioteca Aspose.Page para .NET: Verifica que la biblioteca esté referenciada en tu proyecto. Puedes descargarla desde la [documentación de Aspose.Page para .NET](https://reference.aspose.com/page/net/).
- Directorio de documentos: Crea una carpeta en disco donde se guardará el archivo PS generado y reemplaza **“Your Document Directory”** en el código con esa ruta.

## Importar espacios de nombres

Para empezar, importa los espacios de nombres que te dan acceso a las clases de dibujo y específicas de PS:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## ¿Qué es un rectángulo con degradado lineal?

Un **rectángulo con degradado lineal** es simplemente una forma rectangular cuyo interior se pinta con un degradado lineal: los colores hacen una transición suave a lo largo de una línea recta, típicamente de izquierda a derecha (horizontal) o de arriba a abajo (vertical). En Aspose.Page logras esto combinando un `GraphicsPath` que define el rectángulo con un `LinearGradientBrush` que describe la transición de color.

## ¿Por qué usar texto con relleno degradado y contorno de texto con degradado?

- **Atractivo visual:** El texto con relleno degradado añade profundidad y estilo moderno a informes, facturas o materiales promocionales.  
- **Consistencia de marca:** Igualar los colores corporativos con valores ARGB precisos.  
- **Versatilidad:** El mismo pincel puede reutilizarse para rellenos de formas, rellenos de texto y degradados de contorno, reduciendo la duplicación de código.

## Paso 1: Configurar el documento

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Paso 2: Definir el rectángulo degradado y los colores

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Paso 3: Establecer la transformación para el pincel

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## Paso 4: Establecer la pintura y rellenar el rectángulo

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## Cómo aplicar texto con relleno degradado

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Uso del contorno de texto con degradado

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## Paso 7: Cerrar la página actual y guardar el documento

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

¡Felicidades! Has añadido con éxito un **rectángulo con degradado lineal** a un documento PostScript y has usado el mismo pincel para **texto con relleno degradado** y un **contorno de texto con degradado**.

## Casos de uso comunes y consejos

- **Encabezados de informes:** Rellena bloques de texto grandes con degradados para resaltar los títulos de sección.  
- **Logotipos de marca:** Reproduce formas de logotipos con formas rellenas de degradado para una marca coherente.  
- **Consejo profesional:** Reutiliza la misma instancia de `LinearGradientBrush` para múltiples llamadas de dibujo y mantén los colores perfectamente alineados entre formas y texto.

## Preguntas frecuentes

### Q1: ¿Puedo aplicar degradados a otras formas además de rectángulos?
**R:** Sí, puedes aplicar degradados a cualquier forma definida por un `GraphicsPath`. Simplemente agrega círculos, polígonos o rutas personalizadas antes de llamar a `document.Fill(path)`.

### Q2: ¿Cómo puedo cambiar los colores del degradado?
**R:** Modifica los valores de `Color.FromArgb` al crear el `LinearGradientBrush`. El primer color es el inicio y el segundo es el final del degradado.

### Q3: ¿Aspose.Page es compatible con diferentes formatos de documento?
**R:** Absolutamente. Aspose.Page soporta XPS, PS, PDF y varios otros formatos vectoriales. Consulta la documentación oficial para la lista completa.

### Q4: ¿Puedo usar Aspose.Page en proyectos comerciales?
**R:** Sí, la licencia comercial está disponible. Consulta la página de compra para más detalles: [here](https://purchase.aspose.com/buy).

### Q5: ¿Dónde puedo encontrar soporte de la comunidad?
**R:** Únete al foro de la comunidad de Aspose.Page: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**Última actualización:** 2026-02-25  
**Probado con:** Aspose.Page 24.10 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}