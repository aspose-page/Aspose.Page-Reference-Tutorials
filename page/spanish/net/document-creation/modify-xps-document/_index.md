---
date: 2026-01-12
description: Aprenda cómo modificar documentos XPS usando Aspose.Page para .NET y
  descubra cómo agregar texto a archivos XPS con ejemplos de código simples.
linktitle: Modify XPS Document
second_title: Aspose.Page .NET API
title: Modificar documento XPS con Aspose.Page para .NET
url: /es/net/document-creation/modify-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modificar documento XPS con Aspose.Page para .NET

## Introducción

Bienvenido a nuestra guía paso a paso sobre **cómo modificar documentos xps** con Aspose.Page para .NET. Ya sea que necesite insertar una firma, añadir una marca de agua o simplemente colocar texto personalizado en una página, este tutorial le muestra exactamente **cómo agregar texto** a un documento XPS en pocos minutos. Revisaremos cada línea de código, explicaremos por qué cada paso es importante y le daremos consejos para evitar errores comunes.

### Respuestas rápidas
- **¿Qué cubre este tutorial?** Añadir un texto de firma ("Confirmed") a páginas seleccionadas de un archivo XPS.  
- **¿Qué biblioteca se requiere?** Aspose.Page para .NET (última versión).  
- **¿Necesito una licencia?** Una licencia temporal funciona para pruebas; se requiere una licencia completa para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10 minutos para una inserción básica de firma.

## ¿Qué es modificar un documento XPS?

XPS (XML Paper Specification) es el formato de documento de diseño fijo de Microsoft, similar al PDF. Modificar un documento XPS significa cambiar programáticamente su contenido visual —agregar texto, imágenes o formas— sin convertir el archivo a otro formato. Aspose.Page proporciona un modelo de objetos rico que le permite editar archivos XPS directamente desde su código .NET.

## ¿Por qué usar Aspose.Page para modificar documentos XPS?

* **Control total** – trabajar con páginas, glifos, pinceles y transformaciones a bajo nivel.  
* **Sin dependencias externas** – biblioteca .NET pura, sin necesidad de componentes de Office o Adobe.  
* **Multiplataforma** – funciona en Windows, Linux y macOS a través de .NET Core.  
* **Rendimiento robusto** – maneja documentos grandes de manera eficiente y soporta tipografía avanzada.

## Requisitos previos

