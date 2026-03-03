---
date: 2026-03-03
description: Aprenda cómo establecer un tamaño de página personalizado y agregar una
  segunda página PS a un documento PostScript usando Aspose.Page para .NET.
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Establecer tamaño de página personalizado en documento PS con Aspose.Page
url: /es/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar página a documento PostScript (PS) con Aspose.Page

## Introducción

## Respuestas rápidas
- **¿Puedo establecer un tamaño de página personalizado?** Sí – simplemente pase el ancho y la altura al abrir una página.  
- **¿Cómo agrego una segunda página PS?** Llame a `document.OpenPage(width, height)` una segunda vez.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **¿Necesito una licencia?** Una licencia temporal funciona para pruebas; se requiere una licencia completa para producción.  
- **¿Dónde puedo descargar Aspose.Page?** Desde la página oficial de descarga enlazada a continuación.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de que tiene los siguientes requisitos previos listados:

- Conocimientos prácticos de desarrollo .NET.  
- Visual Studio instalado en su máquina.  
- Biblioteca Aspose.Page para .NET, que puede descargar [aquí](https://releases.aspose.com/page/net/).  
- Su directorio de documentos preferido para pruebas.

## Importar espacios de nombres

Asegúrese de incluir los espacios de nombres necesarios en su proyecto para acceder a las funcionalidades proporcionadas por Aspose.Page. En el ejemplo dado, los espacios de nombres se incluyen implícitamente, pero es esencial verificar y hacer ajustes según la estructura de su proyecto.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Paso 1: Configurar su proyecto

Cree un nuevo proyecto .NET en Visual Studio y configure las configuraciones necesarias. Asegúrese de referenciar la biblioteca Aspose.Page en su proyecto.

## Establecer tamaño de página personalizado y agregar segunda página PS

Esta sección muestra exactamente cómo **establecer un tamaño de página personalizado** para cada página y cómo **agregar una segunda página ps** al mismo documento.

### Paso 2: Inicializar el documento

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### Paso 3: Agregar la primera página (tamaño predeterminado)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### Paso 4: Agregar la segunda página con un tamaño (personalizado) diferente

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### Paso 5: Guardar el documento

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

Siga estos pasos meticulosamente, y logrará **establecer un tamaño de página personalizado** y agregar una **segunda página PS** a un documento PostScript usando Aspose.Page para .NET.

## Por qué es importante

- **Diseño preciso** – Las dimensiones de página personalizadas le permiten coincidir con las especificaciones de la impresora o crear formatos de folleto únicos.  
- **Múltiples páginas** – Agregar una segunda página (o más) permite informes multipágina sin herramientas externas de combinación.  
- **Multiplataforma** – El archivo PS generado puede renderizarse en cualquier dispositivo compatible con PostScript o convertirse a PDF posteriormente.

## Problemas comunes y solución de problemas

- **Ruta incorrecta** – Asegúrese de que `dataDir` termine con un separador de ruta o use `Path.Combine`.  
- **Problemas de licencia** – Sin una licencia válida, la biblioteca puede añadir una marca de agua o limitar la cantidad de páginas.  
- **Confusión de unidades** – El ancho y la altura se miden en puntos (1 punto = 1/72 de pulgada). Ajuste según corresponda.

## Preguntas frecuentes

**P1: ¿Es Aspose.Page compatible con diferentes formatos de documento?**  
R1: Aspose.Page se centra principalmente en la manipulación de documentos PostScript. Para otros formatos, puede explorar bibliotecas Aspose diseñadas para necesidades específicas.

**P2: ¿Puedo personalizar el tamaño de página en Aspose.Page?**  
R2: ¡Por supuesto! Como se muestra en el tutorial, puede especificar diferentes tamaños para cada página según sus requisitos.

**P3: ¿Dónde puedo encontrar más ejemplos y documentación?**  
R3: Visite la [documentación](https://reference.aspose.com/page/net/) para obtener información completa y una variedad de ejemplos.

**P4: ¿Cómo obtengo una licencia temporal para Aspose.Page?**  
R4: Diríjase a [este enlace](https://purchase.aspose.com/temporary-license/) para adquirir una licencia temporal para propósitos de prueba.

**P5: ¿Dónde puedo buscar soporte de la comunidad o hacer preguntas?**  
R5: Únase al [foro de la comunidad Aspose.Page](https://forum.aspose.com/c/page/39) para conectarse con otros desarrolladores, compartir experiencias y buscar ayuda.

---

**Última actualización:** 2026-03-03  
**Probado con:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}