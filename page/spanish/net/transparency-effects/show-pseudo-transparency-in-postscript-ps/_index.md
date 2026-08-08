---
date: 2026-03-29
description: Aprenda a usar un pincel de degradado lineal en C# para crear pseudo‑transparencia
  en PostScript con Aspose.Page para .NET.
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: Pincel de degradado lineal C# para pseudo‑transparencia en PS
url: /es/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pincel de degradado lineal C# para pseudo‑transparencia en PostScript (PS)

## Introducción

Si necesita agregar un sutil efecto de transparencia a sus archivos PostScript (PS), el **linear gradient brush C#** es la herramienta perfecta. Aspose.Page for .NET facilita pintar rectángulos con rellenos de degradado opacos y translúcidos, dando a sus documentos un aspecto moderno y en capas. En este tutorial recorreremos los pasos exactos necesarios para crear pseudo‑transparencia usando un pincel de degradado lineal en C#.

## Respuestas rápidas
- **¿Qué biblioteca proporciona el linear gradient brush?** Aspose.Page for .NET
- **¿Qué clase gráfica crea el degradado?** `LinearGradientBrush`
- **¿Puedo controlar la opacidad por color?** Sí, usando `Color.FromArgb(alpha, …)`
- **¿Necesito una licencia para producción?** Se requiere una licencia válida de Aspose.Page
- **¿Versiones de .NET compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## ¿Qué es un linear gradient brush C#?

Un `LinearGradientBrush` es un objeto GDI+ que pinta una transición suave entre dos colores a lo largo de una línea recta. Cuando especifica el canal alfa (0‑255) para cada color, puede crear degradados translúcidos —exactamente lo que necesitamos para pseudo‑transparencia en PostScript.

## ¿Por qué usar un linear gradient brush C# para pseudo‑transparencia?

- **Control de opacidad granular:** Ajuste el alfa de cada color para lograr el nivel de transparencia deseado.  
- **Renderizado independiente del dispositivo:** El pincel funciona igual en pantalla, PDF, EPS y salidas PS.  
- **API simple:** Unas pocas líneas de código C# producen efectos visuales de nivel profesional.

## Requisitos previos

Antes de sumergirse en el código, asegúrese de que tiene:

- Aspose.Page for .NET instalado. Puede descargarlo desde la [documentación de Aspose.Page](https://reference.aspose.com/page/net/).
- Una carpeta con permiso de escritura donde se guardará el documento PostScript generado.

Ahora que tiene las herramientas necesarias, comencemos a crear los rectángulos pseudo‑transparentes.

## Importar espacios de nombres

Antes de comenzar, importe los espacios de nombres que contienen las clases que utilizaremos:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Paso 1: Crear el flujo de salida para el documento PostScript

Comenzamos creando un flujo de archivo que contendrá el archivo PS resultante, luego inicializamos el `PsDocument`.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Paso 2: Crear un rectángulo con un relleno de degradado **opaco**

Aquí construimos un `LinearGradientBrush` cuyo colores son completamente opacos (alpha = 255). Este rectángulo servirá como capa de fondo.

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Paso 3: Crear un rectángulo con un relleno de degradado **translúcido**

Ahora usamos un **linear gradient brush C#** donde los valores alfa son menores a 255 (p. ej., 150 y 50). Esto hace que el rectángulo sea parcialmente transparente, logrando el efecto de pseudo‑transparencia.

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Paso 4: Cerrar la página y guardar el documento

Finalmente terminamos la página y escribimos el archivo PS en el disco.

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

Al seguir estos cuatro pasos, puede combinar sin problemas rectángulos opacos y translúcidos, creando un efecto pseudo‑transparente convincente en cualquier salida PostScript.

## Problemas comunes y soluciones

| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| Los colores aparecen completamente opacos | Valor alfa establecido en 255 por error | Use `Color.FromArgb(alpha, …)` con `alpha` < 255 |
| El degradado se estira incorrectamente | Matriz de transformación incorrecta | Verifique que los parámetros de la matriz coincidan con las dimensiones del rectángulo |
| El archivo de salida está vacío | Flujo no cerrado o no se llamó a `Save()` | Asegúrese de que `document.ClosePage()` y `document.Save()` se ejecuten dentro del bloque `using` |

## Preguntas frecuentes

**Q: ¿Es Aspose.Page compatible con todas las versiones de .NET?**  
A: Aspose.Page for .NET es compatible con varias versiones del framework .NET, garantizando flexibilidad y facilidad de integración.

**Q: ¿Puedo aplicar pseudo‑transparencia a otras formas además de rectángulos?**  
A: Sí, los mismos principios pueden aplicarse a cualquier forma ajustando el `GraphicsPath` según corresponda.

**Q: ¿Dónde puedo encontrar ejemplos y documentación adicionales?**  
A: Explore la [documentación de Aspose.Page](https://reference.aspose.com/page/net/) para obtener ejemplos completos y referencias detalladas de la API.

**Q: ¿Hay una prueba gratuita disponible para Aspose.Page?**  
A: Sí, puede acceder a una prueba gratuita de Aspose.Page desde [este enlace](https://releases.aspose.com/).

**Q: ¿Cómo puedo obtener una licencia temporal para Aspose.Page?**  
A: Visite [este enlace](https://purchase.aspose.com/temporary-license/) para obtener una licencia temporal para Aspose.Page.

---

**Última actualización:** 2026-03-29  
**Probado con:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}