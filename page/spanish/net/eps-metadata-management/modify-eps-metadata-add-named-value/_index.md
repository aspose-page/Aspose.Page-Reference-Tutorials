---
title: Agregar valor con nombre con Aspose.Page
linktitle: Agregar valor con nombre
second_title: Aspose.Página .NET API
description: Aprenda a agregar valores con nombre a archivos EPS en .NET usando Aspose.Page. Este completo tutorial le guiará a través del proceso paso a paso.
weight: 12
url: /es/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar valor con nombre con Aspose.Page

## Introducción

En el ámbito del procesamiento de documentos con .NET, Aspose.Page se destaca como una poderosa herramienta para manejar archivos EPS. Aspose.Page permite a los desarrolladores manipular metadatos XMP, facilitando tareas como agregar valores con nombre. Este tutorial lo guiará a través del proceso de agregar valores con nombre a un archivo EPS usando Aspose.Page paso a paso.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos del lenguaje de programación C#.
- Un entorno de desarrollo integrado (IDE) como Visual Studio instalado.
-  Aspose.Page para la biblioteca .NET. Si no está instalado, puede descargarlo desde[aquí](https://releases.aspose.com/page/net/).

## Importar espacios de nombres

En primer lugar, importemos los espacios de nombres necesarios a su código C#. Estos espacios de nombres son vitales para acceder a las funcionalidades proporcionadas por Aspose.Page:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Paso 1: inicializar el flujo de entrada del archivo EPS

 El paso inicial implica inicializar el flujo de entrada para el archivo EPS. Reemplazar`"Your Document Directory"` con la ruta a su directorio de documentos:

```csharp
// ExInicio:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Paso 2: obtenga metadatos XMP

Recupere metadatos XMP del archivo EPS. Si el archivo EPS carece de metadatos XMP, se creará uno nuevo, lleno de valores de los comentarios de metadatos de PS:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Paso 3: cambiar los valores de metadatos XMP

Ahora, hagamos cambios en los metadatos XMP. En este ejemplo, agregaremos un valor con nombre a la estructura "xmpTPg:MaxPageSize":

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Paso 4: guarde el archivo EPS con metadatos XMP modificados

Guarde el archivo EPS con los metadatos XMP actualizados. Cree un flujo de salida y guarde el archivo EPS modificado:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Conclusión

¡Felicidades! Ha agregado con éxito un valor con nombre a un archivo EPS usando Aspose.Page en .NET. Este tutorial lo ha guiado a través de los pasos esenciales, mostrando la simplicidad y efectividad de Aspose.Page en la manipulación de documentos.

## Preguntas frecuentes

### P1: ¿Aspose.Page es compatible con diferentes versiones de archivos EPS?

R1: Aspose.Page admite varias versiones de archivos EPS, lo que garantiza la compatibilidad con una amplia gama de documentos.

### P2: ¿Puedo utilizar Aspose.Page para proyectos comerciales?

 R2: Sí, Aspose.Page viene con una licencia comercial y puedes comprarla.[aquí](https://purchase.aspose.com/buy).

### P3: ¿Hay una prueba gratuita disponible para Aspose.Page?

 R3: Sí, puedes explorar Aspose.Page con una prueba gratuita disponible[aquí](https://releases.aspose.com/).

### P4: ¿Cómo puedo obtener soporte o conectarme con la comunidad Aspose?

 A4: Visita el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para obtener apoyo y conectarse con la comunidad.

### P5: ¿Qué es una licencia temporal y cómo puedo obtenerla?

 R5: Si necesita una licencia temporal para fines de prueba o evaluación, puede adquirir una[aquí](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
