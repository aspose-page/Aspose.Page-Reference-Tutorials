---
date: 2026-01-05
description: Aprende a transformar documentos XPS sin esfuerzo con Aspose.Page para
  .NET. Sigue nuestra guía paso a paso para lograr transformaciones sin problemas.
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: Cómo transformar XPS con Aspose.Page para .NET
url: /es/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo transformar XPS con Aspose.Page para .NET

## Introducción

Bienvenido al mundo de Aspose.Page para .NET, una biblioteca potente que le permite realizar diversas transformaciones en documentos XPS sin esfuerzo. **En este tutorial, descubrirá cómo transformar documentos XPS usando Aspose.Page para .NET**, ya sea que sea un desarrollador experimentado o que recién esté comenzando. Recorreremos cada paso, explicaremos el razonamiento detrás de cada transformación y le daremos consejos prácticos que podrá aplicar en proyectos reales.

## Respuestas rápidas
- **¿Qué puedes lograr?** Crear, trasladar, escalar y rotar elementos del lienzo XPS de forma programática.  
- **¿Qué biblioteca se requiere?** Aspose.Page para .NET (última versión).  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Plataformas compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para las transformaciones básicas mostradas aquí.

## ¿Qué es “how to transform xps”?
La frase *how to transform xps* se refiere a modificar programáticamente el diseño, tamaño y orientación de los elementos dentro de un documento XPS (XML Paper Specification). Con Aspose.Page, puede aplicar transformaciones basadas en matrices a los lienzos, lo que le brinda un control granular sobre la posición, escala y rotación sin editar manualmente el XML de XPS.

## ¿Por qué usar Aspose.Page para transformaciones XPS?
- **Integración completa con .NET** – funciona sin problemas con Visual Studio, Rider y otros IDEs.  
- **Sin dependencias externas** – la API maneja todos los detalles de bajo nivel de XPS por usted.  
- **Amplio soporte de transformaciones** – trasladar, escalar, rotar y combinar múltiples transformaciones en una sola llamada.  
- **Optimizada para rendimiento** – adecuada para generar informes, facturas o cualquier gráfico imprimible al vuelo.

## Requisitos previos

Antes de comenzar, asegúrese de tener:

- **Biblioteca Aspose.Page para .NET** – descárguela e instálela desde la documentación oficial: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **Entorno de desarrollo** – Visual Studio, Visual Studio Code o cualquier otro IDE compatible con .NET.  
- **Directorio de documentos** – una carpeta en su máquina donde leerá/escribirá archivos XPS. Reemplace el marcador de posición en el código con la ruta real.

Ahora que tenemos todo listo, vamos al código.

## Importar espacios de nombres

Primero, importe los espacios de nombres que exponen las clases de Aspose.Page que necesitará:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Cómo transformar XPS – Guía paso a paso

### Paso 1: Crear un nuevo documento XPS

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Explicación*: Definimos la carpeta que contiene nuestros archivos de origen y salida, luego instanciamos un `XpsDocument` vacío. Este objeto será el lienzo para todas las transformaciones posteriores.

### Paso 2: Crear un lienzo principal

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Por qué es importante*: El lienzo principal actúa como contenedor para todos los demás lienzos. Al aplicar un pequeño desplazamiento garantizamos que el contenido no se recorte en el borde de la página.

### Paso 3: Crear una geometría de ruta de rectángulo

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Consejo*: La cadena de ruta sigue la sintaxis estándar de rutas XPS (`M` para mover, `L` para línea, `Z` para cerrar). Ajuste las coordenadas para cambiar el tamaño del rectángulo.

### Paso 4: Añadir un relleno para rectángulos

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Pro tip*: Use `CreateColor` con valores RGB para coincidir con la paleta de su marca.

### Paso 5: Añadir un nuevo lienzo sin transformaciones

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Aquí simplemente colocamos un rectángulo en la página sin transformación adicional—útil como elemento de referencia.

### Paso 6: Añadir un nuevo lienzo con transformación de traslación

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*¿Qué está ocurriendo?* La primera matriz mueve el rectángulo 200 unidades hacia abajo. La llamada subsiguiente a `Translate` lo desplaza 500 unidades a la derecha, demostrando cómo se pueden encadenar múltiples traslaciones.

### Paso 7: Añadir un nuevo lienzo con transformación de escala doble

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*¿Por qué escalar?* Escalar por 2 duplica el ancho y la altura del rectángulo, permitiéndole crear gráficos más grandes sin redefinir la geometría.

### Paso 8: Añadir un nuevo lienzo con transformación de rotación alrededor de un punto

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Idea clave*: `RotateAround` gira el lienzo alrededor de un punto personalizado (aquí (100, 50)), dándole control fino sobre el ancla de rotación.

### Paso 9: Guardar el documento XPS resultante

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

Después de aplicar todas las transformaciones, el documento se guarda en `output1.xps`. Abra el archivo en cualquier visor XPS para ver los rectángulos apilados con sus respectivas traslaciones, escalas y rotaciones.

## Problemas comunes y solución de problemas

| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| Archivo de salida vacío | `dataDir` apunta a una carpeta inexistente | Asegúrese de que el directorio exista o use una ruta absoluta |
| Los rectángulos no se posicionan como se espera | Valores de matriz incorrectos | Verifique el orden de las llamadas a `Translate`, `Scale` y `RotateAround` |
| Los colores aparecen incorrectos | Valores RGB fuera del rango 0‑255 | Use valores de byte válidos para cada canal |

## Preguntas frecuentes

**P: ¿Aspose.Page para .NET es compatible con todos los entornos de desarrollo .NET?**  
R: Sí, funciona sin problemas con Visual Studio, Visual Studio Code, Rider y cualquier IDE que soporte .NET.

**P: ¿Dónde puedo encontrar ejemplos adicionales y documentación detallada de la API?**  
R: Visite la documentación oficial en [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**P: ¿Puedo probar Aspose.Page antes de comprar una licencia?**  
R: Absolutamente. Una prueba gratuita está disponible aquí: [Aspose.Page Free Trial](https://releases.aspose.com/).

**P: ¿Cómo obtengo una licencia temporal para pruebas?**  
R: Puede solicitar una a través de la página de licencia temporal: [Temporary License](https://purchase.aspose.com/temporary-license/).

**P: ¿Dónde compro una licencia completa?**  
R: Compre directamente en la tienda de Aspose: [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**Última actualización:** 2026-01-05  
**Probado con:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}