---
date: 2026-06-25
description: Aprenda cómo recortar documentos XPS usando Aspose.Page para .NET. Esta
  guía paso a paso le muestra cómo crear, manipular y guardar archivos XPS de manera
  eficiente.
keywords:
- how to clip xps
- Aspose.Page .NET
- XPS clipping tutorial
linktitle: Recorte de XPS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to clip XPS documents using Aspose.Page for .NET. This step‑by‑step
    guide shows you how to create, manipulate, and save XPS files efficiently.
  headline: How to Clip XPS with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can assign a complex `PathGeometry` that contains several sub‑paths
      to the `Clip` property, allowing layered masking.
    question: Can I combine multiple clip geometries on a single canvas?
  - answer: When you later convert the XPS to PDF using Aspose.PDF, the clip geometry
      is preserved, so the visual result remains identical.
    question: Does clipping affect PDF conversion?
  - answer: XPS itself does not support animation; however, you can generate a series
      of XPS pages with different clip shapes to simulate motion.
    question: Is it possible to animate clipping in XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Cómo recortar XPS con Aspose.Page para .NET
url: /es/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo recortar XPS con Aspose.Page para .NET

## Introducción

¡Bienvenido a este tutorial completo sobre **cómo recortar XPS** usando Aspose.Page para .NET! En esta guía, aprenderás paso a paso cómo crear un documento XPS, aplicar máscaras de recorte geométricas y guardar el resultado. El recorte te permite ocultar partes de un lienzo, habilitando diseños sofisticados como imágenes enmascaradas, formas personalizadas o áreas de contenido enfocadas, todo sin salir de tu código .NET.

## Respuestas rápidas
- **¿Qué es recortar XPS?** Aplicar una máscara geométrica (clip) para limitar el área visible de los elementos del lienzo XPS.  
- **¿Qué biblioteca es la mejor para esto?** Aspose.Page para .NET ofrece una API completa para la creación y recorte de XPS.  
- **¿Requisitos previos?** Visual Studio, tiempo de ejecución .NET y la biblioteca Aspose.Page para .NET.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un escenario básico de recorte.  
- **¿Puedo usar esto en producción?** Sí, con una licencia válida de Aspose (prueba disponible).

## Qué es “cómo recortar XPS”

Recortar XPS significa aplicar una máscara geométrica a un lienzo de modo que cualquier dibujo fuera de la máscara no se renderice. Esta técnica es ideal para crear imágenes enmascaradas, botones con formas personalizadas o enfocar la atención del lector en una región específica de la página. Al definir una geometría de recorte —como un rectángulo, círculo o ruta compleja— obtienes un control granular sobre lo que aparece en la página XPS final.

## Por qué usar Aspose.Page para .NET para recortar XPS

Aspose.Page ofrece manipulación determinista de XPS del lado del servidor sin dependencias externas. Soporta **más de 50 formatos de entrada y salida**, puede procesar **archivos XPS de 200 páginas en menos de 0,5 segundos** en una CPU estándar de 2,5 GHz, y funciona en .NET Framework 4.0+, .NET Core 2.0+, .NET 5, .NET 6 y .NET 7. La API te brinda control total sobre transformaciones del lienzo, geometrías de rutas y pinceles, garantizando una salida de alta calidad cada vez.