- **Aspose.Page para .NET** – Instale el paquete NuGet o descargue la biblioteca desde la documentación oficial **[here](https://reference.aspose.com/page/net/)**.  
- **Archivo XPS de entrada** – Obtenga un documento XPS de muestra (p. ej., `input1.xps`) desde la **[Aspose releases page](https://releases.aspose.com/page/net/)**.  
- **Directorio de trabajo** – Cree una carpeta en su máquina para almacenar los archivos de entrada y salida y anote su ruta completa; asignará esta ruta a la variable `dir` en el código.  
- **Entorno de desarrollo** – Visual Studio 2019/2022, .NET Framework 4.7.2 o posterior, o cualquier proyecto .NET Core/5/6.

Ahora que todo está configurado, vamos a sumergirnos en el código.

## Importar espacios de nombres

En su proyecto .NET, comience importando los espacios de nombres requeridos para Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## Paso 1: Abrir flujo del documento XPS

Abriremos el archivo XPS de origen como un flujo y crearemos un objeto `XpsDocument` que representa todo el documento.

```csharp
// ExStart:3
// The path to the documents directory.
string dir = "Your Document Directory";
// Open a stream of XPS file
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // Create PS document from stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // Continue to the next step...
}
// ExEnd:3
```

*Consejo profesional:* Envuelva el flujo en un bloque `using` para asegurar que el manejador del archivo se libere automáticamente.

## Paso 2: Crear texto de firma

A continuación, creamos un pincel de color sólido que se usará para pintar los glifos de la firma.

```csharp
// ExStart:4
// Create fill of the signature text
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Continue to the next step...
// ExEnd:4
```

Puede cambiar `Color.BlueViolet` a cualquier `System.Drawing.Color` que coincida con la identidad de su marca.

## Paso 3: Definir páginas y agregar firma

Especificaremos qué páginas deben recibir la firma y luego añadiremos los glifos a cada página.

```csharp
// ExStart:5
// Define pages where signature will be set
int[] pageNumbers = new int[] {1, 2, 3};

// For every defined page set signature "Confirmed" at coordinates x=650 and y=950
for (int i = 0; i < pageNumbers.Length; i++)
{
    // Define active page
    document.SelectActivePage(pageNumbers[i]);

    // Create glyphs object
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // Define fill for glyphs
    glyphs.Fill = textFill;
}
// Continue to the next step...
// ExEnd:5
```

*¿Por qué estas coordenadas?* Los valores X y Y se miden en puntos (1/72 pulgada). Ajústelos para posicionar el texto exactamente donde lo necesite en el diseño de su página.

## Paso 4: Guardar cambios en el documento XPS

Finalmente, escriba el documento modificado de nuevo en el disco.

```csharp
// ExStart:6
// Save changed XPS document
document.Save(dir + "input1_out.xps");
// ExEnd:6
```

El nuevo archivo `input1_out.xps` ahora contiene la firma “Confirmed” en las páginas 1‑3.

## Problemas comunes y soluciones

| Problema | Causa | Solución |
|----------|-------|----------|
| **Firma no visible** | Coordenadas incorrectas o página no seleccionada | Verifique que `SelectActivePage` se llame para cada página y ajuste los valores X/Y. |
| **Excepción en `AddGlyphs`** | Fuente no instalada en el servidor | Asegúrese de que la fuente especificada (p. ej., Arial) esté disponible, o incruste una fuente personalizada usando `document.AddFont`. |
| **Archivo de salida corrupto** | Flujo no cerrado correctamente | Utilice sentencias `using` para todos los flujos y llame a `document.Dispose()` si es necesario. |
| **Ralentización del rendimiento en archivos grandes** | Cargando todo el documento en memoria | Procese las páginas en lotes o use `XpsLoadOptions` con opciones de transmisión (si están disponibles en versiones más recientes). |

## Preguntas frecuentes

**P: ¿Es Aspose.Page compatible con los últimos frameworks .NET?**  
R: Sí, Aspose.Page se actualiza regularmente para soportar .NET Framework 4.5+, .NET Core 3.1+, .NET 5 y .NET 6.

**P: ¿Puedo personalizar la fuente y el estilo del texto añadido?**  
R: Por supuesto. Cambie los parámetros de `AddGlyphs` (nombre de fuente, tamaño, `FontStyle`) para adaptarlos a su diseño.

**P: ¿Existen límites de tamaño para los archivos XPS?**  
R: Aspose.Page puede manejar documentos grandes, pero el consumo de memoria crece con el tamaño del archivo. Para archivos muy grandes, considere procesar las páginas individualmente.

**P: ¿Cómo obtengo una licencia temporal para Aspose.Page?**  
R: Puede adquirir una licencia temporal **[here](https://purchase.aspose.com/temporary-license/)**.

**P: ¿Dónde puedo buscar ayuda o conectarme con la comunidad de Aspose?**  
R: Visite el **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** para hacer preguntas y compartir experiencias.

## Conclusión

En este tutorial demostramos cómo **modificar documentos xps** añadiendo texto de firma personalizado usando Aspose.Page para .NET. Ahora cuenta con una base sólida para insertar cualquier texto, marca de agua o anotación en páginas específicas de un archivo XPS. Experimente con diferentes fuentes, colores y posiciones para cumplir con los requisitos de marca de su aplicación, y explore la API más amplia de Aspose.Page para capacidades avanzadas de gráficos y diseño.

---

**Última actualización:** 2026-01-12  
**Probado con:** Aspose.Page 24.11 para .NET (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}