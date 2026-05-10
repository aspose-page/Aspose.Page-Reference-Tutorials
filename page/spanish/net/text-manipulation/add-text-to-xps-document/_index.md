---
date: 2026-03-21
description: Aprenda a crear documentos XPS en .NET y a agregar texto usando Aspose.Page
  para .NET. Guía paso a paso para desarrolladores .NET.
linktitle: Add Text to XPS Document
second_title: Aspose.Page .NET API
title: Crear documento XPS .NET y añadir texto con Aspose.Page
url: /es/net/text-manipulation/add-text-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear documento XPS .NET y agregar texto con Aspose.Page

En el desarrollo moderno de .NET, la capacidad de **crear documento XPS .NET** archivos programáticamente es una habilidad valiosa, especialmente cuando necesitas generar informes imprimibles, facturas o gráficos personalizados. Este tutorial te guía a través del uso de Aspose.Page para **aspose.page add text** a un documento XPS, dándote control total sobre el diseño y el estilo, todo desde tu aplicación .NET.

## Respuestas rápidas
- **¿Qué cubre este tutorial?** Agregar texto a un documento XPS recién creado usando Aspose.Page para .NET.  
- **¿Cuánto tiempo lleva?** Aproximadamente 5‑10 minutos para una implementación básica.  
- **¿Cuáles son los requisitos previos?** Entorno de desarrollo .NET y la biblioteca Aspose.Page.  
- **¿Se requiere una licencia?** Sí, se necesita una licencia válida de Aspose.Page para uso en producción.  
- **¿Puede ejecutarse en .NET Core / .NET 6+?** Absolutamente – Aspose.Page soporta todas las versiones recientes de .NET.

## ¿Qué es crear documento XPS .NET?

Crear un documento XPS en .NET significa generar un archivo de diseño fijo que preserva la apariencia exacta de tu contenido en dispositivos e impresoras. XPS (XML Paper Specification) es el estándar abierto de Microsoft para la descripción de páginas, similar a PDF pero totalmente basado en XML.

## ¿Por qué usar Aspose.Page para agregar texto?

Aspose.Page ofrece una API de alto nivel y orientada a objetos que abstrae el marcado XPS de bajo nivel. Puedes agregar texto, gráficos y formas sin lidiar con XML sin procesar, lo que hace que el proceso de desarrollo sea más rápido y menos propenso a errores.

## Requisitos previos

- Aspose.Page para .NET: Asegúrate de tener la biblioteca Aspose.Page instalada. Puedes descargarla desde la [documentación de Aspose.Page para .NET](https://reference.aspose.com/page/net/).
- Entorno de desarrollo: Configura tu entorno de desarrollo .NET. Si aún no lo has hecho, sigue las instrucciones de instalación proporcionadas en la [documentación](https://reference.aspose.com/page/net/).
- Directorio de documentos: Crea un directorio donde almacenarás tus documentos. Reemplaza "Your Document Directory" en el fragmento de código proporcionado con la ruta real.

Ahora que hemos cubierto los conceptos básicos, sumergámonos en el código.

## Importar espacios de nombres

Primero, importa los espacios de nombres necesarios para iniciar el proyecto:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Paso 1: Crear documento XPS .NET

Crea un nuevo documento XPS que servirá como lienzo para nuestro texto.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## Paso 2: Crear un pincel para el texto

Define un pincel de color sólido que determina el color del texto. Aquí usamos negro.

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## Paso 3: Agregar glifos (aspose.page add text)

Los glifos son la representación de bajo nivel de los caracteres en un documento XPS. Esta llamada agrega el texto “Hello World!” en las coordenadas especificadas.

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## Paso 4: Guardar el documento XPS resultante

Persistir el documento en disco para que puedas verlo o imprimirlo más tarde.

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

Al seguir estos pasos, has creado con éxito **crear documento XPS .NET** y agregado texto personalizado usando Aspose.Page.

## Problemas comunes y soluciones

| Problema | Razón | Solución |
|----------|-------|----------|
| **Archivo no encontrado** al guardar | `dataDir` apunta a una carpeta inexistente | Asegúrate de que el directorio exista o usa `Directory.CreateDirectory(dataDir)` antes de guardar. |
| **Texto no visible** | El color del pincel coincide con el fondo | Cambia `Color.Black` a otro color contrastante. |
| **Fuente no compatible** | La fuente no está instalada en la máquina | Usa una fuente que se garantice que está presente, o incrusta la fuente usando las funciones de incrustación de fuentes de Aspose.Page. |

## Preguntas frecuentes

### Q1: ¿Puedo personalizar la fuente y el tamaño del texto agregado?

A1: Sí, tienes control total sobre la fuente y el tamaño. Ajusta los parámetros en el método `AddGlyphs` según corresponda.

### Q2: ¿Aspose.Page es compatible con .NET Core?

A2: ¡Absolutamente! Aspose.Page soporta .NET Core, garantizando compatibilidad con las últimas tecnologías .NET.

### Q3: ¿Existen requisitos de licencia para usar Aspose.Page?

A3: Sí, necesitas una licencia válida. Explora las opciones de licencia [aquí](https://purchase.aspose.com/buy).

### Q4: ¿Cómo puedo obtener soporte o ayuda?

A4: Visita el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para conectar con la comunidad y obtener asistencia.

### Q5: ¿Hay una prueba gratuita disponible?

A5: ¡Claro! Puedes obtener una prueba gratuita [aquí](https://releases.aspose.com/).

**Preguntas y respuestas adicionales**

**Q: ¿Puedo agregar varios bloques de texto en la misma página?**  
A: Sí, simplemente llama a `doc.AddGlyphs` varias veces con diferentes coordenadas.

**Q: ¿Aspose.Page permite rotar el texto?**  
A: Puedes aplicar una matriz de transformación al objeto `XpsGlyphs` para rotar o inclinar el texto.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Última actualización:** 2026-03-21  
**Probado con:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

---