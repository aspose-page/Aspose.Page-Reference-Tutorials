---
date: 2026-03-26
description: Aprende a crear documentos PostScript en .NET con patrones de mosaico
  de texturas usando Aspose.Page. Sigue nuestra guía paso a paso para añadir texturas
  ricas a tus archivos PS.
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: Crear documento PostScript .NET con mosaico de textura
url: /es/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear documento PostScript .NET con mosaico de textura

## Cómo crear un documento PostScript .NET con mosaico de textura

En este tutorial aprenderá a **crear documento PostScript .NET** y a enriquecerlo con un patrón de mosaico de textura usando la biblioteca Aspose.Page. Recorreremos cada paso, desde la configuración de su proyecto hasta rellenar y trazar texto con el pincel de textura, para que pueda producir archivos PS visualmente atractivos en minutos.

## Respuestas rápidas
- **¿Qué biblioteca se utiliza?** Aspose.Page for .NET  
- **¿Puedo usar .NET Core?** Sí, la biblioteca soporta .NET Core y .NET 5/6  
- **¿Qué formatos de imagen funcionan para la textura?** Cualquier formato soportado por System.Drawing (BMP, PNG, JPEG, etc.)  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un ejemplo básico  
- **¿Necesito una licencia?** Una prueba gratuita funciona para pruebas; se requiere una licencia para producción  

## Requisitos previos

- [Visual Studio](https://visualstudio.microsoft.com/) instalado en su máquina.  
- Conocimientos básicos de programación en C#.  
- Descargue e instale la [biblioteca Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- Un archivo de imagen para el patrón de textura (p.ej., **TestTexture.bmp**).

## Importar espacios de nombres

En su archivo C#, importe los espacios de nombres requeridos para que el compilador sepa dónde encontrar los tipos que utilizaremos:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Paso 1: Configurar el directorio del documento

Reemplace **Your Document Directory** con la carpeta donde desea que se guarde el archivo PS generado.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Paso 2: Crear flujo de salida para el documento PS

Este bloque abre un flujo de archivo, configura el tamaño de página (A4 por defecto) y crea una nueva instancia de **PsDocument** sobre la que dibujaremos.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Paso 3: Aplicar patrón de mosaico de textura

Aquí cargamos el bitmap, lo envolvemos en un **TextureBrush**, opcionalmente lo estiramos horizontalmente y le indicamos al **PsDocument** que use este pincel para las operaciones de dibujo posteriores.

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

## Paso 4: Crear ruta de rectángulo y rellenar

Se define un rectángulo simple y se rellena con el pincel de textura que configuramos anteriormente.

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

## Paso 5: Establecer trazo y dibujar

Recuperamos la pintura actual (el pincel de textura), creamos una pluma roja para el contorno y dibujamos el borde del rectángulo.

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

## Paso 6: Rellenar y trazar texto con patrón de textura

Este paso demuestra la capacidad de **rellenar y trazar texto**: los caracteres “ABC” se rellenan con el pincel de textura y luego se delinean, creando un efecto visual impactante.

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

## Paso 7: Guardar y cerrar el documento

Cerrar la página finaliza los comandos de dibujo, y `Save()` escribe el archivo PostScript en el disco.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

## Problemas comunes y soluciones

- **La textura aparece estirada incorrectamente** – Ajuste los valores de `Matrix` para controlar la escala en direcciones X/Y.  
- **Imagen no encontrada** – Verifique que `dataDir` apunte a la carpeta correcta y que el nombre del archivo coincida exactamente, incluidas mayúsculas/minúsculas.  
- **Los colores se ven incorrectos** – Recuerde que PostScript usa un espacio de color independiente del dispositivo; asegúrese de usar objetos `Color` que se mapeen correctamente.

## Preguntas frecuentes

**P:** ¿Puedo usar otros formatos de imagen para el patrón de textura?  
**R:** Sí, cualquier formato soportado por `System.Drawing.Bitmap` (BMP, PNG, JPEG, GIF, etc.) funciona.

**P:** ¿Es Aspose.Page compatible con .NET Core?  
**R:** Absolutamente. La biblioteca funciona en .NET Framework, .NET Core y .NET 5/6.

**P:** ¿Cómo cambio el tamaño del rectángulo texturizado?  
**R:** Modifique los valores de `RectangleF` en el paso de creación del rectángulo (p.ej., `new RectangleF(0, 0, 300, 150)`).

**P:** ¿Puedo aplicar varios patrones de textura en un documento?  
**R:** Sí. Simplemente cree un nuevo `TextureBrush` con una imagen diferente y llame a `SetPaint` nuevamente antes de dibujar la siguiente forma o texto.

**P:** ¿Dónde puedo encontrar más ejemplos y la referencia de la API?  
**R:** Visite el [Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para obtener ayuda de la comunidad y la [documentación oficial](https://reference.aspose.com/page/net/) para el uso detallado de la API.

## Conclusión

Ahora sabe cómo **crear documento PostScript .NET** y aplicar un patrón de mosaico de textura, incluido cómo **rellenar y trazar texto** con esa textura. Experimente con diferentes imágenes, matrices de escala y primitivas de dibujo para producir archivos PS con estilo personalizado para informes, folletos o cualquier salida con mucho contenido gráfico.

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}