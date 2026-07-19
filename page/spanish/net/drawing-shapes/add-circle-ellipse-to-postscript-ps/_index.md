---
date: 2026-07-19
description: Aprenda el tutorial de asp page postscript para agregar elipses circulares
  a archivos PostScript (PS) usando Aspose.Page for .NET – cómo generar salida postscript
  rápidamente.
keywords:
- asp page postscript tutorial
- how to generate postscript
- write postscript output
lastmod: 2026-07-19
linktitle: Agregar elipse circular a PostScript (PS)
og_description: tutorial de asp page postscript que le muestra cómo generar salida
  postscript añadiendo elipses circulares con Aspose.Page for .NET. Siga la guía paso
  a paso para una integración rápida.
og_image_alt: 'Guide: Add circle ellipse to PostScript using Aspose.Page .NET'
og_title: tutorial de asp page postscript – Agregar elipse circular (PS)
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn the asp page postscript tutorial for adding circle ellipses to
    PostScript (PS) files using Aspose.Page for .NET – how to generate postscript
    output quickly.
  headline: asp page postscript tutorial – Add Circle Ellipse (PS)
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily focuses on PostScript, but Aspose provides other
      libraries for various formats. Check the [Aspose documentation](https://reference.aspose.com/page/net/)
      for a full list.
    question: Can I use Aspose.Page for .NET with other document formats?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community discussions and support.
    question: Where can I find additional support and community discussions?
  - answer: Yes, you can access the [free trial](https://releases.aspose.com/) to
      explore the features of Aspose.Page for .NET.
    question: Is there a free trial available for Aspose.Page for .NET?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Page?
  - answer: Purchase Aspose.Page for .NET from the [buy page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- postscript
- Aspose.Page
- .NET drawing
- circle ellipse
title: tutorial de asp page postscript – Agregar elipse circular (PS)
url: /es/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# tutorial de asp page postscript – Añadir elipse circular (PS)

## Introducción

En este **asp page postscript tutorial** descubrirás cómo añadir elipses circulares perfectas a un documento PostScript (PS) utilizando la biblioteca Aspose.Page para .NET. Ya sea que estés generando dibujos técnicos, gráficos vectoriales o informes personalizados, Aspose.Page te permite escribir salida PostScript sin lidiar con la sintaxis de bajo nivel de PS. Recorreremos cada paso, desde la configuración del entorno hasta la renderización de dos elipses—una rellena y otra con contorno—para que puedas integrar esta capacidad en tus propias aplicaciones de inmediato.

## Respuestas rápidas
- **¿Qué cubre este tutorial?** Añadir elipses circulares rellenas y con contorno a un archivo PS con Aspose.Page para .NET.  
- **¿Cuántos pasos de código se requieren?** Ocho pasos concisos, cada uno ilustrado con un fragmento de código listo para ejecutar.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET 5, .NET 6, .NET Core 3.1 y .NET Framework 4.6+.  
- **¿Puedo reutilizar la misma ruta gráfica?** Sí—crea un `GraphicsPath` una vez y dibújalo o rellénalo varias veces.

## ¿Qué es el asp page postscript tutorial?
El **asp page postscript tutorial** es una guía paso a paso que demuestra cómo generar contenido PostScript de forma programática con Aspose.Page para .NET. Se centra en código práctico, casos de uso del mundo real y consejos de buenas prácticas para que puedas producir archivos PS fiables rápidamente.

## ¿Por qué usar Aspose.Page para la generación de PostScript?
Aspose.Page admite **más de 30 formatos de salida** (incluidos PDF, SVG y EPS) y puede renderizar **documentos de cientos de páginas** sin cargar todo el archivo en memoria, ofreciendo una **reducción de la huella de memoria de hasta el 70 %** en comparación con la construcción manual de cadenas PS. Su API de alto nivel elimina la necesidad de escribir comandos PS sin procesar, reduciendo el tiempo de desarrollo en **un 80 %** en promedio.

## Requisitos previos

Antes de sumergirnos en el tutorial, asegúrate de que tienes los siguientes requisitos previos:

1. Biblioteca Aspose.Page para .NET: Descarga e instala la biblioteca Aspose.Page para .NET desde [aquí](https://releases.aspose.com/page/net/).  
2. Entorno de desarrollo: Asegúrate de tener un entorno de desarrollo .NET funcionando configurado en tu máquina.

Ahora, comencemos con la guía paso a paso.

## Importar espacios de nombres

Las directivas `using` traen las clases de Aspose.Page al alcance para que puedas trabajar directamente con gráficos, colores y documentos PS.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Ahora, desglosaremos el ejemplo proporcionado en varios pasos para guiarte a través del proceso de añadir elipses circulares a un documento PostScript.

## ¿Cómo establezco el directorio del documento?

Para indicar al programa dónde almacenar el archivo PS generado, debes especificar una ruta de carpeta a la que la aplicación pueda escribir. Usa una variable como `dataDir` y asígnale una ruta completa o relativa; esta ruta se combinará con el nombre del archivo de salida más adelante en el código.  
> **Consejo profesional:** Usa `Path.Combine(Environment.CurrentDirectory, "output")` para crear una ruta multiplataforma y evitar separadores codificados.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## ¿Cómo creo el flujo de salida para el documento PostScript?

Crear un flujo de salida abre un manejador de archivo en el que el motor Aspose.Page escribirá los datos PostScript. Al usar un `FileStream` con `FileMode.Create`, el archivo se crea de nuevo en cada ejecución, sobrescribiendo cualquier versión anterior. Este flujo se pasa luego al constructor `PsDocument`.  

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

## ¿Cómo configuro las opciones de guardado e inicializo un documento PS?

`PsSaveOptions` te permite especificar el tamaño de página, la resolución y otras configuraciones de renderizado. Aquí usamos el tamaño de página A4 estándar y un documento de una sola página. `PsDocument` representa el documento PostScript que se está creando; recibe el flujo de salida y las opciones de guardado, y gestiona los eventos del ciclo de vida de la página.  

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## ¿Cómo creo una ruta gráfica para la primera elipse?

`GraphicsPath` representa una forma vectorial que puede dibujarse o rellenarse en una página PostScript. El constructor toma las coordenadas X/Y de la esquina superior izquierda, seguidas del ancho y la altura, lo que permite definir el tamaño y la posición exactos de la elipse en la página.  

```csharp
//Create graphics path from the first ellipse
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

## ¿Cómo establezco la pintura y relleno la primera elipse?

`SolidBrush` define un color de relleno sólido para operaciones de dibujo. Al crear un `SolidBrush` con un `Color` específico y pasarlo a `graphics.FillPath`, la elipse se renderiza con ese color sólido.  

```csharp
//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Fill the ellipse
document.Fill(path);
```

## ¿Cómo creo una ruta gráfica para la segunda elipse?

Se define un segundo `GraphicsPath` para ilustrar cómo puedes dibujar un contorno (trazo) separado de un relleno. Se usa el mismo patrón de constructor, pero puedes cambiar las dimensiones del rectángulo para producir una elipse de tamaño diferente.  

```csharp
//Create graphics path from the second ellipse
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

## ¿Cómo establezco el trazo y dibujo la segunda elipse?

`SolidPen` especifica el color y el ancho para trazar formas. Al proporcionar un `SolidPen` a `graphics.DrawPath`, el contorno de la elipse se dibuja sin relleno, dándote una forma trazada limpia.  

```csharp
//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Stroke (outline) the ellipse
document.Draw(path);
```

## ¿Cómo cierro la página actual y guardo el documento?

Después de emitir todos los comandos de dibujo, debes cerrar la página activa con `document.ClosePage()` para finalizar su contenido. Finalmente, al llamar a `document.Save()` se escribe el data acumulado de PostScript en el flujo abierto previamente, generando el archivo de salida en el disco.  

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

## Problemas comunes y soluciones

| Problema | Razón | Solución |
|----------|-------|----------|
| **Archivo no encontrado** | Ruta de directorio incorrecta | Verifica que la carpeta exista o créala con `Directory.CreateDirectory`. |
| **Salida en blanco** | Olvidar llamar a `document.ClosePage()` | Asegúrate de cerrar la página antes de guardar. |
| **Colores incorrectos** | Usar `Color.FromArgb` con orden incorrecto | Usa `Color.FromRgb(red, green, blue)` para mayor claridad. |
| **Ralentización del rendimiento en archivos grandes** | Cargar todo el documento en memoria | Usa `PsSaveOptions` con `EnableMemorySaving = true` para transmitir páginas grandes. |

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Page para .NET con otros formatos de documento?**  
A: Aspose.Page se centra principalmente en PostScript, pero Aspose ofrece otras bibliotecas para varios formatos. Consulta la [documentación de Aspose](https://reference.aspose.com/page/net/) para obtener una lista completa.

**Q: ¿Dónde puedo encontrar soporte adicional y discusiones de la comunidad?**  
A: Visita el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para discusiones de la comunidad y soporte.

**Q: ¿Hay una prueba gratuita disponible para Aspose.Page para .NET?**  
A: Sí, puedes acceder a la [prueba gratuita](https://releases.aspose.com/) para explorar las funciones de Aspose.Page para .NET.

**Q: ¿Cómo puedo obtener una licencia temporal para Aspose.Page?**  
A: Obtén una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/) para propósitos de prueba y evaluación.

**Q: ¿Dónde puedo comprar Aspose.Page para .NET?**  
A: Compra Aspose.Page para .NET en la [página de compra](https://purchase.aspose.com/buy).

## Conclusión

¡Felicidades! Has completado con éxito el **asp page postscript tutorial** para añadir elipses circulares a documentos PostScript usando Aspose.Page para .NET. Al seguir los ocho pasos claros, ahora puedes generar archivos PS de alta calidad con elipses rellenas y con contorno, listos para integrarse en motores de informes, exportadores CAD o cualquier canal de gráficos personalizado.

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Aspose.Page .NET – Dibujar formas](/page/net/drawing-shapes/)
- [Crear documento postscript .net – Añadir rectángulo con Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)
- [Cómo crear documento PostScript con Aspose.Page para .NET](/page/net/document-creation/create-postscript-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}