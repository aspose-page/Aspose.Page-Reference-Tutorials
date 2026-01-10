---
date: 2026-01-10
description: Convierta XPS a PDF sin esfuerzo en .NET con Aspose.Page. Descargue la
  biblioteca, explore la documentación y obtenga una prueba gratuita.
linktitle: Convert XPS to PDF
second_title: Aspose.Page .NET API
title: Convertir XPS a PDF con Aspose.Page para .NET
url: /es/net/document-conversion/convert-xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir XPS a PDF con Aspose.Page para .NET

## Introducción

En este tutorial aprenderás **cómo convertir XPS a PDF** usando la biblioteca Aspose.Page para .NET. Convertir XPS a PDF es una necesidad común cuando necesitas compartir documentos XPS con usuarios que solo disponen de lectores PDF, o cuando deseas incrustar contenido XPS en flujos de trabajo PDF más amplios. Repasaremos cada paso, explicaremos por qué cada configuración es importante y te mostraremos cómo afinar la salida—como establecer la calidad JPEG y aplicar compresión de imágenes en PDF.

## Respuestas rápidas
- **¿Qué biblioteca es la mejor para la conversión de XPS a PDF?** Aspose.Page para .NET
- **¿Necesito una licencia para producción?** Sí, se requiere una licencia comercial; hay una versión de prueba disponible.
- **¿Puedo controlar la calidad de la imagen?** Por supuesto—usa `JpegQualityLevel` y `PdfImageCompression`.
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **¿Es posible convertir varios archivos XPS en un solo PDF?** Sí, mediante un bucle que recorra los archivos y fusione los resultados.

## Requisitos previos

Antes de embarcarnos en este proceso de conversión, asegúrate de contar con los siguientes requisitos:

