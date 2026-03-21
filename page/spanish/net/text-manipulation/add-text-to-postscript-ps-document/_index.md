---
date: 2026-03-21
description: Aprende cómo rellenar texto y agregar texto a documentos PS usando Aspose.Page
  para .NET. Guía paso a paso con ejemplos de código.
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Cómo rellenar texto en documentos PostScript (PS) con Aspose.Page
url: /es/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo rellenar texto en documentos PostScript (PS) con Aspose.Page

## Introducción

Si necesitas **how to fill text** dentro de un archivo PostScript (PS), Aspose.Page para .NET lo hace sencillo. Ya sea que estés generando informes, facturas o gráficos personalizados, agregar y dar estilo al texto es un requisito esencial. En este tutorial recorreremos todo el proceso—desde configurar el entorno hasta guardar el documento PS final—para que puedas añadir texto a archivos PS con confianza en tus aplicaciones .NET.

## Respuestas rápidas
- **¿Qué significa “fill text”?** Renderiza los caracteres usando un pincel sólido, pintando los glifos directamente en la página.  
- **¿Puedo usar fuentes personalizadas?** Sí—Aspose.Page admite fuentes personalizadas mediante la función `add custom font ps`.  
- **¿Cómo guardo el documento PS?** Llama a `document.Save()` después de cerrar la página; esto escribe el archivo en disco (`save ps document`).  
- **¿Se admite “fill and stroke text”?** Absolutamente; usa `FillAndStrokeText` para aplicar tanto relleno como contorno.  
- **¿Qué versiones de .NET se requieren?** Cualquier .NET Framework 4.5+ o tiempo de ejecución .NET Core/5/6+.

## ¿Qué es “how to fill text” en un documento PS?

Rellenar texto significa pintar los caracteres con un color sólido (o pincel) sin contorno. En PostScript, esto es análogo al operador `fill`. Aspose.Page abstrae esto en métodos fáciles de usar como `FillText` y `FillAndStrokeText`.

## ¿Por qué usar Aspose.Page para agregar custom font ps?

- **Compatibilidad total con fuentes** – las fuentes del sistema y las fuentes externas TrueType/OpenType funcionan sin configuración adicional.  
- **Posicionamiento preciso** – controlas las coordenadas X/Y, el tamaño y el estilo.  
- **Estilizado avanzado** – combina rellenos, contornos y plumas para efectos como “fill and stroke text”.  
- **Multiplataforma** – funciona en Windows, Linux y macOS con la misma API.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

- **Aspose.Page para .NET** – descarga la biblioteca desde la [documentación de Aspose.Page .NET](https://reference.aspose.com/page/net/).  
- **Directorio de documentos** – una carpeta en tu máquina donde vivirán los archivos PS de origen y salida (referido como *Your Document Directory* en el código).  
- **Carpeta de fuentes** – una subcarpeta que contiene cualquier fuente personalizada que planees usar.

## Importar espacios de nombres

Primero, importa los espacios de nombres requeridos para que el compilador sepa dónde encontrar las clases que utilizaremos:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Guía paso a paso

### Paso 1: Crear flujo de salida para el documento PS  

Abrimos un `FileStream` que contendrá el archivo PS generado, configuramos `PsSaveOptions` para que apunte a nuestra carpeta de fuentes personalizadas y creamos una instancia de `PsDocument`.

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **Consejo:** Mantén el bloque `using` para asegurar que el flujo se cierre automáticamente, lo que también finaliza el archivo PS (`save ps document`).

### Paso 2: Rellenar texto con una fuente del sistema  

Aquí demostramos la operación básica de **how to fill text** usando la fuente incorporada *Times New Roman*.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### Paso 3: Rellenar texto con una fuente personalizada  

Si necesitas un aspecto específico, carga una fuente personalizada desde la carpeta de fuentes usando `ExternalFontCache.FetchDrFont`. Esto satisface el requisito **add custom font ps**.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### Paso 4: Contornear (stroke) texto con una fuente del sistema  

El contorno dibuja el contorno del glifo. Combínalo con un relleno para lograr un efecto “fill and stroke”.

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **Por qué esto importa:** La llamada `FillAndStrokeText` muestra cómo **fill and stroke text** en un solo paso, dándote un control tipográfico más rico.

### Paso 5: Contornear texto con una fuente personalizada  

La misma técnica de contorno funciona con cualquier fuente personalizada que hayas cargado.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### Paso 6: Cerrar la página y guardar el documento  

Finalizar es sencillo: cierra la página actual e invoca `Save()` para escribir el archivo PS en disco.

```csharp
document.ClosePage();
document.Save();
}
```

> **Resultado:** Encontrarás `AddText_outPS.ps` en *Your Document Directory*, que contiene texto rellenado y contorneado renderizado con fuentes del sistema y personalizadas.

## Problemas comunes y soluciones

| Problema | Solución |
|----------|----------|
| **Fuente personalizada no encontrada** | Verifica que el archivo de fuente (.ttf/.otf) exista en la carpeta referenciada por `AdditionalFontsFolders`. |
| **El texto aparece en la posición incorrecta** | Ajusta las coordenadas X/Y pasadas a `FillText`/`OutlineText`. Recuerda que PostScript usa puntos (1/72 de pulgada). |
| **Los colores se ven diferentes** | Asegúrate de estar usando `SolidBrush` o `Pen` con los valores correctos de `Color`. |
| **El documento no se guarda** | Confirma que el bloque `using` se complete sin excepciones y que la aplicación tenga permisos de escritura en la carpeta de destino. |

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Page con otras bibliotecas .NET?**  
R: Sí, Aspose.Page se integra sin problemas con otros componentes .NET, permitiéndote combinar bibliotecas de PDF, imagen o gráficos en la misma solución.

**P: ¿Son esenciales las fuentes personalizadas para este proceso?**  
R: Aunque las fuentes del sistema funcionan bien, las fuentes personalizadas te brindan total libertad de diseño y son útiles cuando se requiere tipografía específica de la marca.

**P: ¿Es Aspose.Page adecuado para el procesamiento de documentos a gran escala?**  
R: Absolutamente. La biblioteca está optimizada para escenarios de alto rendimiento y puede manejar miles de archivos PS de manera eficiente.

**P: ¿Puedo modificar la posición del texto en el documento PS?**  
R: Por supuesto—simplemente cambia los valores numéricos X/Y en las llamadas a `FillText` o `OutlineText`.

**P: ¿Dónde puedo buscar asistencia para consultas relacionadas con Aspose.Page?**  
R: Visita el [Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para conectar con la comunidad y obtener ayuda de expertos.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-03-21  
**Probado con:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose