---
date: 2026-02-25
description: Aprende a crear un degradado XPS con relleno horizontal usando Aspose.Page
  para .NET. Eleva el atractivo visual sin esfuerzo en tus documentos.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'Crear degradado XPS: relleno horizontal con Aspose.Page para .NET'
url: /es/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear degradado XPS – Añadir degradado horizontal a XPS con Aspose.Page para .NET

## Introducción

En este tutorial **creará rellenos con degradado XPS** que se extienden horizontalmente a lo largo de sus páginas. Añadir un degradado horizontal puede hacer que un documento XPS luzca más pulido y atractivo al instante, especialmente para informes, folletos o cualquier salida visualmente rica. Recorreremos todo el proceso usando Aspose.Page para .NET, desde la configuración del entorno hasta guardar el archivo XPS final.

## Respuestas rápidas
- **¿Qué cubre este tutorial?** Añadir un degradado horizontal a un documento XPS con Aspose.Page para .NET.  
- **¿Qué biblioteca se requiere?** Aspose.Page para .NET (cualquier versión reciente).  
- **¿Necesito una licencia?** Una versión de prueba funciona para desarrollo; se necesita una licencia comercial para producción.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 5–10 minutos para un degradado básico.  
- **¿Puedo cambiar la dirección del degradado?** Sí – modifique los puntos de inicio/fin del `LinearGradientBrush`.

## Cómo crear un degradado XPS con Aspose.Page para .NET

A continuación encontrará una guía paso a paso que explica **por qué** existe cada línea de código, no solo **qué** hace. Siéntase libre de seguirla en Visual Studio o su editor .NET preferido.

## Requisitos previos

Antes de comenzar, asegúrese de contar con los siguientes requisitos:

1. Biblioteca Aspose.Page para .NET: Asegúrese de que la biblioteca Aspose.Page para .NET esté instalada en su entorno de desarrollo. Puede descargarla desde la [documentación de Aspose.Page para .NET](https://reference.aspose.com/page/net/).

2. Entorno de desarrollo: Configure un entorno de desarrollo adecuado, incluido un editor de código como Visual Studio.

## Importar espacios de nombres

Comience importando los espacios de nombres necesarios en su proyecto. Estos espacios de nombres son esenciales para trabajar con Aspose.Page para .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Ahora, desglosaremos el ejemplo proporcionado en varios pasos.

## Paso 1: Establecer la ruta del directorio del documento

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Paso 2: Crear un nuevo documento XPS

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Paso 3: Inicializar las paradas del degradado

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Paso 4: Crear una nueva ruta

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Paso 5: Guardar el documento XPS resultante

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Ahora, ha añadido con éxito un degradado horizontal a su documento XPS usando Aspose.Page para .NET.

## Problemas comunes y soluciones

| Problema | Razón | Solución |
|----------|-------|----------|
| El degradado aparece como color sólido | Las paradas del degradado no se añadieron correctamente | Asegúrese de que `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` se ejecute después de establecer el pincel. |
| El archivo guardado está vacío | `dataDir` apunta a una carpeta inexistente | Verifique que la carpeta exista o use una ruta absoluta. |
| Error de compilación en `PointF` | Falta la referencia a `System.Drawing` | Añada una referencia a `System.Drawing.Common` (para .NET Core/5+). |

## Preguntas frecuentes

### Q1: ¿Dónde puedo encontrar la documentación de Aspose.Page para .NET?

A1: Puede encontrar la documentación [aquí](https://reference.aspose.com/page/net/).

### Q2: ¿Cómo descargo Aspose.Page para .NET?

A2: Puede descargar la biblioteca desde la [página de descarga de Aspose.Page para .NET](https://releases.aspose.com/page/net/).

### Q3: ¿Dónde puedo comprar Aspose.Page para .NET?

A3: Puede comprar Aspose.Page para .NET en la [página de compra](https://purchase.aspose.com/buy).

### Q4: ¿Hay una versión de prueba gratuita disponible?

A4: Sí, puede obtener una prueba gratuita [aquí](https://releases.aspose.com/).

### Q5: ¿Cómo obtengo una licencia temporal para Aspose.Page para .NET?

A5: Puede obtener una licencia temporal desde [este enlace](https://purchase.aspose.com/temporary-license/).

## Preguntas frecuentes adicionales

**P: ¿Puedo usar esta técnica de degradado con documentos XPS que ya contienen imágenes?**  
R: Absolutamente. El degradado se aplica a una capa de ruta, por lo que las imágenes existentes permanecen sin cambios.

**P: ¿Es posible crear un degradado vertical en su lugar?**  
R: Sí. Cambie los puntos de inicio y fin del `LinearGradientBrush` para que tengan diferentes coordenadas Y mientras mantiene constante la X.

**P: ¿Aspose.Page es compatible con .NET Core?**  
R: La biblioteca es totalmente compatible con .NET Core, .NET 5 y versiones posteriores.

**P: ¿Cómo puedo reutilizar el mismo degradado en varias páginas?**  
R: Cree el `XpsLinearGradientBrush` una vez, guárdelo en una variable y asígnelo a las rutas en cada página.

## Conclusión

Mejorar sus documentos XPS con degradados no solo aumenta el atractivo visual, sino que también brinda una experiencia de usuario más atractiva. Con Aspose.Page para .NET, puede **crear degradados XPS** rápidamente y de forma fiable, dando a sus informes, folletos o libros electrónicos un acabado profesional.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-02-25  
**Probado con:** Aspose.Page para .NET 24.11  
**Autor:** Aspose  

---