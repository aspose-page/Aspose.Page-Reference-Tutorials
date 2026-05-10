---
date: 2026-03-21
description: Aprenda cómo agregar texto Unicode a un documento XPS usando Aspose.Page
  para .NET. Esta guía le muestra cómo crear un documento XPS en C# y añadir texto
  con cadenas Unicode usando Aspose.Page.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Cómo agregar texto Unicode a un documento XPS con Aspose.Page
url: /es/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar texto Unicode a un documento XPS con Aspose.Page

## Introducción

Si necesitas **how to add unicode** caracteres en un archivo XPS, has llegado al lugar correcto. En este tutorial recorreremos los pasos exactos necesarios para **create XPS document C#**‑style usando Aspose.Page para .NET y demostraremos la capacidad de **aspose page add text** con una cadena Unicode. Al final tendrás un documento XPS totalmente funcional que muestra texto Unicode de derecha a izquierda (RTL) correctamente.

## Respuestas rápidas
- **¿Qué cubre el tutorial?** Agregar texto Unicode a un documento XPS con Aspose.Page para .NET.  
- **¿Qué lenguaje se usa?** C# (compatible con .NET Framework y .NET Core).  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Puedo cambiar la fuente o el tamaño?** Sí – el ejemplo usa Arial 20 pt, pero cualquier fuente instalada funciona.  
- **¿Se incluye soporte RTL?** Configurar `BidiLevel = 1` habilita la renderización de derecha a izquierda para cadenas Unicode.

## ¿Qué es “how to add unicode” en XPS?

Agregar texto Unicode significa insertar caracteres de cualquier idioma —árabe, hebreo, chino, etc.— en un documento XPS. La clase `XpsGlyphs` de Aspose.Page maneja la colocación de glifos a bajo nivel, mientras que la propiedad `BidiLevel` controla la dirección del texto para scripts RTL.

## ¿Por qué usar Aspose.Page para agregar texto?

- **Integración completa con .NET** – funciona con .NET Framework, .NET Core, .NET 5/6+.  
- **Sin dependencias externas** – código puro administrado, sin interop COM.  
- **Soporte tipográfico avanzado** – fuentes, estilos, colores y texto bidireccional.  
- **Alto rendimiento** – crea y guarda archivos XPS rápidamente, ideal para generación del lado del servidor.

## Requisitos previos

- Conocimientos básicos de C# y desarrollo .NET.  
- Visual Studio (cualquier versión reciente).  
- Biblioteca Aspose.Page para .NET – descárgala desde [here](https://releases.aspose.com/page/net/).

## Importar espacios de nombres

Primero, importa los espacios de nombres que te dan acceso al modelo XPS y a las utilidades de dibujo.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Paso 1: Configurar el documento – create XPS document C#

Crea un nuevo documento XPS que alojará el texto Unicode.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Paso 2: Agregar texto Unicode – aspose page add text

Ahora agregamos la cadena Unicode real. En este ejemplo usamos la fuente Arial, tamaño 20, y posicionamos el texto en (400 f, 200 f). El `BidiLevel` de 1 indica al renderizador que trate la cadena como de derecha a izquierda.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Paso 3: Guardar el documento

Finalmente, guarda el archivo XPS en disco.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

¡Felicidades! Has agregado correctamente texto **how to add unicode** a un documento XPS usando Aspose.Page para .NET.

## Problemas comunes y soluciones

| Problema | Razón | Solución |
|----------|-------|----------|
| El texto aparece distorsionado | La fuente no soporta el rango Unicode | Utiliza una fuente que contenga los glifos necesarios (p.ej., Arial Unicode MS). |
| El texto RTL sigue de izquierda a derecha | `BidiLevel` no está configurado o está en 0 | Asegúrate de que `glyphs.BidiLevel = 1;` para scripts RTL. |
| El archivo no se guarda | Ruta `dataDir` inválida | Verifica que el directorio exista y que la aplicación tenga permisos de escritura. |

## Preguntas frecuentes

**P: ¿Es Aspose.Page compatible con los últimos frameworks .NET?**  
R: Sí, Aspose.Page se actualiza regularmente para soportar .NET Framework, .NET Core y .NET 5/6+.

**P: ¿Puedo personalizar el estilo y tamaño de la fuente al agregar texto?**  
R: ¡Por supuesto! El método `AddGlyphs` te permite especificar cualquier familia de fuentes, tamaño y `FontStyle` que necesites.

**P: ¿Dónde puedo encontrar documentación adicional para Aspose.Page?**  
R: Puedes consultar la documentación [here](https://reference.aspose.com/page/net/) para obtener detalles completos de la API.

**P: ¿Hay recursos gratuitos para comenzar con Aspose.Page?**  
R: Sí, explora el foro de la comunidad en [Aspose.Page forum](https://forum.aspose.com/c/page/39) para obtener consejos, ejemplos y soporte de la comunidad.

**P: ¿Existe una versión de prueba disponible antes de comprar?**  
R: ¡Claro! Descarga la prueba gratuita desde [here](https://releases.aspose.com/) para evaluar la biblioteca.

**Última actualización:** 2026-03-21  
**Probado con:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}