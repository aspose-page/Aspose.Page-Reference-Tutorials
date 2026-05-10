---
date: 2026-01-12
description: Aprenda cómo guardar un archivo PostScript y crear un documento PostScript
  usando Aspose.Page para .NET, y aplicar múltiples transformaciones para gráficos
  dinámicos.
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: Guardar archivo PostScript con transformaciones de Aspose.Page (.NET)
url: /es/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Guardar archivo PostScript con transformaciones de Aspose.Page (.NET)

## Introducción

En este tutorial descubrirás cómo **guardar un archivo PostScript** mientras trabajas con Aspose.Page para .NET. Recorreremos la creación de un documento PostScript, la aplicación de múltiples transformaciones como traslación, escalado, rotación y cizallado, y finalmente guardaremos el resultado. Al final estarás cómodo creando gráficos dinámicos programáticamente y sabrás exactamente dónde colocar cada transformación en el estado gráfico.

## Respuestas rápidas
- **¿Qué puedo crear?** Un documento PostScript con todas las funciones y gráficos transformados.  
- **¿Qué biblioteca se requiere?** Aspose.Page para .NET (descargable desde el sitio oficial).  
- **¿Cómo guardo el archivo?** Usa `PsDocument.Save()` después de configurar los estados gráficos.  
- **¿Puedo aplicar múltiples transformaciones?** Sí – combínalas con `Transform` o llamadas secuenciales.  
- **¿Se necesita una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.

## ¿Qué es una operación de “guardar archivo postscript”?

Guardar un archivo PostScript significa persistir los comandos de dibujo que has creado en memoria a un archivo `.ps` en disco. El archivo puede entonces ser renderizado por cualquier intérprete PostScript, impresora o visor.

## ¿Por qué usar Aspose.Page para .NET para crear documentos postscript?

Aspose.Page proporciona una API de alto nivel e independiente del dispositivo que abstrae la sintaxis de bajo nivel de PostScript. Obtienes:

- Objetos C# fuertemente tipados para rutas, pinceles y transformaciones.  
- Manejo automático de la pila de estado gráfico (save/restore).  
- Soporte completo para matrices de transformación complejas sin cálculos manuales.  

## Requisitos previos

Antes de comenzar, asegúrate de tener:

- **Aspose.Page para .NET** biblioteca integrada en tu proyecto. Obténla desde el [enlace de descarga](https://releases.aspose.com/page/net/).  
- Una carpeta con permisos de escritura donde se almacenará el archivo `.ps` generado. Reemplaza la ruta de marcador de posición en el código con tu directorio real.

## Importar espacios de nombres

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Ahora exploremos cada paso de transformación uno por uno.

## Sin transformaciones

### Paso 1: Crear flujo de salida

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Este fragmento crea un **documento PostScript** con un solo rectángulo naranja y **guarda el archivo PostScript** sin aplicar ninguna transformación.

## Traslación

### Paso 1: Guardar estado gráfico

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Guardar el estado gráfico te permite volver atrás después de mover objetos.

### Paso 2: Trasladar estado gráfico

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

La traslación mueve todo lo dibujado después de esta llamada 250 unidades a la derecha.

### Paso 3: Rellenar rectángulo con transformación de traslación

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Ahora un rectángulo azul aparece 250 puntos a la derecha del naranja.

### Paso 4: Restaurar estado gráfico

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

Restaurar devuelve el sistema de coordenadas a su posición original, de modo que el dibujo posterior no se vea afectado por la traslación.

## Escalado

> *Puedes seguir el mismo patrón—guardar estado, aplicar `Scale`, dibujar y luego restaurar.*  
> **Consejo profesional:** Usa escalado no uniforme (`Scale(sx, sy)`) para estirar objetos solo en una dirección.

## Rotación

> *Rota alrededor del origen o de un punto pivote personalizado usando `Rotate(angle)`.*
> **Consejo profesional:** Combina `Translate` antes de la rotación para rotar alrededor de un punto específico.

## Cizallado

> *Las transformaciones de cizallado (`Shear(shx, shy)`) inclinan formas, útiles para efectos cursivos.*  

## Transformaciones complejas

> *Para escenarios avanzados, crea una `Matrix` personalizada y pásala a `Transform(matrix)`.*
> Aquí es donde **aplicas múltiples transformaciones** en un solo paso.

## Conclusión

Has aprendido cómo **guardar un archivo PostScript**, **crear un documento PostScript** y **aplicar múltiples transformaciones** usando Aspose.Page para .NET. Experimenta con diferentes órdenes de transformación, combínalas y observa cómo evolucionan los gráficos.

## Preguntas frecuentes

**P: ¿Cómo puedo aplicar múltiples transformaciones a un solo objeto?**  
R: Usa el método `Transform` con una `Matrix` personalizada que combine traslación, escalado, rotación o cizallado en el orden que necesites.

**P: ¿Puedo previsualizar las transformaciones antes de guardar el documento?**  
R: Sí—renderiza el `PsDocument` a una imagen o usa un visor PostScript para inspeccionar la salida antes de llamar a `Save()`.

**P: ¿Es posible aplicar transformaciones a elementos específicos en un documento?**  
R: Absolutamente. Guarda el estado gráfico antes de dibujar el elemento, aplica la transformación deseada, dibuja y luego restaura el estado.

**P: ¿Hay consideraciones de rendimiento al trabajar con transformaciones complejas?**  
R: Las matrices complejas aumentan el trabajo de la CPU. Mantén las transformaciones lo más simples posible y reutiliza los estados guardados al dibujar muchos objetos similares.

**P: ¿Cómo puedo obtener soporte o asistencia para consultas relacionadas con Aspose.Page?**  
R: Visita el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para ayuda de la comunidad, o contacta directamente al soporte de Aspose.

**Última actualización:** 2026-01-12  
**Probado con:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}