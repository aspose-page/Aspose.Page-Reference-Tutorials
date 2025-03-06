---
title: Agregue texto a un documento XPS con Aspose.Page para .NET
linktitle: Agregar texto al documento XPS
second_title: Aspose.Página .NET API
description: Explore una guía paso a paso sobre cómo agregar texto a documentos XPS usando Aspose.Page para .NET. Mejore sus proyectos .NET sin esfuerzo.
weight: 13
url: /es/net/text-manipulation/add-text-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregue texto a un documento XPS con Aspose.Page para .NET

## Introducción

En el dinámico mundo del desarrollo .NET, Aspose.Page se destaca como una poderosa herramienta para trabajar con documentos XPS. Agregar texto a documentos XPS es un requisito común y Aspose.Page simplifica este proceso. En este tutorial, exploraremos cómo usar Aspose.Page para .NET para agregar texto sin problemas a documentos XPS.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

- Aspose.Page para .NET: asegúrese de tener instalada la biblioteca Aspose.Page. Puedes descargarlo desde el[Aspose.Page para la documentación de .NET](https://reference.aspose.com/page/net/).

-  Entorno de desarrollo: configure su entorno de desarrollo .NET. Si aún no lo ha hecho, siga las instrucciones de instalación proporcionadas en el[documentación](https://reference.aspose.com/page/net/).

- Directorio de documentos: cree un directorio donde almacenará sus documentos. Reemplace "Su directorio de documentos" en el fragmento de código proporcionado con la ruta real.

Ahora, pasemos a la guía paso a paso.

## Importar espacios de nombres

En primer lugar, importemos los espacios de nombres necesarios para iniciar nuestro proyecto:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Paso 1: cree un nuevo documento XPS

Para comenzar a trabajar con Aspose.Page, cree un nuevo documento XPS. Este será el lienzo donde agregaremos nuestro texto.

```csharp
// ExInicio:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// Fin final: 3
```

## Paso 2: crea un pincel para texto

Ahora, creemos un pincel para definir el color del texto. En este ejemplo, usamos un pincel de color negro.

```csharp
// ExInicio:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// Fin final: 4
```

## Paso 3: agregue glifos al documento

Los glifos representan el texto en documentos XPS. Agregue glifos al documento con la fuente, tamaño, estilo y posición deseados.

```csharp
// ExInicio:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// Fin final: 5
```

## Paso 4: guarde el documento XPS resultante

Finalmente, guarde el documento XPS con el texto agregado en su directorio especificado.

```csharp
// ExInicio:6
doc.Save(dataDir + "AddText_out.xps");
// Fin final: 6
```

Si sigue estos sencillos pasos, habrá agregado texto con éxito a un documento XPS utilizando Aspose.Page para .NET.

## Conclusión

En conclusión, Aspose.Page para .NET proporciona una solución sencilla para agregar texto a documentos XPS en sus proyectos .NET. La simplicidad de la biblioteca, combinada con sus sólidas funciones, la convierte en una herramienta invaluable para la manipulación de documentos.

## Preguntas frecuentes

### P1: ¿Puedo personalizar la fuente y el tamaño del texto agregado?

 R1: Sí, tienes control total sobre la fuente y el tamaño. Ajuste los parámetros en el`AddGlyphs` método en consecuencia.

### P2: ¿Aspose.Page es compatible con .NET Core?

R2: ¡Absolutamente! Aspose.Page es compatible con .NET Core, lo que garantiza la compatibilidad con las últimas tecnologías .NET.

### P3: ¿Existe algún requisito de licencia para utilizar Aspose.Page?

 R3: Sí, necesita una licencia válida. Explorar opciones de licencia[aquí](https://purchase.aspose.com/buy).

### P4: ¿Cómo puedo obtener apoyo o buscar ayuda?

 A4: Visita el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para conectarse con la comunidad y obtener ayuda.

### P5: ¿Hay una prueba gratuita disponible?

 R5: ¡Por supuesto! Puedes obtener una prueba gratuita[aquí](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
