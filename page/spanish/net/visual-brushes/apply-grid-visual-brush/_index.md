---
date: 2026-04-03
description: Aprende a agregar un rectángulo transparente y aplicar un Grid Visual
  Brush en .NET usando Aspose.Page para crear documentos XPS impresionantes.
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: Aplicar pincel visual de cuadrícula
second_title: Aspose.Page .NET API
title: Agregar rectángulo transparente usando Grid Visual Brush (.NET)
url: /es/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar rectángulo transparente usando Grid Visual Brush (.NET)

## Introducción

Si buscas **agregar un rectángulo transparente** a un documento XPS mientras aplicas un elegante Grid Visual Brush, has llegado al lugar correcto. En este tutorial recorreremos los pasos exactos necesarios con Aspose.Page for .NET, para que puedas crear documentos visualmente ricos que destaquen. Al final tendrás un ejemplo completo y ejecutable que demuestra ambas técnicas en un flujo de trabajo sencillo y fácil de seguir.

## Respuestas rápidas
- **¿Qué hace un rectángulo transparente?** Añade una superposición semi‑opaca que permite que el contenido de fondo se vea.  
- **¿Qué API crea el brush?** `XpsDocument.CreateVisualBrush` construye el Grid Visual Brush.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un ejemplo básico.

## ¿Qué es un rectángulo transparente en XPS?
Un rectángulo transparente es simplemente una forma cuyo color de relleno incluye un componente alfa menor que 1.0, lo que permite que los gráficos subyacentes sean parcialmente visibles. Esto es perfecto para resaltar secciones sin oscurecer completamente el fondo.

## ¿Por qué usar un Grid Visual Brush?
Un Grid Visual Brush te permite mosaicar un pequeño gráfico vectorial en un área mayor, creando patrones como cuadrículas, tramas o texturas personalizadas. Combinarlo con un rectángulo transparente te brinda efectos visuales en capas que son ligeros e independientes de la resolución.

## Requisitos previos

Antes de sumergirte en el código, asegúrate de tener:

- **Aspose.Page for .NET** – puedes descargarlo [aquí](https://releases.aspose.com/page/net/).
- Un entorno de desarrollo .NET (Visual Studio, VS Code, o cualquier IDE que prefieras).
- Una carpeta donde se guardarán los archivos XPS generados.

## Importar espacios de nombres

En tu archivo C#, importa los espacios de nombres requeridos:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Ahora vamos a dividir la solución en pasos claros y numerados.

## Paso 1: Inicializar XpsDocument

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

Comenzamos creando una instancia de `XpsDocument`, que contendrá todas las operaciones de dibujo posteriores.

## Paso 2: Crear geometría de cuadrícula magenta

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

Esta geometría define el contorno de la cuadrícula que el visual brush rellenará.

## Paso 3: Diseñar VisualBrush de cuadrícula magenta

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

Aquí dibujamos una pequeña loseta magenta que se repetirá a lo largo de la cuadrícula.

## Paso 4: Aplicar VisualBrush a la cuadrícula

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

La llamada `CreateVisualBrush` vincula la loseta magenta a la geometría de la cuadrícula y habilita el mosaico.

## Paso 5: Añadir la cuadrícula al lienzo

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

Colocamos la cuadrícula en mosaico en un lienzo y aplicamos una transformación de traslación para que aparezca en la ubicación deseada.

## Paso 6: Añadir rectángulo transparente

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

En este paso **añadimos un rectángulo transparente** (la forma roja con `Opacity = 0.7f`). Ajusta el valor de opacidad para controlar cuán translúcido es el rectángulo.

## Paso 7: Guardar el documento

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

El archivo XPS se escribe en la carpeta que especificaste anteriormente.

## Casos de uso comunes

- **Resaltado de informes:** Superponer un rectángulo semi‑transparente para enfatizar un gráfico o tabla.  
- **Efectos de marca de agua:** Combinar una cuadrícula en mosaico con una superposición transparente para una marca sutil.  
- **PDFs/XPS interactivos:** Usa el patrón como fondo para campos de formulario manteniendo la UI legible.

## Consejos de solución de problemas

- **¿Opacidad no visible?** Asegúrate de que tu visor soporta transparencia XPS; algunos visores antiguos pueden ignorar la propiedad `Opacity`.  
- **¿Tamaño de loseta incorrecto?** Verifica que el rectángulo fuente (`new RectangleF(0f, 0f, 10f, 10f)`) coincida con las dimensiones de la loseta vectorial.  
- **¿Archivo no guardado?** Verifica que `dataDir` apunte a un directorio existente y con permisos de escritura.

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Page for .NET en aplicaciones web y de escritorio?**  
A: Sí, la biblioteca funciona en todos los tipos de aplicaciones .NET.

**Q: ¿Hay una versión de prueba disponible antes de comprar?**  
A: Por supuesto, puedes acceder a la prueba gratuita [aquí](https://releases.aspose.com/).

**Q: ¿Dónde puedo encontrar soporte adicional o discusiones de la comunidad?**  
A: Visita el [Aspose.Page Forum](https://forum.aspose.com/c/page/39) para obtener ayuda de la comunidad y los ingenieros de Aspose.

**Q: ¿Cómo puedo obtener una licencia temporal para evaluación?**  
A: Puedes adquirir una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

**Q: ¿Qué otra documentación está disponible para Aspose.Page for .NET?**  
A: Explora la documentación completa [aquí](https://reference.aspose.com/page/net/).

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}