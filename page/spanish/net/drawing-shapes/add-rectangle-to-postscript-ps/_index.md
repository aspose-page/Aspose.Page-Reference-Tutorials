---
date: 2026-01-18
description: Aprende a crear documentos PostScript en .NET y añadir rectángulos usando
  Aspose.Page para .NET. Guía paso a paso con ejemplos de código.
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: Crear documento PostScript .NET – Añadir rectángulo con Aspose.Page
url: /es/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Añadir rectángulo a PostScript (PS) con Aspose.Page para .NET

## Introducción

Si buscas **crear documento postscript .net**, Aspose.Page ofrece una solución potente para manejar archivos PostScript. En este tutorial, te guiaremos paso a paso para añadir rectángulos a un documento PostScript usando Aspose.Page para .NET, dándote una base sólida para generar gráficos más complejos.

## Respuestas rápidas
- **¿Qué biblioteca necesito?** Aspose.Page para .NET.
- **¿Puedo crear un documento PostScript desde cero?** Sí, la API permite construir archivos PS programáticamente.
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita sirve para pruebas; se requiere una licencia para producción.
- **¿Cuánto tiempo lleva la implementación?** Normalmente menos de 10 minutos para formas básicas.

## ¿Qué es crear un documento postscript .net?
Crear un documento PostScript en .NET significa generar programáticamente un archivo .ps que describe el contenido de la página—texto, gráficos o formas—utilizando la API de Aspose.Page. Este enfoque es ideal para generación de gráficos del lado del servidor, creación automatizada de informes o cualquier escenario donde necesites un control preciso sobre el formato de salida.

## ¿Por qué usar Aspose.Page para .NET?
- **Control total sobre los gráficos** – dibuja formas, establece colores y aplica trazos sin lidiar con la sintaxis de bajo nivel de PS.
- **Multiplataforma** – funciona en entornos Windows, Linux y macOS.
- **Sin dependencias externas** – la biblioteca gestiona toda la generación de PS internamente.
- **Documentación y ejemplos abundantes** – ponte en marcha rápidamente.

## Requisitos previos

- **Biblioteca Aspose.Page para .NET** – descárgala e instálala desde [aquí](https://releases.aspose.com/page/net/).
- **Entorno de desarrollo** – Visual Studio, VS Code o cualquier IDE compatible con .NET.

## Importar espacios de nombres

Antes de comenzar a codificar, importa los espacios de nombres que exponen las clases necesarias:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Ahora dividamos el ejemplo en pasos claros y numerados.

## Paso 1: Configurar el directorio de tu documento

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Reemplaza `"Your Document Directory"` con la carpeta donde deseas que se guarde el archivo PS resultante.

## Paso 2: Crear el flujo de salida para el documento PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Este flujo apunta a **AddRectangle_outPS.ps**. Si lo deseas, puedes renombrar el archivo o cambiar la ubicación según necesites.

## Paso 3: Establecer opciones de guardado y crear el documento PS

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

## Paso 5: Añadir un rectángulo con contorno

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

Cerrar la página finaliza el dibujo, y `Save()` escribe el archivo PS en disco.

## Problemas comunes y consejos

- **Ruta de archivo incorrecta** – Asegúrate de que `dataDir` termine con un separador de ruta (`\\` o `/`) o usa `Path.Combine`.
- **Licencia faltante** – En un entorno de producción, aplica tu licencia de Aspose antes de crear el documento para evitar marcas de evaluación.
- **Visibilidad del color** – Si el rectángulo aparece vacío, verifica que los colores del pincel o la pluma contrasten con el fondo de la página.

## Preguntas frecuentes

**P:** ¿Puedo personalizar los colores de los rectángulos?  
**R:** Por supuesto. Cambia los valores `Color.Orange` o `Color.Red` en los constructores de `SolidBrush` y `Pen` por cualquier `System.Drawing.Color` que prefieras.

**P:** ¿Aspose.Page es compatible con otros formatos de documento?  
**R:** Sí. Además de PostScript, Aspose.Page también soporta generación de XPS y EPS.

**P:** ¿Cómo puedo añadir texto al mismo documento?  
**R:** Usa la clase `TextFragment` para colocar texto en las coordenadas deseadas, luego llama a `document.Draw(textFragment)`.

**P:** ¿Dónde puedo encontrar ejemplos adicionales y la referencia completa de la API?  
**R:** Explora la documentación [aquí](https://reference.aspose.com/page/net/) y únete a la comunidad en el [foro de Aspose.Page](https://forum.aspose.com/c/page/39).

**P:** ¿Puedo probar Aspose.Page antes de comprar?  
**R:** Sí, descarga una prueba gratuita [aquí](https://releases.aspose.com/). Para una evaluación prolongada, considera una [licencia temporal](https://purchase.aspose.com/temporary-license/).

---

**Última actualización:** 2026-01-18  
**Probado con:** Aspose.Page 24.12 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}