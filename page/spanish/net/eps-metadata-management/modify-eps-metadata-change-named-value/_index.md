---
title: Cambiar el valor con nombre con Aspose.Page para .NET
linktitle: Cambiar valor con nombre
second_title: Aspose.Página .NET API
description: Aprenda a cambiar valores con nombre en archivos EPS usando Aspose.Page para .NET. Personalice los metadatos XMP sin esfuerzo para un procesamiento de documentos personalizado.
weight: 16
url: /es/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cambiar el valor con nombre con Aspose.Page para .NET

## Introducción

En el mundo del procesamiento de documentos, Aspose.Page para .NET destaca como una poderosa herramienta para manipular archivos EPS. Una de las funcionalidades clave que ofrece es la capacidad de cambiar valores con nombre dentro de los metadatos XMP. Este tutorial lo guiará a través del proceso de cambiar un valor con nombre usando Aspose.Page para .NET, permitiéndole personalizar sus archivos EPS de acuerdo con sus necesidades específicas.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

-  Aspose.Page para .NET: asegúrese de tener instalada la biblioteca Aspose.Page para .NET. Si no, puedes descargarlo.[aquí](https://releases.aspose.com/page/net/).

- Directorio de documentos: tenga un directorio designado para sus archivos EPS donde pueda realizar los cambios de valores nombrados.

## Importar espacios de nombres

En su proyecto .NET, necesita importar los espacios de nombres necesarios para acceder a la funcionalidad proporcionada por Aspose.Page. Agregue los siguientes espacios de nombres a su código:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ahora, dividamos el código en varios pasos para una comprensión integral:

## Paso 1: inicializar el flujo de entrada del archivo EPS

```csharp
// ExInicio:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// Fin final: 1
```

En este paso, configuramos el flujo de entrada para el archivo EPS que desea modificar. Asegúrese de reemplazar "Su directorio de documentos" con la ruta real a su directorio de documentos.

## Paso 2: obtenga metadatos XMP

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Recupere los metadatos XMP existentes del archivo EPS. Si el archivo EPS no contiene metadatos XMP, se generará uno nuevo con valores de los comentarios de metadatos PS.

## Paso 3: cambiar los valores de metadatos XMP

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Aquí, demostramos cómo cambiar dos valores con nombre dentro de la estructura "xmpTPg:MaxPageSize". Puede personalizar esto según sus requisitos específicos.

## Paso 4: guarde el archivo EPS con metadatos XMP modificados

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Guarde el archivo EPS modificado en el flujo de salida. El archivo ahora reflejará los cambios realizados en los metadatos XMP.

## Conclusión

Con este tutorial, ha aprendido cómo aprovechar Aspose.Page para .NET para cambiar los valores con nombre dentro de los metadatos XMP en archivos EPS. Esta funcionalidad abre un mundo de posibilidades para personalizar y adaptar sus documentos para cumplir con requisitos específicos.

## Preguntas frecuentes

### P1: ¿Puedo utilizar Aspose.Page para .NET con otros formatos de documentos?

R1: Sí, Aspose.Page admite varios formatos de documentos, incluidos EPS, XPS y PDF.

### P2: ¿Existe una versión de prueba disponible de Aspose.Page para .NET?

 R2: Sí, puedes acceder a una prueba gratuita[aquí](https://releases.aspose.com/).

### P3: ¿Dónde puedo encontrar más documentación sobre Aspose.Page para .NET?

 A3: consulte la documentación[aquí](https://reference.aspose.com/page/net/).

### P4: ¿Cómo puedo obtener una licencia temporal de Aspose.Page para .NET?

 R4: Puede obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).

### P5: ¿Qué opciones de soporte están disponibles para los usuarios de Aspose.Page para .NET?

 A5: Visita el foro de la comunidad[aquí](https://forum.aspose.com/c/page/39) para apoyo y discusiones.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
