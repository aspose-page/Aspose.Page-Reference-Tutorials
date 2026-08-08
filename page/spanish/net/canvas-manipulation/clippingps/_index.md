---
date: 2026-06-25
description: Aprenda cómo agregar una ruta de recorte en PostScript usando Aspose.Page
  para .NET – guía paso a paso con técnicas de pincel y rectángulo punteado.
keywords:
- how to add clipping path
- Aspose.Page clipping
- PostScript graphics .NET
linktitle: Recorte PS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add clipping path in PostScript using Aspose.Page for
    .NET – step‑by‑step guide with paint brush and dashed rectangle techniques.
  headline: How to Add Clipping Path to PostScript with Aspose.Page for .NET
  type: TechArticle
- description: Learn how to add clipping path in PostScript using Aspose.Page for
    .NET – step‑by‑step guide with paint brush and dashed rectangle techniques.
  name: How to Add Clipping Path to PostScript with Aspose.Page for .NET
  steps:
  - name: Set Document Directory
    text: Define the folder where your source and output files will live. This makes
      it easy to locate the generated PS file later.
  - name: Create Output Stream for PostScript Document
    text: Create a writable stream that will hold the generated PS file. Using a `FileStream`
      ensures the file is written directly to disk.
  - name: Create Save Options
    text: '`PsSaveOptions` is Aspose.Page’s configuration object for PS output. It
      lets you control compression, version, and other rendering details.'
  - name: Create a New 1‑Paged PS Document
    text: '`PsDocument` represents a PostScript document object. You instantiate it
      with the output stream and the save options you just configured.'
  - name: Create Graphics Path from the Rectangle
    text: '`GraphicsPath` is a vector container for geometric shapes. Here we start
      with a simple rectangle that will later be clipped.'
  - name: Clipping by Shape
    text: We add a clipping path using a circle, set the paint brush to blue, and
      fill the rectangle within the clipped region. This demonstrates how clipping
      limits drawing to the circle’s interior.
  - name: Displace Upper Level Graphics State & Draw Dashed Rectangle
    text: After restoring the previous graphics state, we translate the cursor, create
      a `Pen` with `DashStyle.Dash`, and draw a dashed rectangle around the clipped
      content. The blue stroke highlights the clipping boundary. `Pen` defines stroke
      attributes such as color and dash style. `DashStyle.Dash` specifi
  - name: Close and Save Document
    text: Finish the page, flush the stream, and dispose of resources. The PS file
      is now written to disk and ready for viewing in any PostScript viewer. You have
      now successfully **added clipping path**, set a custom paint brush, and drawn
      a dashed rectangle around your graphics using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: It restricts drawing operations to a defined shape, hiding everything
      outside that shape.
    question: What does “add clipping path” do?
  - answer: Aspose.Page for .NET provides a rich API for PS/EPS manipulation.
    question: Which library handles clipping in .NET?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes, use `SetPaint` with any `SolidBrush` or gradient you prefer.
    question: Can I change the brush color?
  - answer: Absolutely – create a `Pen` with `DashStyle.Dash` and use `Draw`.
    question: Is drawing a dashed rectangle possible?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Cómo agregar una ruta de recorte a PostScript con Aspose.Page para .NET
url: /es/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar una ruta de recorte a PostScript con Aspose.Page para .NET

## Introducción

En este tutorial integral aprenderá **cómo agregar una ruta de recorte** a un documento PostScript (PS) usando Aspose.Page para .NET. Recorreremos cada paso, le mostraremos cómo **establecer un pincel**, y demostraremos cómo **dibujar un rectángulo punteado** alrededor del contenido recortado. Al final tendrá un archivo PS totalmente funcional que ilustra el recorte por forma, dando a sus gráficos un aspecto más dinámico y profesional.

## Respuestas rápidas
- **¿Qué hace “add clipping path”?** Restringe las operaciones de dibujo a una forma definida, ocultando todo lo que está fuera de esa forma.  
- **¿Qué biblioteca maneja el recorte en .NET?** Aspose.Page para .NET ofrece una API completa para la manipulación de PS/EPS.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Puedo cambiar el color del pincel?** Sí, use `SetPaint` con cualquier `SolidBrush` o degradado que prefiera.  
- **¿Es posible dibujar un rectángulo punteado?** Absolutamente – cree un `Pen` con `DashStyle.Dash` y use `Draw`.  

## ¿Qué es una ruta de recorte en PostScript?

Una ruta de recorte define la región visible de los comandos de dibujo posteriores, descartando cualquier cosa renderizada fuera de sus límites. En términos prácticos, le permite enmascarar gráficos de modo que solo se muestre la porción dentro de la ruta, lo cual es esencial para crear composiciones complejas sin alterar permanentemente los objetos originales.

## ¿Cómo agregar una ruta de recorte a un documento PostScript con Aspose.Page?

Cargue un `PsDocument`, defina una ruta gráfica (por ejemplo, un círculo), aplique `Clip()` para restringir el área de dibujo, luego use `SetPaint` y `Fill` para renderizar contenido dentro de la región recortada. Después de restaurar el estado gráfico, puede dibujar formas adicionales —como un rectángulo punteado— sin afectar el área recortada. Esta secuencia logra el recorte con solo unas pocas llamadas concisas a la API.

