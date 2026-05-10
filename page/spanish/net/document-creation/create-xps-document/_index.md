---
date: 2026-01-12
description: 'Aprenda a crear documentos XPS con Aspose.Page para .NET: una guía paso
  a paso para generar documentos electrónicos de alta calidad.'
linktitle: Create XPS Document
second_title: Aspose.Page .NET API
title: Crear documento XPS con Aspose.Page para .NET
url: /es/net/document-creation/create-xps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear documento XPS con Aspose.Page para .NET

## Introducción

Bienvenido a nuestra guía paso a paso sobre **cómo crear un documento XPS** usando Aspose.Page para .NET. En este tutorial, exploraremos el proceso de generación de archivos XPS, un formato ampliamente utilizado para documentos electrónicos. Ya sea que seas un desarrollador experimentado o que recién estés comenzando con Aspose.Page, esta guía está diseñada para ayudarte a crear documentos XPS sin problemas con ejemplos claros y explicaciones detalladas.

## Respuestas rápidas
- **¿Qué biblioteca necesito?** Aspose.Page for .NET  
- **¿Puedo ejecutar esto en .NET Core?** Sí, la biblioteca soporta completamente .NET Core y .NET 5/6  
- **¿Cuántas líneas de código?** Menos de 20 líneas para producir un archivo XPS básico  
- **¿Necesito una licencia para pruebas?** Hay una versión de prueba gratuita disponible; se requiere una licencia para producción  
- **¿Qué formato tiene la salida?** XPS (XML Paper Specification)  

## Cómo crear un documento XPS usando Aspose.Page para .NET

A continuación encontrarás todo lo que necesitas antes de comenzar a programar, seguido de una guía concisa y numerada.

## Requisitos previos

Antes de sumergirnos en el tutorial, asegúrate de tener los siguientes requisitos previos:

1. Biblioteca Aspose.Page para .NET: Descarga e instala la biblioteca Aspose.Page desde el [enlace de descarga](https://releases.aspose.com/page/net/).

2. Tu directorio de documentos: Elige o crea un directorio en tu sistema donde quieras guardar los archivos XPS de salida.

¡Ahora, vamos al tutorial!

## Importar espacios de nombres

Para usar Aspose.Page para .NET, necesitas importar los espacios de nombres necesarios en tu proyecto. Sigue estos pasos:

### Paso 1: Añadir referencia a Aspose.Page

En tu proyecto, añade una referencia a la biblioteca Aspose.Page para .NET. Puedes encontrar el DLL necesario en el paquete descargado.

### Paso 2: Importar espacios de nombres

Include the following namespaces in your code file:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Ahora que hemos configurado los requisitos previos e importado los espacios de nombres necesarios, desglosaremos el proceso de creación de un documento XPS en varios pasos.

## Paso 1: Establecer el directorio del documento

```csharp
string dir = "Your Document Directory";
```

Asegúrate de reemplazar `"Your Document Directory"` con la ruta real donde deseas guardar el archivo XPS de salida.

## Paso 2: Crear documento XPS

```csharp
XpsDocument xDocs = new XpsDocument();
```

Inicializa un nuevo documento XPS usando la clase `XpsDocument`.

## Paso 3: Añadir glifos al documento

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

Utiliza el método `AddGlyphs` para añadir glifos (texto) al documento. Personaliza la fuente, el tamaño, el estilo y la posición según sea necesario.

## Paso 4: Establecer color de relleno de los glifos

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

Especifica el color de relleno para los glifos añadidos. En este ejemplo, usamos negro, pero puedes elegir cualquier color.

## Paso 5: Guardar el resultado

```csharp
xDocs.Save(dir + "output.xps");
```

Finalmente, guarda el documento XPS en el directorio especificado con el nombre de archivo deseado. El archivo XPS resultante contendrá el texto "Hello World!".

¡Felicidades! Has creado exitosamente un documento XPS usando Aspose.Page para .NET.

## Consejos comunes y trampas

- **Ruta del directorio** – Usa `Path.Combine(dir, "output.xps")` para evitar la falta de separadores de ruta en diferentes sistemas operativos.  
- **Disponibilidad de fuentes** – La fuente que especifiques debe estar instalada en la máquina donde se ejecuta el código; de lo contrario, Aspose sustituirá una fuente predeterminada.  
- **Múltiples páginas** – Para crear archivos XPS de varias páginas, instancia objetos `XpsPage` adicionales y agrega contenido a cada página antes de guardar.

## Conclusión

En este tutorial, recorrimos el proceso de creación de documentos XPS usando Aspose.Page para .NET. Esta poderosa biblioteca ofrece una forma fluida de generar documentos electrónicos con facilidad. Experimenta con diferentes fuentes, estilos y contenido para adaptar tus archivos XPS a tus necesidades específicas.

## Preguntas frecuentes

### P1: ¿Puedo usar fuentes personalizadas en mi documento XPS?

R1: Sí, puedes especificar la familia y el tamaño de la fuente al añadir glifos a tu documento XPS.

### P2: ¿Es Aspose.Page compatible con .NET Core?

R2: Sí, Aspose.Page soporta .NET Core, lo que te permite usarlo en aplicaciones multiplataforma.

### P3: ¿Cómo puedo añadir imágenes a un documento XPS?

R3: Aspose.Page proporciona métodos para añadir imágenes a tu documento XPS. Consulta la documentación para ejemplos detallados.

### P4: ¿Puedo crear documentos XPS de varias páginas?

R4: ¡Absolutamente! Puedes añadir múltiples páginas a un documento XPS usando la biblioteca Aspose.Page.

### P5: ¿Hay una versión de prueba disponible?

R5: Sí, puedes explorar las funciones de Aspose.Page descargando la [prueba gratuita](https://releases.aspose.com/).

---

**Última actualización:** 2026-01-12  
**Probado con:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}