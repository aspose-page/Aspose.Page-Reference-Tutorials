---
date: 2026-02-25
description: Aprende a crear documentos XPS y aplicar un degradado lineal con Aspose.Page
  para .NET. Sigue nuestra guía paso a paso para guardar el archivo XPS.
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: Crear documento XPS con degradado vertical usando Aspose.Page
url: /es/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Añadir degradado vertical a XPS con Aspose.Page para .NET

## Introducción

En este tutorial **creará un documento XPS** que presenta un degradado vertical suave. Añadir degradados es una forma común de hacer que los archivos XPS se vean más profesionales, perfecto para informes, folletos o cualquier gráfico imprimible. Le guiaremos paso a paso, desde la configuración del proyecto hasta guardar el archivo XPS final, para que pueda aplicar rápidamente un degradado lineal a cualquier ruta.

## Respuestas rápidas
- **¿Qué cubre este tutorial?** Añadir un degradado lineal vertical a una ruta en un documento XPS.  
- **¿Qué biblioteca se requiere?** Aspose.Page para .NET.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un ejemplo básico.  
- **¿Puedo guardar el resultado como archivo XPS?** Sí, el método `Save` escribe el archivo en el disco.

## ¿Qué es un degradado vertical en XPS?

Un degradado vertical es una transición de color que va desde la parte superior de una forma hasta la inferior. En XPS, esto se logra con un **pincel de degradado lineal** que define los puntos de inicio y fin, además de una colección de puntos de degradado que controlan el color en posiciones específicas.

## ¿Por qué usar Aspose.Page para crear documentos XPS con degradados?

- **Integración completa con .NET** – funciona con .NET Framework, .NET Core y .NET 5/6+.  
- **Sin dependencias externas** – todo el renderizado lo gestiona la biblioteca.  
- **Alta fidelidad** – los degradados se renderizan exactamente como se definen, cumpliendo la especificación XPS.  
- **Fácil de mantener** – modelo de objetos claro para rutas, pinceles y colores.

## Requisitos previos

- Biblioteca Aspose.Page para .NET: Asegúrese de que tiene la biblioteca Aspose.Page para .NET instalada en su entorno de desarrollo. Puede descargarla [aquí](https://releases.aspose.com/page/net/).
- Entorno de desarrollo: Configure un entorno de desarrollo .NET con su IDE preferido, como Visual Studio.

Ahora que todo está listo, sumérjase en el código.

## Importar espacios de nombres

En su aplicación .NET, incluya los espacios de nombres necesarios para acceder a las clases y métodos de Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Paso 1: Configurar el directorio del documento

Defina la carpeta donde se guardará el archivo XPS generado.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Paso 2: Crear un nuevo documento XPS

Instancie un documento XPS nuevo que luego rellenaremos con una ruta rellena de degradado.

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Paso 3: Definir los puntos de degradado

Los puntos de degradado determinan los colores y sus posiciones a lo largo de la línea del degradado. Aquí creamos cinco puntos para producir una transición vertical suave.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Paso 4: Crear una ruta con degradado

Dibujamos una ruta con forma de rectángulo y aplicamos un **pincel de degradado lineal** que corre verticalmente desde el punto (10, 110) hasta el punto (10, 200). El pincel recibe los puntos de degradado definidos anteriormente.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Paso 5: Guardar el documento XPS resultante

Finalmente, escriba el documento XPS en disco. Este paso de **guardar archivo XPS** produce `AddVerticalGradient_outXPS.xps` en la carpeta que especificó.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**Consejo profesional:** Verifique la salida abriendo el archivo XPS en Windows XPS Viewer o cualquier visor de terceros para asegurarse de que el degradado se muestra como se espera.

## Problemas comunes y solución de problemas

| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| El degradado aparece como color sólido | Los puntos de degradado no se añadieron al pincel | Asegúrese de que `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` se ejecute. |
| Archivo no encontrado al guardar | `dataDir` apunta a una carpeta inexistente | Cree el directorio primero o use una ruta absoluta. |
| Los colores se ven diferentes | Los valores de color usan orden ARGB; verifique el orden de los canales | Use `CreateColor(alpha, red, green, blue)` correctamente. |

## Preguntas frecuentes

**P: ¿Es Aspose.Page compatible con Visual Studio 2019?**  
R: Sí, Aspose.Page es compatible con Visual Studio 2019. Asegúrese de tener la versión correcta de la biblioteca instalada.

**P: ¿Puedo usar Aspose.Page para proyectos comerciales?**  
R: Sí, Aspose.Page puede usarse para proyectos comerciales. Visite [aquí](https://purchase.aspose.com/buy) para explorar las opciones de licencia.

**P: ¿Hay una prueba gratuita disponible?**  
R: Sí, puede obtener una prueba gratuita de Aspose.Page [aquí](https://releases.aspose.com/).

**P: ¿Dónde puedo encontrar la documentación de Aspose.Page?**  
R: La documentación está disponible [aquí](https://reference.aspose.com/page/net/).

**P: ¿Cómo puedo obtener soporte o hacer preguntas?**  
R: Visite el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para soporte de la comunidad.

## Conclusión

Ahora sabe cómo **crear un documento XPS**, **aplicar un degradado lineal** y **guardar el archivo XPS** usando Aspose.Page para .NET. Este enfoque le brinda control total sobre el estilo visual en las salidas XPS, haciendo que sus documentos imprimibles destaquen.

---  

**Última actualización:** 2026-02-25  
**Probado con:** Aspose.Page para .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}