`PsDocument` representa un objeto de documento PostScript.  
`GraphicsPath` es un contenedor vectorial para formas geométricas.  
`Clip()` establece la región de recorte para el dibujo posterior.  
`SetPaint` asigna un pincel usado para rellenar formas.  
`Fill` renderiza la ruta actual usando el pincel actual.

## ¿Por qué usar Aspose.Page para recortar?

Aspose.Page admite **más de 50 formatos de entrada y salida**, incluidos PS, EPS, PDF, SVG y tipos de imagen, y puede procesar documentos de cientos de páginas sin cargar todo el archivo en memoria. La biblioteca no tiene **dependencias externas**, se ejecuta en **.NET Framework 4.5+**, **.NET Core 3.1+** y **.NET 6+**, y ofrece control total sobre el estado gráfico (guardar/restaurar, trasladar, rotar). Estos beneficios cuantificados la convierten en una opción fiable para la generación de gráficos del lado del servidor.

## Requisitos previos

- Conocimientos básicos de programación en C#.  
- Biblioteca Aspose.Page para .NET instalada – puede descargarla [aquí](https://releases.aspose.com/page/net/).  
- Visual Studio o cualquier IDE .NET preferido.  

## Importar espacios de nombres

Los siguientes espacios de nombres le dan acceso a los objetos gráficos centrales y a las opciones de guardado específicas de PS.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Ahora desglosaremos el ejemplo en pasos claros y numerados.

### Paso 1: Establecer el directorio del documento

Defina la carpeta donde vivirán sus archivos de origen y salida. Esto facilita localizar el archivo PS generado más adelante.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Paso 2: Crear flujo de salida para el documento PostScript

Cree un flujo de escritura que contendrá el archivo PS generado. Usar un `FileStream` garantiza que el archivo se escriba directamente en el disco.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Paso 3: Crear opciones de guardado

`PsSaveOptions` es el objeto de configuración de Aspose.Page para la salida PS. Le permite controlar la compresión, la versión y otros detalles de renderizado.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Paso 4: Crear un nuevo documento PS de 1 página

`PsDocument` representa un objeto de documento PostScript. Lo instancia con el flujo de salida y las opciones de guardado que acaba de configurar.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Paso 5: Crear ruta gráfica a partir del rectángulo

`GraphicsPath` es un contenedor vectorial para formas geométricas. Aquí comenzamos con un rectángulo simple que luego será recortado.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Paso 6: Recorte por forma

Agregamos una ruta de recorte usando un círculo, establecemos el pincel de pintura en azul y rellenamos el rectángulo dentro de la región recortada. Esto demuestra cómo el recorte limita el dibujo al interior del círculo.

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

Después de restaurar el estado gráfico anterior, trasladamos el cursor, creamos un `Pen` con `DashStyle.Dash` y dibujamos un rectángulo punteado alrededor del contenido recortado. El trazo azul resalta el límite del recorte.

`Pen` define atributos de trazo como color y estilo de guión.  
`DashStyle.Dash` especifica un patrón de línea punteada.

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

Finalice la página, vacíe el flujo y libere los recursos. El archivo PS ahora está escrito en el disco y listo para visualizarse en cualquier visor de PostScript.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Ahora ha agregado correctamente **una ruta de recorte**, configurado un pincel de pintura personalizado y dibujado un rectángulo punteado alrededor de sus gráficos usando Aspose.Page para .NET.

## Problemas comunes y soluciones

- **Recorte no visible:** Asegúrese de llamar a `WriteGraphicsSave()` antes de trasladar y `WriteGraphicsRestore()` después de rellenar.  
- **Colores incorrectos:** Verifique que `SetPaint` se llame después de `Clip` y antes de `Fill`.  
- **Las líneas punteadas aparecen sólidas:** Asegúrese de que el `DashStyle` del `Pen` esté configurado a `DashStyle.Dash` antes de `SetStroke`.  

## Preguntas frecuentes

### Q1: ¿Puedo usar Aspose.Page para .NET con otros lenguajes de programación?
R: Aspose.Page está diseñado principalmente para aplicaciones .NET, pero Aspose ofrece bibliotecas equivalentes para Java, C++ y otras plataformas.

### Q2: ¿Dónde puedo encontrar ejemplos adicionales y documentación para Aspose.Page para .NET?
Puede explorar más ejemplos y documentación detallada en la [documentación de Aspose.Page](https://reference.aspose.com/page/net/).

### Q3: ¿Hay una prueba gratuita disponible para Aspose.Page para .NET?
Sí, puede acceder a una prueba gratuita de Aspose.Page para .NET [aquí](https://releases.aspose.com/).

### Q4: ¿Cómo puedo obtener una licencia temporal para Aspose.Page para .NET?
Puede obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

### Q5: ¿Dónde puedo obtener soporte o discutir consultas relacionadas con Aspose.Page?
Visite los [foros de Aspose.Page](https://forum.aspose.com/c/page/39) para soporte comunitario y discusiones.

---

**Última actualización:** 2026-06-25  
**Probado con:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo crear un documento PostScript con Aspose.Page para .NET](/page/net/document-creation/create-postscript-document/)
- [Guardar archivo PostScript con transformaciones de Aspose.Page (.NET)](/page/net/canvas-manipulation/transformationsps/)
- [Crear documento postscript .net – Agregar rectángulo con Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}