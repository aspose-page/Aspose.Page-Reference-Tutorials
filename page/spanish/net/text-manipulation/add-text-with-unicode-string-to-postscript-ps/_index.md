---
date: 2026-03-21
description: Aprenda a crear documentos PostScript en C# con texto Unicode usando
  Aspose.Page para .NET, una forma rápida de mejorar la manipulación de documentos.
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
title: Crear documento PostScript en C# con texto Unicode – Aspose.Page
url: /es/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Añadir texto con cadena Unicode a PostScript (PS) con Aspose.Page

## Introducción

Si necesita **crear un documento PostScript C#** e incrustar caracteres Unicode, Aspose.Page para .NET hace que el proceso sea sencillo. En este tutorial recorreremos un ejemplo completo y práctico que le muestra cómo añadir texto japonés (o cualquier cadena Unicode) a un archivo PS, elegir una fuente personalizada y guardar el resultado. Al final, tendrá un fragmento reutilizable que podrá insertar en cualquier proyecto C#.

## Respuestas rápidas
- **¿Qué cubre este tutorial?** Añadir texto Unicode a un archivo PostScript usando Aspose.Page en C#.
- **¿Qué biblioteca se requiere?** Aspose.Page para .NET (última versión).
- **¿Necesito una fuente especial?** Cualquier fuente TrueType/OpenType que admita el rango Unicode deseado, por ejemplo, *Arial Unicode MS*.
- **¿Cuántas líneas de código?** Aproximadamente 30 líneas, divididas en pasos claros.
- **¿Se necesita una licencia?** Una licencia temporal funciona para evaluación; se requiere una licencia completa para producción.

## ¿Qué es “create postscript document c#”?
Crear un documento PostScript en C# significa generar programáticamente un archivo .ps que sigue las especificaciones del lenguaje PostScript. Aspose.Page abstrae los detalles de bajo nivel, permitiéndole centrarse en contenido como texto, gráficos y fuentes.

## ¿Por qué usar Aspose.Page para texto Unicode?
- **Compatibilidad total con Unicode** – renderiza caracteres de cualquier idioma sin codificación manual.
- **Independiente del dispositivo** – el mismo código funciona para salidas PS, EPS y PDF.
- **Sin dependencias externas** – la biblioteca gestiona la carga de fuentes y el mapeo de glifos internamente.

## Requisitos previos

- Familiaridad básica con C# y desarrollo .NET.
- Biblioteca Aspose.Page para .NET instalada. Puede descargarla desde la [documentación de Aspose.Page para .NET](https://reference.aspose.com/page/net/).
- Una carpeta que contenga las fuentes que planea usar (p. ej., *Arial Unicode MS*).

## Importar espacios de nombres

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Paso 1: Configurar el directorio del documento y la carpeta de fuentes

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## Paso 2: Crear el flujo de salida para el documento PostScript

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Additional options can be set here)
    
    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Further steps will be explained below)
    
    // Save the document
    document.Save();
}
```

## Paso 3: Añadir texto Unicode con fuente personalizada

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Paso 4: Cerrar la página actual

```csharp
document.ClosePage();
```

## Paso 5: Finalizar y guardar el documento

```csharp
document.Save();
```

## Problemas comunes y soluciones

- **Fuente no encontrada** – Asegúrese de que la ruta `AdditionalFontsFolders` apunte a la carpeta que contiene los archivos .ttf/.otf y que el nombre de la fuente coincida exactamente.
- **Caracteres basura** – Verifique que la cadena fuente esté codificada como UTF‑8 en su archivo fuente C# (use `#pragma warning disable 1591` si es necesario).
- **Archivo no creado** – Compruebe los permisos de escritura en `dataDir` y que el flujo se libere correctamente (el bloque `using` lo gestiona).

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Page para .NET con otros lenguajes de programación?**  
A: Aspose.Page está diseñado principalmente para .NET, pero existen equivalentes en Java disponibles.

**Q: ¿Cómo obtengo una licencia temporal para Aspose.Page para .NET?**  
A: Visite [Temporary License](https://purchase.aspose.com/temporary-license/) para obtener una licencia temporal.

**Q: ¿Existe un foro de la comunidad para discusiones sobre Aspose.Page?**  
A: Sí, visite el [Aspose.Page forum](https://forum.aspose.com/c/page/39) para obtener soporte de la comunidad.

**Q: ¿Con qué formatos puede trabajar Aspose.Page para .NET?**  
A: Aspose.Page admite varios formatos, incluidos XPS, PS, EPS, PDF y más.

**Q: ¿Puedo personalizar la apariencia del texto añadido?**  
A: Sí, puede personalizar la fuente, el tamaño, el color y otras propiedades del texto en Aspose.Page.

## Conclusión

En este tutorial demostramos cómo **crear un documento PostScript C#** e incrustar texto Unicode usando Aspose.Page. Siguiendo los pasos anteriores, podrá integrar rápidamente la renderización de texto multilingüe en cualquier aplicación .NET, dándole control total sobre la generación y el diseño del documento.

---

**Última actualización:** 2026-03-21  
**Probado con:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}