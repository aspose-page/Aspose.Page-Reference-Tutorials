---
date: 2026-01-20
description: Aprenda a crear un documento XPS, añadir un rectángulo y guardar el archivo
  XPS usando Aspose.Page para .NET en esta guía paso a paso.
linktitle: Add Rectangle to XPS Document
second_title: Aspose.Page .NET API
title: 'Crear documento XPS: agregar rectángulo con Aspose.Page para .NET'
url: /es/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear documento XPS: agregar rectángulo con Aspose.Page para .NET

## Introducción

En este tutorial usted **creará archivos de documento XPS** y dibujará un rectángulo dentro de ellos usando la biblioteca Aspose.Page para .NET. Agregar formas como rectángulos es un requisito común cuando necesita generar facturas, informes o gráficos personalizados de forma programática. Siga los pasos a continuación y tendrá un archivo XPS listo para usar en minutos.

## Respuestas rápidas
- **¿Qué puedo generar?** Documentos XPS con gráficos vectoriales y texto.  
- **¿Qué biblioteca?** Aspose.Page para .NET (prueba gratuita disponible).  
- **¿Cuánto tiempo lleva?** Aproximadamente 5‑10 minutos para implementar y ejecutar.  
- **¿Necesito una licencia?** Se requiere una licencia temporal para uso en producción.  
- **¿Puedo guardar el resultado como archivo XPS?** Sí – el método `Save` escribe un **archivo XPS guardado** en disco.

## ¿Qué es “crear documento XPS”?

Crear un documento XPS significa construir programáticamente una descripción de página en el formato XML Paper Specification. El archivo resultante es independiente de la resolución, ideal para impresión y visualización de alta calidad en todas las plataformas.

## ¿Por qué usar Aspose.Page para crear documento XPS?

- **Soporte completo de .NET** – funciona con .NET Framework, .NET Core y .NET 5/6+.  
- **API de dibujo rica** – incluye geometría de rutas, pinceles, plumas y manejo de texto.  
- **Sin dependencias externas** – todo se ejecuta en proceso sin necesidad de Office o Acrobat.  

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. **Aspose.Page para .NET** – descárguelo [aquí](https://releases.aspose.com/page/net/).  
2. **Una carpeta con permisos de escritura** donde se almacenarán los archivos XPS generados.

## Importar espacios de nombres

En su proyecto .NET, importe los espacios de nombres requeridos:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Paso 1: establecer el directorio del documento

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **Consejo profesional:** Use una ruta absoluta o `Path.Combine` para evitar problemas de separador de rutas en diferentes sistemas operativos.

## Paso 2: crear un nuevo documento XPS

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

En este punto usted tiene un objeto **documento XPS creado** que contendrá todos los elementos de dibujo.

## Paso 3: agregar un rectángulo (usando create path geometry)

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

La llamada `CreatePathGeometry` **crea geometría de ruta** que define el contorno del rectángulo. Puede modificar la cadena de comandos similar a SVG para dibujar otras formas.

## Paso 4: guardar el documento (save XPS file)

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Llamar a `Save` escribe el **archivo XPS guardado** en la ubicación que especificó.

¡Felicidades! Ha creado exitosamente un **documento XPS**, agregado un rectángulo y guardado el archivo.

## Problemas comunes y soluciones

| Problema | Razón | Solución |
|----------|-------|----------|
| `FileNotFoundException` en `doc.Save` | `dataDir` apunta a una carpeta inexistente | Asegúrese de que el directorio exista o créelo con `Directory.CreateDirectory(dataDir)`. |
| El rectángulo no es visible | Falta el perfil de color del trazo o la geometría de ruta está malformada | Verifique la ruta del archivo ICC y la cadena de geometría (`M … Z`). |
| Ralentización del rendimiento en documentos grandes | Demasiadas llamadas individuales a `AddPath` | Agrupe operaciones de dibujo o reutilice objetos de pinceles/pluma. |

## Preguntas frecuentes

**P: ¿Es Aspose.Page compatible con todas las aplicaciones .NET?**  
R: Sí, Aspose.Page está diseñado para funcionar sin problemas con todas las aplicaciones .NET.

**P: ¿Dónde puedo encontrar la documentación de Aspose.Page para .NET?**  
R: La documentación está disponible [aquí](https://reference.aspose.com/page/net/).

**P: ¿Puedo probar Aspose.Page para .NET de forma gratuita antes de comprar?**  
R: Sí, puede obtener una prueba gratuita [aquí](https://releases.aspose.com/).

**P: ¿Cómo puedo obtener una licencia temporal para Aspose.Page para .NET?**  
R: Visite [este enlace](https://purchase.aspose.com/temporary-license/) para obtener una licencia temporal.

**P: ¿Dónde puedo buscar soporte de la comunidad o hacer preguntas relacionadas con Aspose.Page para .NET?**  
R: Visite el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para soporte de la comunidad.

---

**Última actualización:** 2026-01-20  
**Probado con:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}