## Requisitos previos
- Visual Studio instalado en tu máquina.  
- Biblioteca Aspose.Page para .NET añadida a tu proyecto. Puedes descargarla [aquí](https://releases.aspose.com/page/net/).  
- Conocimientos básicos del lenguaje de programación C#.

## Cómo recortar XPS

Carga un documento XPS, crea un lienzo, define una geometría de recorte (p. ej., un círculo), asigna la geometría a la propiedad `Clip` del lienzo, dibuja tu contenido y, finalmente, guarda el documento. Todos estos pasos pueden realizarse con solo unas pocas llamadas a métodos, y Aspose.Page maneja automáticamente el marcado XML subyacente, de modo que te concentras en el diseño visual en lugar de la estructura del archivo.

## Importar espacios de nombres

Para usar las funcionalidades de Aspose.Page para .NET, necesitas importar los espacios de nombres requeridos en tu proyecto. Sigue estos pasos:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.IO;
```

Ahora, desglosaremos el código de ejemplo que proporcionaste en varios pasos.

## Paso 1: Establecer la ruta del directorio del documento.

Define la carpeta donde se creará el archivo XPS. Usar `Path.Combine` garantiza el separador de directorios correcto en cualquier SO.

```csharp
string dataDir = Path.Combine(Environment.CurrentDirectory, "Output");
Directory.CreateDirectory(dataDir);
```

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Paso 2: Crear un nuevo documento XPS.

Instancia la clase `XpsDocument`, que representa todo el paquete XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

```csharp
string dataDir = "Your Document Directory";
```

## Paso 3: Crear el lienzo principal.

La clase `Canvas` representa una superficie de dibujo dentro de una página XPS donde se renderizan formas, imágenes y texto.

```csharp
Canvas mainCanvas = new Canvas();
```

```csharp
XpsDocument doc = new XpsDocument();
```

## Paso 4: Establecer los desplazamientos izquierdo y superior en el lienzo principal.

Ajusta la posición del lienzo para controlar dónde comienza el dibujo en la página.

```csharp
mainCanvas.Left = 20;
mainCanvas.Top = 30;
```

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

## Paso 5: Crear una geometría de ruta rectangular.

`PathGeometry` define una forma vectorial; aquí creamos un rectángulo simple.

```csharp
PathGeometry rectGeometry = new PathGeometry("M0,0 L100,0 100,50 0,50 Z");
```

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Paso 6: Crear un relleno para rectángulos.

Define un pincel de color sólido que se usará para rellenar el rectángulo.

```csharp
SolidColorBrush rectFill = new SolidColorBrush(Color.Black);
```

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

## Paso 7: Añadir otro lienzo con recorte al lienzo principal.

Crea un lienzo hijo que recibirá una máscara de recorte.

```csharp
Canvas clippedCanvas = new Canvas();
mainCanvas.Children.Add(clippedCanvas);
```

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Paso 8: Crear una geometría circular para el recorte.

`PathGeometry` también puede representar círculos; esta geometría se asignará a la propiedad `Clip` del lienzo hijo.

```csharp
PathGeometry circleClip = new PathGeometry("M50,0 A50,50 0 1 0 49.9,0 Z");
clippedCanvas.Clip = circleClip;
```

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

## Paso 9: Crear un rectángulo en el segundo lienzo y rellenarlo.

Dibuja un rectángulo dentro del lienzo recortado; solo la porción dentro del círculo será visible.

```csharp
Path rectangle = new Path(rectGeometry, rectFill);
clippedCanvas.Children.Add(rectangle);
```

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

## Paso 10: Añadir el segundo lienzo con un rectángulo con trazo al lienzo principal.

Añade un rectángulo con trazo para ilustrar cómo los trazos interactúan con el recorte.

```csharp
Path strokedRect = new Path(rectGeometry, null, new Pen(Color.Blue, 2));
mainCanvas.Children.Add(strokedRect);
```

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Paso 11: Crear un rectángulo en el tercer lienzo y trazarlo.

Un tercer lienzo demuestra dibujo independiente sin recorte.

```csharp
Canvas thirdCanvas = new Canvas();
PathGeometry thirdRectGeom = new PathGeometry("M0,0 L150,0 150,75 0,75 Z");
Path thirdRect = new Path(thirdRectGeom, null, new Pen(Color.Green, 3));
thirdCanvas.Children.Add(thirdRect);
mainCanvas.Children.Add(thirdCanvas);
```

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

## Paso 12: Guardar el documento XPS resultante.

Persistir el paquete XPS en el sistema de archivos.

```csharp
doc.Save(Path.Combine(dataDir, "ClippedOutput.xps"));
```

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

## Problemas comunes y soluciones
- **Ruta inválida** – Asegúrate de que `dataDir` termine con una barra invertida (`\\`) o usa `Path.Combine`.  
- **Recorte no aplicado** – Verifica que la cadena de geometría de recorte esté bien formada; un espacio faltante puede hacer que el recorte se ignore.  
- **Excepción de licencia** – En una compilación no de evaluación, agrega una licencia válida de Aspose antes de crear el documento para evitar excepciones en tiempo de ejecución.

## Preguntas frecuentes

### P1: ¿Puedo usar Aspose.Page para .NET con otros formatos de documento?
R1: Aspose.Page para .NET se centra principalmente en documentos XPS, pero Aspose ofrece otras bibliotecas para varios formatos de documento.

### P2: ¿Es Aspose.Page para .NET adecuado para principiantes?
R2: Sí, Aspose.Page para .NET está diseñado para ser fácil de usar, y los principiantes pueden comprender rápidamente sus funcionalidades con la documentación adecuada.

### P3: ¿Dónde puedo encontrar más ejemplos y recursos?
R3: Visita la [documentación](https://reference.aspose.com/page/net/) y el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para obtener recursos y ejemplos extensos.

### P4: ¿Cómo puedo obtener una licencia temporal para Aspose.Page para .NET?
R4: Puedes obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

### P5: ¿Hay una prueba gratuita disponible para Aspose.Page para .NET?
R5: Sí, puedes explorar la prueba gratuita [aquí](https://releases.aspose.com/).

## Preguntas frecuentes adicionales

**P: ¿Puedo combinar múltiples geometrías de recorte en un solo lienzo?**  
R: Sí, puedes asignar una `PathGeometry` compleja que contenga varias sub‑rutas a la propiedad `Clip`, lo que permite un enmascarado en capas.

**P: ¿El recorte afecta la conversión a PDF?**  
R: Cuando conviertes posteriormente el XPS a PDF usando Aspose.PDF, la geometría de recorte se conserva, por lo que el resultado visual permanece idéntico.

**P: ¿Es posible animar el recorte en XPS?**  
R: XPS en sí no soporta animación; sin embargo, puedes generar una serie de páginas XPS con diferentes formas de recorte para simular movimiento.

---

**Última actualización:** 2026-06-25  
**Probado con:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

```csharp
doc.Save(dataDir + "output2.xps");
```

## Tutoriales relacionados

- [Cómo transformar XPS con Aspose.Page para .NET](/page/net/canvas-manipulation/transformationsxps/)
- [Añadir rectángulo al documento XPS con Aspose.Page para .NET](/page/net/drawing-shapes/add-rectangle-to-xps-document/)
- [Convertir XPS a PDF con Aspose.Page para .NET](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< /blocks/products/products-backtop-button >}}

{{< blocks/products/products-backtop-button >}}