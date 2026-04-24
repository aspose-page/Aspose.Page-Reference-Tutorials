---
date: 2026-01-05
description: Aprenda a recortar documentos XPS usando Aspose.Page para .NET. Esta
  guía paso a paso le muestra cómo crear, manipular y guardar archivos XPS de manera
  eficiente.
linktitle: Clipping XPS
second_title: Aspose.Page .NET API
title: Cómo recortar XPS con Aspose.Page para .NET
url: /es/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo recortar XPS con Aspose.Page for .NET

## Introducción

¡Bienvenido a este tutorial completo sobre **cómo recortar XPS** usando Aspose.Page for .NET! En esta guía, le mostraremos el proceso de crear, manipular y guardar documentos XPS con la biblioteca. XPS, o XML Paper Specification, es un formato de documento estandarizado y abierto, y Aspose.Page for .NET proporciona herramientas potentes para trabajar con documentos XPS en sus aplicaciones .NET.

## Respuestas rápidas
- **¿Qué es recortar XPS?** Aplicar una máscara geométrica (clip) para limitar el área visible de los elementos del lienzo XPS.  
- **¿Qué biblioteca es la mejor para esto?** Aspose.Page for .NET ofrece una API completa para la creación y recorte de XPS.  
- **¿Requisitos previos?** Visual Studio, tiempo de ejecución .NET y la biblioteca Aspose.Page for .NET.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un escenario básico de recorte.  
- **¿Puedo usar esto en producción?** Sí, con una licencia válida de Aspose (prueba disponible).

## Qué es “recortar XPS”
El recorte en XPS funciona definiendo una **geometría de recorte** (por ejemplo, un círculo o un rectángulo) y asignándola a un lienzo. Todo lo dibujado fuera de esa geometría no se renderiza, lo que permite crear diseños de página sofisticados como imágenes enmascaradas, formas personalizadas o áreas de contenido enfocadas.

## ¿Por qué usar Aspose.Page for .NET para recortar XPS?
- **Control total** sobre transformaciones del lienzo, geometrías de ruta y pinceles.  
- **Sin dependencias externas** – todo se ejecuta dentro de su aplicación .NET.  
- **Compatibilidad multiplataforma** para .NET Framework, .NET Core y .NET 5/6+.  
- **Alto rendimiento** con una API ligera que escribe archivos XPS válidos.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio instalado en su máquina.  
- Biblioteca Aspose.Page for .NET añadida a su proyecto. Puede descargarla [aquí](https://releases.aspose.com/page/net/).  
- Conocimientos básicos del lenguaje de programación C#.

## Importar espacios de nombres

Para usar las funcionalidades de Aspose.Page for .NET, necesita importar los espacios de nombres requeridos en su proyecto. Siga estos pasos:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Ahora, desglosaremos el código de ejemplo que proporcionó en varios pasos.

## Paso 1: Establecer la ruta del directorio del documento.

```csharp
string dataDir = "Your Document Directory";
```

Asegúrese de reemplazar "Your Document Directory" con la ruta real a su directorio de documentos.

## Paso 2: Crear un nuevo documento XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

Esto crea un nuevo documento XPS con el que trabajará.

## Paso 3: Crear el lienzo principal.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

Este paso crea el lienzo principal, que es común para todos los elementos de la página.

## Paso 4: Establecer los desplazamientos izquierdo y superior en el lienzo principal.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Ajuste los desplazamientos izquierdo y superior según sus requisitos.

## Paso 5: Crear una geometría de ruta de rectángulo.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

## Paso 6: Crear un relleno para los rectángulos.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Defina el color de relleno para los rectángulos.

## Paso 7: Añadir otro lienzo con recorte al lienzo principal.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

## Paso 8: Crear una geometría circular para el recorte.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Esto crea una geometría de recorte circular y la aplica al segundo lienzo.

## Paso 9: Crear un rectángulo en el segundo lienzo y rellenarlo.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Paso 10: Añadir el segundo lienzo con un rectángulo contorneado al lienzo principal.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

## Paso 11: Crear un rectángulo en el tercer lienzo y contornearlo.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

## Paso 12: Guardar el documento XPS resultante.

```csharp
doc.Save(dataDir + "output2.xps");
```

## Problemas comunes y soluciones
- **Ruta inválida** – Asegúrese de que `dataDir` termine con una barra invertida (`\\`) o use `Path.Combine`.  
- **Recorte no aplicado** – Verifique que la cadena de geometría de recorte esté bien formada; un espacio faltante puede hacer que se ignore el recorte.  
- **Excepción de licencia** – En una compilación no de evaluación, añada una licencia válida de Aspose antes de crear el documento para evitar excepciones en tiempo de ejecución.

## Preguntas frecuentes

### Q1: ¿Puedo usar Aspose.Page for .NET con otros formatos de documento?

A1: Aspose.Page for .NET se centra principalmente en documentos XPS, pero Aspose ofrece otras bibliotecas para varios formatos de documento.

### Q2: ¿Es Aspose.Page for .NET adecuado para principiantes?

A2: Sí, Aspose.Page for .NET está diseñado para ser fácil de usar, y los principiantes pueden comprender rápidamente sus funcionalidades con la documentación adecuada.

### Q3: ¿Dónde puedo encontrar más ejemplos y recursos?

A3: Visite la [documentación](https://reference.aspose.com/page/net/) y el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para obtener recursos y ejemplos extensos.

### Q4: ¿Cómo puedo obtener una licencia temporal para Aspose.Page for .NET?

A4: Puede obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

### Q5: ¿Hay una prueba gratuita disponible para Aspose.Page for .NET?

A5: Sí, puede explorar la prueba gratuita [aquí](https://releases.aspose.com/).

## Preguntas frecuentes adicionales

**P: ¿Puedo combinar múltiples geometrías de recorte en un solo lienzo?**  
**R:** Sí, puede asignar un `PathGeometry` complejo que contenga varias sub‑rutas a la propiedad `Clip`, lo que permite enmascarado en capas.

**P: ¿El recorte afecta la conversión a PDF?**  
**R:** Cuando convierta posteriormente el XPS a PDF usando Aspose.PDF, la geometría de recorte se conserva, por lo que el resultado visual sigue siendo idéntico.

**P: ¿Es posible animar el recorte en XPS?**  
**R:** XPS en sí no admite animación; sin embargo, puede generar una serie de páginas XPS con diferentes formas de recorte para simular movimiento.

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}