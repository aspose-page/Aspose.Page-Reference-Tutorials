---
date: 2026-06-30
description: Aprenda cómo crear un documento postscript .NET y añadir rectángulos
  usando Aspose.Page para .NET. Guía paso a paso con ejemplos de código.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: Añadir rectángulo a PostScript (PS)
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Crear documento PostScript .NET – Añadir rectángulo Aspose.Page
url: /es/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar rectángulo a PostScript (PS) con Aspose.Page para .NET

## Introducción

Aspose.Page for .NET es una biblioteca que permite la creación y manipulación de archivos PostScript, EPS y XPS de forma programática. Si buscas **create postscript document .net**, este tutorial te guía a través de la adición de rectángulos a un documento PostScript usando Aspose.Page, brindándote una base sólida para la generación de gráficos más ricos.

## Respuestas rápidas
- **¿Qué biblioteca necesito?** Aspose.Page for .NET.  
- **¿Puedo crear un documento PostScript desde cero?** Sí – la API permite crear archivos PS programáticamente.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia para producción.  
- **¿Cuánto tiempo lleva la implementación?** Normalmente menos de 10 minutos para formas básicas.

## ¿Qué es crear un documento postscript .net?
Crear un documento PostScript en .NET significa generar programáticamente un archivo `.ps` que describe el contenido de la página—texto, gráficos o formas—usando la API de Aspose.Page. Este enfoque es ideal para la generación de gráficos del lado del servidor, la creación automatizada de informes, o cualquier escenario donde necesites un control preciso sobre el formato de salida.

## ¿Por qué usar Aspose.Page para .NET?
Aspose.Page admite **30+ primitivas gráficas** y puede generar archivos de hasta **500 MB** sin cargar todo el documento en memoria, ofreciendo renderizado de alto rendimiento en Windows, Linux y macOS. Te brinda control total sobre formas, colores y trazos, eliminando la necesidad de escribir código PostScript de bajo nivel.

- **Full control over graphics** – dibuja formas, establece colores y aplica trazos sin lidiar con la sintaxis de PS de bajo nivel.  
- **Cross‑platform** – funciona en entornos Windows, Linux y macOS.  
- **No external dependencies** – la biblioteca maneja toda la generación de PS internamente.  
- **Rich documentation & examples** – ponte en marcha rápidamente.

## Requisitos previos

- **Aspose.Page for .NET Library** – descarga e instala desde [aquí](https://releases.aspose.com/page/net/).  
- **Development Environment** – Visual Studio, VS Code, o cualquier IDE compatible con .NET.

## Importar espacios de nombres

El espacio de nombres `Aspose.Page` expone las clases principales que necesitarás, como `Document`, `Page`, `SolidBrush` y `Pen`. Impórtalo antes de comenzar a programar.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Ahora vamos a dividir el ejemplo en pasos claros y numerados.

## Paso 1: Configura tu directorio de documentos

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Reemplaza `"Your Document Directory"` con la carpeta donde deseas guardar el archivo PS resultante.

## Paso 2: Crear flujo de salida para el documento PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Este flujo apunta a **AddRectangle_outPS.ps**. Si lo deseas, puedes renombrar el archivo o cambiar la ubicación según sea necesario.

## Paso 3: Configurar opciones de guardado y crear el documento PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Aquí indicamos a Aspose.Page que use un tamaño de página A4 y cree un documento de una sola página.

## Paso 4: Añadir un rectángulo relleno

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Definimos un rectángulo en (250, 100) con ancho 150 y alto 100, establecemos un pincel naranja y rellenamos la forma.

## Paso 5: Añadir un rectángulo contorneado

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Se crea un segundo rectángulo más abajo en la página, esta vez con un trazo rojo de 3 puntos.

## Paso 6: Cerrar la página y guardar el documento

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Cerrar la página finaliza el dibujo, y `Save()` escribe el archivo PS en el disco.

## ¿Cómo crear un documento postscript .net?
`Document` es la clase principal que representa un archivo PostScript en Aspose.Page. `SaveOptions` especifica configuraciones como el tamaño de página y el formato de salida del documento. Carga el objeto `Document`, configura `SaveOptions` para una página A4, dibuja tus formas con `SolidBrush` o `Pen`, y luego llama a `document.Save()`—todo el flujo de trabajo requiere solo unas pocas líneas de código y se ejecuta en cualquier runtime .NET compatible. Este patrón te permite generar archivos PostScript totalmente compatibles sin tocar la sintaxis cruda de PS.

## Cómo generar un archivo postscript
Utiliza la clase `SaveOptions` de Aspose.Page para especificar el formato de salida como PostScript (`SaveFormat.PS`). La biblioteca envía el contenido directamente a un archivo o a un flujo de memoria, lo que te permite generar documentos grandes de manera eficiente sin un consumo excesivo de memoria.

## Problemas comunes y consejos

- **Incorrect file path** – Asegúrate de que `dataDir` termine con un separador de ruta (`\\` o `/`) o usa `Path.Combine`.  
- **Missing license** – En un entorno de producción, aplica tu licencia Aspose antes de crear el documento para evitar marcas de agua de evaluación.  
- **Color visibility** – Si el rectángulo aparece vacío, verifica que los colores del pincel o la pluma contrasten con el fondo de la página.

## Preguntas frecuentes

**Q:** ¿Puedo personalizar los colores de los rectángulos?  
**A:** Por supuesto. Cambia los valores `Color.Orange` o `Color.Red` en los constructores de `SolidBrush` y `Pen` a cualquier `System.Drawing.Color` que prefieras.

**Q:** ¿Es Aspose.Page compatible con otros formatos de documento?  
**A:** Sí. Además de PostScript, Aspose.Page también admite la generación de XPS y EPS.

**Q:** ¿Cómo puedo añadir texto al mismo documento?  
**A:** Usa la clase `TextFragment` para colocar texto en las coordenadas deseadas, luego llama a `document.Draw(textFragment)`.

**Q:** ¿Dónde puedo encontrar ejemplos adicionales y la referencia completa de la API?  
**A:** Explora la documentación [aquí](https://reference.aspose.com/page/net/) y únete a la comunidad en el [foro de Aspose.Page](https://forum.aspose.com/c/page/39).

**Q:** ¿Puedo probar Aspose.Page antes de comprar?  
**A:** Sí, descarga una prueba gratuita [aquí](https://releases.aspose.com/). Para una evaluación prolongada, considera una [licencia temporal](https://purchase.aspose.com/temporary-license/).

---

**Última actualización:** 2026-06-30  
**Probado con:** Aspose.Page 24.12 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Cómo crear un documento PostScript con Aspose.Page para .NET](/page/net/document-creation/create-postscript-document/)
- [Agregar imagen a documento PostScript (PS) con Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Agregar texto a documento PostScript (PS) con Aspose.Page](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}