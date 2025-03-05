---
title: Agregue propiedades simples con Aspose.Page para .NET
linktitle: Agregar propiedades simples
second_title: Aspose.Página .NET API
description: Mejore archivos EPS con Aspose.Page para .NET. Agregue propiedades simples sin esfuerzo para obtener metadatos de documentos personalizados.
type: docs
weight: 14
url: /es/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---
## Introducción

En el ámbito de la manipulación y mejora de documentos, Aspose.Page para .NET surge como una herramienta poderosa que brinda a los desarrolladores la capacidad de agregar y modificar metadatos XMP dentro de archivos EPS sin problemas. Este tutorial lo guiará a través del proceso de agregar propiedades simples a un archivo EPS usando Aspose.Page para .NET.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

1.  Aspose.Page para .NET: asegúrese de tener Aspose.Page para .NET instalado en su entorno de desarrollo. Si no, puedes descargarlo.[aquí](https://releases.aspose.com/page/net/).

2.  Directorio de documentos: configure un directorio para almacenar sus archivos EPS. Actualizar el`dataDir` variable en el fragmento de código proporcionado con la ruta a su directorio de documentos.

## Importar espacios de nombres

Para comenzar, importe los espacios de nombres necesarios para permitir la comunicación con Aspose.Page para .NET. Agregue las siguientes líneas al comienzo de su archivo de código:

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

```csharp
// ExInicio:1
// La ruta al directorio de documentos.
string dataDir = "Your Document Directory";
// Inicializar el flujo de entrada del archivo EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Crear una instancia de PsDocument a partir de una secuencia
PsDocument document = new PsDocument(psStream);
```

## Paso 2: obtenga metadatos XMP

```csharp
// Obtenga metadatos XMP. Si el archivo EPS no contiene metadatos XMP, obtenemos uno nuevo lleno de valores de los comentarios de metadatos de PS (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Paso 3: cambiar los valores de metadatos XMP

```csharp
// Cambiar valores de metadatos XMP
DateTime now = DateTime.UtcNow;

// Agregar propiedad entera
xmp.Add("xmp:Intg1", new XmpValue(111));

// Agregar propiedad FechaHora
xmp.Add("xmp:Date1", new XmpValue(now));

// Agregar propiedad doble
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//Agregar propiedad de cadena
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## Paso 4: guarde el archivo EPS con metadatos XMP modificados

```csharp
// Guarde el archivo EPS con metadatos XMP modificados

// Crear flujo de salida
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Guardar archivo EPS
    document.Save(outPsStream);
}
```

## Paso 5: cierre FileStream

```csharp
finally
{
    psStream.Close();
}
```

Si sigue estos pasos, podrá incorporar fácilmente propiedades simples en sus archivos EPS utilizando Aspose.Page para .NET.

## Conclusión

En conclusión, Aspose.Page para .NET demuestra ser un activo invaluable para los desarrolladores que buscan mejorar archivos EPS con metadatos XMP personalizados. Al agregar propiedades simples, puede personalizar y enriquecer sus documentos para cumplir con requisitos específicos, abriendo un mundo de posibilidades para la manipulación de documentos.

## Preguntas frecuentes

### P1: ¿Aspose.Page para .NET es compatible con todos los archivos EPS?

R1: Aspose.Page para .NET admite una amplia gama de archivos EPS. Sin embargo, la compatibilidad puede variar según la complejidad y estructura de los archivos individuales.

### P2: ¿Puedo modificar los metadatos XMP existentes con Aspose.Page para .NET?

R2: ¡Absolutamente! Como se demuestra en este tutorial, puede cambiar fácilmente los valores de metadatos XMP existentes o agregar otros nuevos que se adapten a sus necesidades.

### P3: ¿Existe alguna limitación en cuanto a los tipos de propiedades que puedo agregar?

R3: Aspose.Page para .NET admite varios tipos de datos para propiedades, incluidos números enteros, fechas, dobles y cadenas. Tiene flexibilidad para elegir el tipo apropiado para sus metadatos.

### P4: ¿Cómo puedo obtener soporte técnico para Aspose.Page para .NET?

 R4: Para asistencia técnica, visite el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) o explorar el[documentación](https://reference.aspose.com/page/net/) para una orientación integral.

### P5: ¿Hay una prueba gratuita disponible para Aspose.Page para .NET?

 R5: Sí, puedes acceder a una prueba gratuita[aquí](https://releases.aspose.com/).