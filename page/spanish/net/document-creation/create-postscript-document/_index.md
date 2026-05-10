---
date: 2026-01-12
description: Aprenda a crear documentos PostScript en .NET usando Aspose.Page. Esta
  guía paso a paso muestra cómo crear archivos PostScript, establecer el tamaño de
  página PostScript y personalizar los márgenes para una integración sin problemas.
linktitle: Create PostScript Document
second_title: Aspose.Page .NET API
title: Cómo crear un documento PostScript con Aspose.Page para .NET
url: /es/net/document-creation/create-postscript-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear documentos PostScript con Aspose.Page para .NET

## Introducción

¡Bienvenido! En este tutorial completo descubrirás **cómo crear documentos PostScript** de forma programática con Aspose.Page para .NET. Ya sea que estés generando facturas, etiquetas de envío o cualquier salida de impresión basada en vectores, esta guía te acompañará paso a paso, desde la configuración del entorno hasta el guardado del archivo *.ps* final. Vamos a sumergirnos y ver lo fácil que es producir un archivo PostScript de alta calidad con solo unas pocas líneas de C#.

## Respuestas rápidas
- **¿Qué biblioteca necesito?** Aspose.Page para .NET  
- **¿Puedo establecer el tamaño de página?** Sí – usa `options.PageSize` (ver “establecer tamaño de página PostScript”).  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **¿Cuánto tiempo lleva la implementación?** Normalmente menos de 10 minutos para un documento básico.

## ¿Qué es “cómo crear PostScript” en .NET?
Aspose.Page ofrece una API rica que abstrae la sintaxis de bajo nivel EPS/PostScript, permitiéndote centrarte en el diseño de página, gráficos y texto. Al usar la biblioteca evitas escribir código PS manualmente y obtienes soporte para fuentes, imágenes y mediciones precisas.

## ¿Por qué usar Aspose.Page para crear PostScript?
- **Control total** sobre dimensiones de página, márgenes y primitivas de dibujo.  
- **Sin dependencias externas** – todo se ejecuta dentro de tu proceso .NET.  
- **Compatibilidad multiplataforma** para Windows, Linux y macOS.  
- **Manejo robusto de fuentes**, incluidas carpetas de fuentes personalizadas.

## Requisitos previos

- Biblioteca Aspose.Page para .NET: Asegúrate de tener instalada la biblioteca Aspose.Page para .NET. Puedes descargarla [aquí](https://releases.aspose.com/page/net/).
- Entorno .NET: Verifica que tienes un entorno .NET funcionando en tu máquina.
- Editor de texto o IDE: Usa tu editor de texto o entorno de desarrollo integrado (IDE) preferido para codificar.

Ahora que tenemos todo listo, comencemos a construir el documento.

## Importar espacios de nombres

Primero, importa los espacios de nombres que te dan acceso a las clases principales de Aspose.Page.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.IO;
```

Estos espacios de nombres exponen `PsDocument`, `PsSaveOptions` y clases de utilidad usadas a lo largo del tutorial.

## Paso 1: Establecer el directorio del documento

```csharp
string dir = "Your Document Directory";
```

Reemplaza `"Your Document Directory"` con la ruta absoluta o relativa donde deseas que se guarde el archivo **PostScript** final.

## Paso 2: Crear el flujo de salida

```csharp
using (Stream outPsStream = new FileStream(dir + "document.ps", FileMode.Create))
```

El `FileStream` abre un flujo escribible llamado **document.ps**. Todos los comandos de dibujo posteriores se escribirán en este flujo.

## Paso 3: Crear opciones de guardado

```csharp
PsSaveOptions options = new PsSaveOptions();
```

`PsSaveOptions` te permite configurar cómo se renderiza y guarda el documento.

## Paso 4: Establecer el tamaño de página PostScript y los márgenes

```csharp
options.PageSize = PageConstants.GetSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT);
options.Margins = PageConstants.GetMargins(PageConstants.MARGINS_ZERO);
```

Aquí **establecemos el tamaño de página PostScript** a A4 vertical y eliminamos todos los márgenes. Puedes reemplazar `SIZE_A4` por otras constantes (p. ej., `SIZE_LETTER`) según los requisitos de tu diseño.

## Paso 5: Establecer carpetas de fuentes adicionales

```csharp
options.AdditionalFontsFolders = new string[] { dir };
```

Si tu documento usa fuentes personalizadas que no están instaladas en el sistema, indica a Aspose.Page la carpeta que contiene esos archivos de fuente.

## Paso 6: Crear documento multipágina

```csharp
bool multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

La instancia `PsDocument` representa el documento PostScript. Establecer `multiPaged` a `false` crea un documento de una sola página (puedes cambiar a `true` para salida multipágina).

## Paso 7: Cerrar y guardar

```csharp
document.ClosePage();
document.Save();
```

Llamar a `ClosePage()` finaliza el contenido de la página, y `Save()` escribe el flujo PostScript completo en disco.

¡Felicidades! Acabas de aprender **cómo crear documentos PostScript** con Aspose.Page para .NET.

## Problemas comunes y soluciones

- **Errores de ruta de archivo** – Asegúrate de que la variable `dir` termine con un separador de ruta (`\` o `/`) o usa `Path.Combine`.
- **Fuentes faltantes** – Si el texto aparece con fuentes predeterminadas, verifica que `options.AdditionalFontsFolders` apunte al directorio correcto.
- **Tamaño de página incorrecto** – Revisa los valores pasados a `PageConstants.GetSize`; también puedes proporcionar dimensiones personalizadas mediante `new SizeF(width, height)`.

## Preguntas frecuentes

### Q1: ¿Dónde puedo encontrar la documentación de Aspose.Page para .NET?
A1: La documentación está disponible [aquí](https://reference.aspose.com/page/net/).

### Q2: ¿Cómo descargo Aspose.Page para .NET?
A2: Puedes descargarlo desde [este enlace](https://releases.aspose.com/page/net/).

### Q3: ¿Dónde puedo comprar una licencia para Aspose.Page para .NET?
A3: Puedes adquirir una licencia [aquí](https://purchase.aspose.com/buy).

### Q4: ¿Hay una prueba gratuita disponible para Aspose.Page para .NET?
A4: Sí, puedes encontrar la prueba gratuita [aquí](https://releases.aspose.com/).

### Q5: ¿Cómo obtengo una licencia temporal para Aspose.Page para .NET?
A5: Obtén una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

### Q6: ¿Puedo generar archivos PostScript multipágina?
A6: Absolutamente. Establece `bool multiPaged = true` al crear `PsDocument` y llama a `document.NewPage()` para cada página adicional.

### Q7: ¿Aspose.Page admite gestión de color?
A7: Sí, puedes incrustar perfiles ICC mediante `PsSaveOptions.ColorProfile` si lo necesitas.

---

**Última actualización:** 2026-01-12  
**Probado con:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}