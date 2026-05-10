---
date: 2026-02-23
description: Aprende cómo agregar degradado a archivos PostScript, guardar el archivo
  PostScript con tamaño de página A4 y rellenar un rectángulo con degradado usando
  Aspose.Page para .NET.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Cómo agregar un degradado – Degradado diagonal en PostScript (PS) con Aspose.Page
  .NET
url: /es/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar un degradado: Degradado diagonal a PostScript (PS) con Aspose.Page .NET

## Introducción

Agregar un degradado diagonal a un documento PostScript (PS) puede mejorar drásticamente el atractivo visual, especialmente cuando necesitas **how to add gradient** efectos en informes técnicos, folletos o aplicaciones intensivas en gráficos. En este tutorial verás exactamente cómo agregar un degradado a un archivo PostScript, establecer un tamaño de página A4 y rellenar un rectángulo con una transición de color suave usando Aspose.Page para .NET.

## Respuestas rápidas
- **¿Qué biblioteca se requiere?** Aspose.Page for .NET  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **¿Puedo cambiar la dirección del degradado?** Sí – rota la transformación del pincel como se muestra en el código  
- **¿Cómo guardo el resultado?** Usa `PsDocument.Save()` que escribe un archivo PostScript en disco  
- **¿Se necesita una licencia para producción?** Sí, una licencia comercial desbloquea la funcionalidad completa  

## ¿Qué es un degradado diagonal en PostScript?

Un degradado diagonal es una transición de color lineal que se ejecuta en un ángulo (normalmente 45°) a través de una forma. En PostScript, esto se logra aplicando un `LinearGradientBrush` con una matriz de transformación personalizada que rota, escala y traslada el degradado para que coincida con el rectángulo deseado.

## ¿Por qué usar Aspose.Page para rellenos con degradado?

Aspose.Page abstrae los comandos de PostScript de bajo nivel, permitiéndote trabajar con objetos gráficos familiares de .NET. Puedes crear rellenos complejos, establecer dimensiones de página y exportar directamente a un **save PostScript file** sin lidiar con la sintaxis cruda de PS.

## Requisitos previos

- **Aspose.Page for .NET Library** – descárgala [here](https://releases.aspose.com/page/net/).  
- **Document Directory** – una carpeta donde se escribirá el archivo `*.ps` generado.

Ahora que hemos cubierto los conceptos básicos, vamos a recorrer la implementación paso a paso.

## Importar espacios de nombres

Primero, importa los espacios de nombres que te dan acceso al dispositivo EPS, utilidades de dibujo y clases de E/S.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Paso 1: Crear flujo de salida para el documento PostScript (Crear documento PostScript)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Paso 2: Establecer tamaño de página A4 (Opciones de guardado)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## Paso 3: Crear un nuevo documento PS de 1‑Página

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Paso 4: Definir parámetros del rectángulo

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Paso 5: Crear ruta gráfica

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Paso 6: Crear pincel de degradado lineal (Rellenar rectángulo con degradado)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Paso 7: Crear transformación para el pincel

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Paso 8: Aplicar transformaciones al pincel (Rotar, Escalar, Trasladar)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Paso 9: Establecer transformación al pincel

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## Paso 10: Establecer pintura y rellenar el rectángulo

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## Paso 11: Cerrar la página actual

```csharp
	//Close current page
	document.ClosePage();
```

## Paso 12: Guardar el documento (Guardar archivo PostScript)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## Cómo guardar el archivo PostScript

La llamada `PsDocument.Save()` escribe el contenido PostScript completamente formado en el flujo que abriste en **Step 1**. Después de que el bloque `using` finalice, el archivo `DiagonaGradient_outPS.ps` estará disponible en el directorio que especificaste.

## Casos de uso comunes

- **Documentación técnica** que necesita un sombreado de fondo sutil.  
- **Folletos de marketing** donde un degradado diagonal aporta un aspecto moderno.  
- **Generadores de informes automáticos** que producen archivos PS imprimibles al instante.  

## Solución de problemas y consejos

- **Colores incorrectos** – verifica los valores ARGB pasados a `LinearGradientBrush`.  
- **Degradado no visible** – asegura que la matriz de transformación rota y escala correctamente; la llamada `Rotate(-45)` establece el ángulo diagonal.  
- **Archivo no creado** – verifica que `dataDir` apunte a una carpeta existente y que la aplicación tenga permisos de escritura.  

## Preguntas frecuentes

**Q: ¿Es Aspose.Page compatible con todos los .NET frameworks?**  
A: Aspose.Page admite una amplia gama de versiones de .NET, desde .NET Framework 4.5+ hasta .NET 6+, garantizando una gran compatibilidad.

**Q: ¿Puedo personalizar los colores del degradado en Aspose.Page?**  
A: Sí, puedes especificar cualquier color ARGB al crear `LinearGradientBrush`, dándote control total sobre los tonos inicial y final.

**Q: ¿Hay una versión de prueba disponible para Aspose.Page?**  
A: Sí, puedes explorar las funciones de Aspose.Page descargando la versión de prueba [here](https://releases.aspose.com/).

**Q: ¿Cómo puedo obtener una licencia temporal para Aspose.Page?**  
A: Obtén una licencia temporal para Aspose.Page [here](https://purchase.aspose.com/temporary-license/) para desbloquear capacidades adicionales durante la evaluación.

**Q: ¿Dónde puedo encontrar soporte comunitario para Aspose.Page?**  
A: Interactúa con la comunidad de Aspose.Page en el [forum](https://forum.aspose.com/c/page/39) para obtener ayuda y participar en discusiones.

---

**Última actualización:** 2026-02-23  
**Probado con:** Aspose.Page for .NET (latest stable release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}