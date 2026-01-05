---
date: 2026-01-05
description: 'Aprende a añadir una ruta de recorte en PostScript usando Aspose.Page
  para .NET: guía paso a paso con técnicas de establecer el pincel y dibujar un rectángulo
  punteado.'
linktitle: Clipping PS
second_title: Aspose.Page .NET API
title: Agregar ruta de recorte a PS con Aspose.Page para .NET
url: /es/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar ruta de recorte a PS con Aspose.Page para .NET

## Introducción

En este tutorial exhaustivo descubrirás cómo **agregar una ruta de recorte** a un documento PostScript (PS) usando Aspose.Page para .NET. Recorreremos cada paso, te mostraremos cómo **establecer el pincel de pintura**, y demostraremos cómo **dibujar un rectángulo punteado** alrededor del contenido recortado. Al final, tendrás un archivo PS completamente funcional que ilustra el recorte por forma, haciendo que tus gráficos sean más dinámicos y profesionales.

## Respuestas rápidas
- **¿Qué hace “agregar ruta de recorte”?** Restringe las operaciones de dibujo a una forma definida, ocultando todo lo que está fuera de esa forma.  
- **¿Qué biblioteca maneja el recorte en .NET?** Aspose.Page para .NET ofrece una API completa para la manipulación de PS/EPS.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Puedo cambiar el color del pincel?** Sí, usa `SetPaint` con cualquier `SolidBrush` o degradado que prefieras.  
- **¿Es posible dibujar un rectángulo punteado?** Absolutamente – crea un `Pen` con `DashStyle.Dash` y usa `Draw`.  

## ¿Qué es una ruta de recorte en PostScript?
Una ruta de recorte define la región visible de los comandos de dibujo posteriores. Todo lo que se dibuje fuera de la ruta se ignora, lo que permite crear gráficos enmascarados complejos sin alterar el contenido original.

## ¿Por qué usar Aspose.Page para el recorte?
- **Sin dependencias externas** – biblioteca pura de .NET.  
- **Control total** sobre el estado gráfico (save/restore, translate, rotate).  
- **Primitivas de dibujo ricas** como `SetPaint`, `Clip` y `Draw` con lápices y pinceles personalizables.  

## Requisitos previos

- Conocimientos básicos de programación en C#.  
- Biblioteca Aspose.Page para .NET instalada – puedes descargarla [aquí](https://releases.aspose.com/page/net/).  
- Visual Studio o cualquier IDE preferido para .NET.  

## Importar espacios de nombres

Primero, importa los espacios de nombres requeridos para la manipulación gráfica:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Ahora desglosaremos el ejemplo en pasos claros y numerados.

### Paso 1: Establecer el directorio del documento

Define la carpeta donde vivirán tus archivos de origen y salida.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Paso 2: Crear flujo de salida para el documento PostScript

Crea un flujo de escritura que contendrá el archivo PS generado.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Paso 3: Crear opciones de guardado

Instancia `PsSaveOptions` con la configuración predeterminada. Puedes personalizar más adelante si lo deseas.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Paso 4: Crear un nuevo documento PS de 1 página

Inicializa el objeto `PsDocument` que representa tu archivo PS.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Paso 5: Crear ruta gráfica a partir del rectángulo

Usaremos un rectángulo como forma base que luego será recortada.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Paso 6: Recorte por forma

Aquí **agregamos la ruta de recorte** usando un círculo, **establecemos el pincel de pintura** a azul, y rellenamos el rectángulo dentro de la región recortada.

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### Paso 7: Desplazar el estado gráfico de nivel superior y dibujar un rectángulo punteado

Después de restaurar el estado anterior, movemos el cursor gráfico nuevamente, **dibujamos un rectángulo punteado** y aplicamos un trazo azul.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### Paso 8: Cerrar y guardar el documento

Finaliza la página y escribe el archivo PS en disco.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Has agregado exitosamente una **ruta de recorte**, establecido un pincel de pintura personalizado y dibujado un rectángulo punteado alrededor de tus gráficos usando Aspose.Page para .NET.

## Problemas comunes y soluciones

- **Recorte no visible:** Asegúrate de llamar a `WriteGraphicsSave()` antes de traducir y a `WriteGraphicsRestore()` después de rellenar.  
- **Colores incorrectos:** Verifica que `SetPaint` se invoque después de `Clip` y antes de `Fill`.  
- **Líneas punteadas aparecen sólidas:** Asegúrate de que la propiedad `DashStyle` del `Pen` esté establecida en `DashStyle.Dash` antes de `SetStroke`.  

## Preguntas frecuentes

### Q1: ¿Puedo usar Aspose.Page para .NET con otros lenguajes de programación?
R: Aspose.Page está diseñado principalmente para aplicaciones .NET. Sin embargo, Aspose ofrece bibliotecas similares para otros lenguajes de programación.

### Q2: ¿Dónde puedo encontrar ejemplos adicionales y documentación para Aspose.Page para .NET?
R: Puedes explorar más ejemplos y documentación detallada en la [documentación de Aspose.Page](https://reference.aspose.com/page/net/).

### Q3: ¿Hay una prueba gratuita disponible para Aspose.Page para .NET?
R: Sí, puedes acceder a una prueba gratuita de Aspose.Page para .NET [aquí](https://releases.aspose.com/).

### Q4: ¿Cómo puedo obtener una licencia temporal para Aspose.Page para .NET?
R: Puedes obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

### Q5: ¿Dónde puedo obtener soporte o discutir consultas relacionadas con Aspose.Page?
R: Visita los [foros de Aspose.Page](https://forum.aspose.com/c/page/39) para soporte comunitario y discusiones.

---

**Última actualización:** 2026-01-05  
**Probado con:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}