- **Biblioteca Aspose.Page para .NET** – Asegúrate de tener la biblioteca Aspose.Page para .NET instalada en tu entorno de desarrollo. Puedes descargarla desde la [documentación de Aspose.Page](https://reference.aspose.com/page/net/).
- **Entorno de desarrollo** – Configura un entorno de desarrollo .NET con Visual Studio o cualquier otro IDE compatible.
- **Documento XPS** – Prepara el documento XPS que deseas convertir a PDF. Puede ser tu archivo XPS de ejemplo almacenado en un directorio designado.

## Importar espacios de nombres

Antes de sumergirte en el código, importemos el espacio de nombres necesario para que las funcionalidades de Aspose.Page para .NET estén accesibles en nuestro proyecto:

```csharp
using Aspose.Page.XPS;
```

## Guía paso a paso

### Paso 1: Inicializar el directorio del documento

Define la carpeta que contiene tu archivo XPS de origen y donde se guardará el PDF resultante.

```csharp
string dataDir = "Your Document Directory";
```

Reemplaza `"Your Document Directory"` con la ruta absoluta o relativa a la carpeta que contiene tu documento XPS.

### Paso 2: Abrir flujos para la salida PDF y la entrada XPS

Usaremos dos flujos de archivo—uno para leer el archivo XPS y otro para escribir el PDF generado.

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

> **Consejo:** Asegúrate de que las rutas sean correctas y de que la aplicación tenga permisos de lectura/escritura en la carpeta de destino.

### Paso 3: Cargar el documento XPS

Crea una instancia de `XpsDocument` a partir del flujo XPS. El objeto `XpsLoadOptions` te permite especificar preferencias de carga, pero la configuración predeterminada funciona en la mayoría de los escenarios.

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

### Paso 4: Configurar las opciones de guardado PDF

Aquí establecemos las preferencias de salida PDF. Observa el uso de **compresión de imágenes PDF** (`PdfImageCompression.Jpeg`) y **calidad JPEG** (`JpegQualityLevel = 100`). Estas configuraciones afectan directamente el tamaño del archivo y la fidelidad visual.

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

- **`JpegQualityLevel`** – Controla la calidad de las imágenes JPEG incrustadas en el PDF (más alto = mejor calidad, archivo más grande).
- **`ImageCompression`** – Elige el algoritmo de compresión; JPEG es ideal para imágenes fotográficas.
- **`TextCompression`** – La compresión Flate reduce el tamaño del PDF sin perder calidad de texto.
- **`PageNumbers`** – Permite **guardar XPS como PDF** solo para las páginas seleccionadas.

### Paso 5: Crear un dispositivo de renderizado PDF

El `PdfDevice` actúa como el objetivo de renderizado que escribe los datos PDF en el flujo que abrimos anteriormente.

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### Paso 6: Guardar el documento en PDF

Finalmente, invoca el método `Save`, pasando el dispositivo de renderizado y las opciones configuradas.

```csharp
document.Save(device, options);
```

Cuando el código termine de ejecutarse, `XPStoPDF_out.pdf` aparecerá en el directorio que especificaste, conteniendo las páginas convertidas con la compresión y calidad que definiste.

## ¿Por qué convertir XPS a PDF?

- **Accesibilidad universal** – Los visores PDF están instalados en prácticamente cualquier dispositivo, mientras que los lectores XPS son raros.
- **Preservar el diseño** – PDF mantiene el diseño visual exacto, fuentes y gráficos del XPS original.
- **Procesamiento posterior** – Una vez en PDF, puedes fusionar, anotar o firmar digitalmente el documento usando otras bibliotecas Aspose.

## Casos de uso comunes

- **Informes empresariales** – Genera informes XPS desde sistemas heredados y conviértelos a PDF para su distribución.
- **Archivado** – Almacena documentos como PDF para preservación a largo plazo, manteniendo la capacidad de crearlos a partir de fuentes XPS.
- **Servicios web** – Ofrece un endpoint API que acepta cargas XPS y devuelve archivos PDF al instante.

## Solución de problemas y consejos

- **Archivo no encontrado** – Verifica la ruta `dataDir` y asegura que el nombre del archivo XPS coincida exactamente.
- **Errores de permiso** – Ejecuta Visual Studio como Administrador o concede permisos de escritura a la carpeta de salida.
- **PDFs grandes** – Si el PDF resultante es demasiado grande, reduce `JpegQualityLevel` o cambia `ImageCompression` a `PdfImageCompression.Zip`.

## Preguntas frecuentes

### P1: ¿Puedo convertir varios archivos XPS a un solo PDF usando Aspose.Page para .NET?

R1: Sí, puedes iterar sobre varios archivos XPS y seguir los mismos pasos para fusionarlos en un único PDF.

### P2: ¿Hay otros formatos de salida compatibles con Aspose.Page para .NET?

R2: Sí, Aspose.Page para .NET admite varios formatos de salida, incluidos TIFF, JPEG, PNG y más.

### P3: ¿Cómo puedo personalizar la apariencia del documento PDF convertido?

R3: Puedes ajustar los parámetros del objeto de opciones, como la compresión de imágenes y la compresión de texto, para lograr la apariencia deseada.

### P4: ¿Existe una versión de prueba disponible para Aspose.Page para .NET?

R4: Sí, puedes explorar las capacidades de Aspose.Page para .NET obteniendo una prueba gratuita [aquí](https://releases.aspose.com/).

### P5: ¿Dónde puedo obtener soporte comunitario para Aspose.Page para .NET?

R5: Visita el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para discusiones y soporte de la comunidad.

## Preguntas frecuentes (amigable con IA)

**P: ¿Cómo establezco la calidad JPEG al convertir XPS a PDF?**  
R: Usa la propiedad `JpegQualityLevel` dentro de `PdfSaveOptions`. Configurarla en 100 brinda la máxima calidad.

**P: ¿Qué significa “compresión de imagen PDF” en este contexto?**  
R: Se refiere a la opción `ImageCompression`, que determina cómo se comprimen las imágenes dentro del PDF (p. ej., JPEG, Zip).

**P: ¿Puedo generar programáticamente un PDF sin una fuente XPS?**  
R: Sí, Aspose.Page también admite **c# generate pdf** directamente desde comandos de dibujo, aunque eso queda fuera del alcance de este tutorial.

**P: ¿Existe una forma de convertir XPS a PDF sin perder gráficos vectoriales?**  
R: La conversión conserva los datos vectoriales; simplemente evita rasterizar imágenes manteniendo `ImageCompression` configurado en JPEG o Zip según sea necesario.

**P: ¿La biblioteca es compatible con .NET Core?**  
R: Absolutamente – Aspose.Page para .NET funciona con .NET Core, .NET 5, .NET 6 y versiones posteriores.

---

**Última actualización:** 2026-01-10  
**Probado con:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}