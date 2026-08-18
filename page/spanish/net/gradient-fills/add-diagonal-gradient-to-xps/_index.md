---
date: 2026-02-23
description: Aprende a crear documentos XPS con degradado diagonal usando Aspose.Page
  para .NET y eleva tus presentaciones visuales sin esfuerzo.
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: Crear gradiente diagonal XPS con Aspose.Page para .NET
url: /es/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear XPS con degradado diagonal usando Aspose.Page para .NET

## Introducción

Si necesitas **crear archivos XPS con degradado diagonal** que llamen la atención, Aspose.Page para .NET lo hace sencillo. En este tutorial aprenderás a añadir un degradado diagonal a un documento XPS, paso a paso, usando la API de Aspose.Page. Al final tendrás un patrón reutilizable que podrás adaptar a cualquier forma o combinación de colores.

## Respuestas rápidas
- **¿Qué hace el método de la API?** Crea un pincel de degradado lineal que se extiende diagonalmente a lo largo de una ruta.  
- **¿Qué clase representa el documento XPS?** `XpsDocument`.  
- **¿Necesito una licencia para ejecutar el ejemplo?** Una prueba gratuita funciona para desarrollo; se requiere una licencia para producción.  
- **¿Puedo cambiar la dirección del degradado?** Sí—ajusta los valores `PointF` de inicio y fin.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## ¿Qué es **crear XPS con degradado diagonal**?
Un degradado diagonal es una transición de color suave que va de una esquina de una forma a la esquina opuesta. En XPS, este efecto se logra aplicando un `LinearGradientBrush` a la propiedad de relleno de una ruta. La biblioteca Aspose.Page abstrae el marcado XPS de bajo nivel, permitiéndote centrarte en los colores y la geometría.

## ¿Por qué usar Aspose.Page para degradados diagonales?
- **Renderizado de alta fidelidad** – la salida coincide exactamente con la especificación XPS.  
- **Integración completa con .NET** – funciona con C#, VB.NET y cualquier lenguaje .NET.  
- **Sin dependencias externas** – todo se maneja en proceso, sin COM ni Office.  
- **Escalable a documentos complejos** – puedes combinar múltiples degradados, imágenes y texto en la misma página.

## Requisitos previos

1. **Biblioteca Aspose.Page para .NET** – descárgala [aquí](https://releases.aspose.com/page/net/).  
2. **Entorno de desarrollo** – Visual Studio, Rider o cualquier editor que admita proyectos .NET.  

Ahora, vamos a sumergirnos en el código.

## Importar espacios de nombres

En tu proyecto .NET, incluye los espacios de nombres necesarios de la biblioteca Aspose.Page para acceder a las clases y métodos requeridos. Añade los siguientes espacios de nombres al comienzo de tu código:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Paso 1: Establecer el directorio del documento

Comienza especificando la ruta a tu directorio de documentos. Aquí es donde se guardará el documento XPS resultante con el degradado diagonal.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Paso 2: Crear un nuevo documento XPS

Inicializa un nuevo `XpsDocument` usando la biblioteca Aspose.Page.

```csharp
XpsDocument doc = new XpsDocument();
```

## Paso 3: Definir los colores del degradado

Crea una lista de objetos `XpsGradientStop`, cada uno representando un color en el degradado diagonal.

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## Paso 4: Añadir un degradado diagonal a una ruta

Crea una nueva ruta con una geometría definida y aplica el degradado diagonal a ella. Ajusta la transformación de renderizado y las propiedades de relleno según sea necesario.

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## Paso 5: Guardar el documento XPS resultante

Finalmente, guarda el documento XPS modificado en el directorio especificado.

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

Has creado con éxito un archivo **XPS con degradado diagonal**. Siéntete libre de experimentar con diferentes paradas de color, cadenas de geometría o matrices de transformación para producir una variedad de efectos visuales.

## Problemas comunes y soluciones
- **Degradado no visible** – Verifica que la geometría de la ruta esté cerrada y que los puntos de inicio/fin del pincel estén dentro de los límites de la ruta.  
- **Colores incorrectos** – Asegúrate de usar `CreateColor` con los valores ARGB correctos; el método espera valores en el rango 0‑255.  
- **Archivo no guardado** – Comprueba que `dataDir` apunte a una carpeta existente y que la aplicación tenga permisos de escritura.

## Preguntas frecuentes

**P: ¿Puedo aplicar varios degradados a diferentes partes del documento?**  
R: Sí, puedes crear múltiples rutas y aplicar degradados distintos a cada una.

**P: ¿Existen estilos de degradado predefinidos disponibles?**  
R: Aspose.Page permite degradados personalizados, dándote control total sobre las transiciones de color.

**P: ¿Puedo usar Aspose.Page para .NET con otros formatos de documento?**  
R: Aspose.Page se centra principalmente en la manipulación de documentos XPS.

**P: ¿Cómo puedo manejar errores relacionados con el procesamiento del documento?**  
R: Consulta la [documentación](https://reference.aspose.com/page/net/) para obtener buenas prácticas de manejo de errores.

**P: ¿Hay una versión de prueba disponible antes de comprar?**  
R: Sí, puedes explorar la [prueba gratuita](https://releases.aspose.com/) para experimentar con Aspose.Page para .NET.

**P: ¿Cómo cambio la dirección del degradado a vertical u horizontal?**  
R: Modifica los argumentos `PointF` en `CreateLinearGradientBrush` para establecer nuevos puntos de inicio y fin.

**P: ¿La biblioteca admite transparencia en los degradados?**  
R: Sí—incluye un valor alfa al crear colores con `CreateColor`.

## Conclusión

Aspose.Page para .NET simplifica el proceso de mejorar documentos XPS con degradados diagonales. Esta guía te llevó paso a paso desde la configuración de los requisitos previos hasta el guardado del archivo final. Sigue experimentando con diferentes formas y paletas de colores para que tus informes, folletos o facturas XPS realmente destaquen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-02-23  
**Probado con:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

---