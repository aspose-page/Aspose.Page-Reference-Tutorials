---
title: Agregue texto con cadena Unicode al documento XPS con Aspose.Page
linktitle: Agregar texto con cadena Unicode al documento XPS
second_title: Aspose.Página .NET API
description: Explore el poder de Aspose.Page para .NET con nuestra guía paso a paso sobre cómo agregar texto Unicode a documentos XPS.
type: docs
weight: 12
url: /es/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---
## Introducción

En el panorama en constante evolución del desarrollo de .NET, Aspose.Page se destaca como una poderosa herramienta para manejar documentos XPS. Entre sus muchas características, la capacidad de agregar texto con cadenas Unicode a un documento XPS es una funcionalidad valiosa. Esta guía paso a paso lo guiará a través del proceso, asegurando que aproveche esta capacidad de manera efectiva.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

- Una comprensión básica del desarrollo .NET.
- Visual Studio instalado en su máquina.
-  Aspose.Page para la biblioteca .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/page/net/).

## Importar espacios de nombres

Para comenzar, asegúrese de importar los espacios de nombres necesarios a su proyecto. Esto proporcionará las clases y funcionalidades necesarias para trabajar con Aspose.Page. Estos son los espacios de nombres esenciales:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Paso 1: configurar el documento

En primer lugar, cree un nuevo documento XPS donde agregará el texto Unicode. Siga el fragmento de código a continuación:

```csharp
// La ruta al directorio de documentos.
string dataDir = "Your Document Directory";
// Crear nuevo documento XPS
XpsDocument doc = new XpsDocument();
```

## Paso 2: agregue texto Unicode

Ahora, agreguemos texto Unicode al documento XPS. Este ejemplo utiliza la fuente Arial, establece el tamaño de fuente en 20 y coloca el texto en las coordenadas (400f, 200f). La cadena Unicode en este caso es "TEN.rof SPX.esopsA". Consulte el fragmento de código a continuación:

```csharp
// Añadir texto
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Paso 3: guarde el documento

Una vez agregado el texto Unicode, guarde el documento XPS resultante. Aquí está el paso final:

```csharp
// Guarde el documento XPS resultante
doc.Save(dataDir + "AddTextRTL_out.xps");
```

¡Felicidades! Ha agregado con éxito texto Unicode a un documento XPS usando Aspose.Page para .NET.

## Conclusión

En este tutorial, exploramos el proceso de agregar texto Unicode a documentos XPS usando Aspose.Page para .NET. Esta funcionalidad abre puertas a la creación de documentos diversos y dinámicos dentro del entorno .NET.

## Preguntas frecuentes

### P1: ¿Aspose.Page es compatible con los últimos frameworks .NET?

R1: Sí, Aspose.Page se actualiza periódicamente para garantizar la compatibilidad con los últimos marcos .NET.

### P2: ¿Puedo personalizar el estilo y el tamaño de fuente al agregar texto?

R2: ¡Absolutamente! El código de ejemplo proporcionado le permite personalizar fácilmente el estilo, el tamaño y otros atributos de la fuente.

### P3: ¿Dónde puedo encontrar documentación adicional para Aspose.Page?

 A3: Puede consultar la documentación.[aquí](https://reference.aspose.com/page/net/) para obtener información completa y ejemplos.

### P4: ¿Existen recursos gratuitos para comenzar con Aspose.Page?

 R4: Sí, puedes explorar el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para apoyo y debates de la comunidad.

### P5: ¿Existe una versión de prueba disponible antes de realizar la compra?

 R5: ¡Por supuesto! Puedes acceder a la versión de prueba gratuita[aquí](https://releases.aspose.com/) antes de realizar una compra.