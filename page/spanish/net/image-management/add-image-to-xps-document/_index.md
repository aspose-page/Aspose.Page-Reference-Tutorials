---
date: 2026-02-28
description: Aprenda a crear documentos XPS en .NET y agregar imágenes usando Aspose.Page
  para .NET. Siga esta guía paso a paso para una experiencia de desarrollo fluida.
linktitle: Add Image to XPS Document
second_title: Aspose.Page .NET API
title: Crear documento XPS .NET – Agregar imagen con Aspose.Page
url: /es/net/image-management/add-image-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Añadir imagen a un documento XPS con Aspose.Page para .NET

En este tutorial aprenderá a **create XPS document .NET** y a incrustar una imagen utilizando la potente biblioteca Aspose.Page. Ya sea que esté generando informes, facturas o gráficos personalizados, añadir elementos visuales a archivos XPS es un requisito frecuente para los desarrolladores .NET.

## Introducción

En el mundo del desarrollo .NET, incorporar imágenes en documentos XPS es una necesidad común. Aspose.Page para .NET simplifica este proceso, ofreciendo un conjunto de herramientas potente para manipular y mejorar documentos XPS sin esfuerzo. Este tutorial le guiará paso a paso para agregar una imagen a un documento XPS usando Aspose.Page para .NET.

## Respuestas rápidas
- **¿Qué cubre este tutorial?** Añadir una imagen a un documento XPS con Aspose.Page para .NET.  
- **¿Qué palabra clave principal se dirige?** *create xps document .net*  
- **¿Necesito una licencia?** Hay una prueba gratuita disponible; se requiere una licencia para producción.  
- **¿Qué versiones de .NET son compatibles?** Funciona con .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 5‑10 minutos para una inserción básica de imagen.

## ¿Qué es “create XPS document .NET”?
Crear un documento XPS en .NET significa generar programáticamente un archivo XML Paper Specification (XPS) —un formato de documento de diseño fijo— usando C# o VB.NET. Aspose.Page proporciona una API fluida que abstrae los detalles de bajo nivel, permitiéndole centrarse en el contenido como texto, formas e imágenes.

## ¿Por qué usar Aspose.Page para agregar una imagen?
- **Control total** sobre la posición, escala y recorte de las imágenes.  
- **Sin dependencias externas** – la biblioteca maneja la decodificación de imágenes internamente.  
- **Compatibilidad multiplataforma** para entornos Windows y Linux.  
- **Alta fidelidad** de renderizado que preserva la calidad de la imagen en el archivo XPS final.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de contar con los siguientes requisitos:

1. Biblioteca Aspose.Page para .NET: Descargue e instale la biblioteca desde [Aspose.Page .NET Documentation](https://reference.aspose.com/page/net/).

2. Entorno de desarrollo: Configure un entorno de desarrollo .NET, como Visual Studio.

3. Imagen de ejemplo: Tenga un archivo de imagen de ejemplo (p. ej., "QL_logo_color.tif") que desee agregar al documento XPS.

## Importar espacios de nombres

Comience importando los espacios de nombres necesarios en su proyecto .NET. Estos espacios de nombres son esenciales para utilizar las funciones que ofrece Aspose.Page para .NET.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Aspose.Page: agregar imagen a un documento XPS

A continuación, recorremos cada paso necesario para **create XPS document .NET** e incrustar una imagen.

### Paso 1: establecer el directorio del documento

Comience especificando la ruta a su directorio de documentos. Este paso garantiza que su proyecto sepa dónde localizar y guardar los archivos.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// ExEnd:1
```

### Paso 2: crear documento XPS

Cree un nuevo documento XPS usando Aspose.Page para .NET.

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// ExEnd:1
```

### Paso 3: agregar imagen al documento XPS

Ahora, agreguemos la imagen al documento XPS. En este ejemplo, utilizaremos una imagen de muestra llamada "QL_logo_color.tif".

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// ExEnd:1
```

### Paso 4: guardar el documento XPS resultante

Guarde el documento XPS con la imagen añadida.

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// ExEnd:1
```

¡Ahora ha agregado exitosamente una imagen a un documento XPS usando Aspose.Page para .NET!

## Problemas comunes y soluciones

- **Error de archivo no encontrado** – Verifique que `dataDir` apunte a la carpeta correcta y que el nombre del archivo de imagen coincida exactamente, incluida la sensibilidad a mayúsculas en Linux.  
- **La imagen aparece distorsionada** – Ajuste los factores de escala de `CreateMatrix` o los parámetros de `RectangleF` para controlar el tamaño y la relación de aspecto.  
- **Formato de imagen no compatible** – Aspose.Page admite formatos raster comunes (PNG, JPEG, TIFF). Convierta los formatos no compatibles antes de usar `CreateImageBrush`.

## Preguntas frecuentes

### Q1: ¿Aspose.Page para .NET es compatible con las versiones más recientes del framework .NET?

A1: Aspose.Page para .NET está diseñado para ser compatible con una amplia gama de versiones del framework .NET, incluidas las más recientes. Consulte la [documentación](https://reference.aspose.com/page/net/) para obtener detalles específicos.

### Q2: ¿Puedo usar Aspose.Page para .NET tanto en entornos Windows como Linux?

A2: Sí, Aspose.Page para .NET es independiente de la plataforma, lo que lo hace adecuado para su uso tanto en Windows como en Linux.

### Q3: ¿Existen opciones de licencia para Aspose.Page para .NET?

A3: Sí, puede explorar las opciones de licencia y realizar una compra [aquí](https://purchase.aspose.com/buy).

### Q4: ¿Hay una prueba gratuita disponible para Aspose.Page para .NET?

A4: Sí, puede probar Aspose.Page para .NET de forma gratuita accediendo a la [prueba gratuita](https://releases.aspose.com/).

### Q5: ¿Dónde puedo buscar asistencia o interactuar con la comunidad de Aspose.Page para .NET?

A5: Visite el [foro de Aspose.Page para .NET](https://forum.aspose.com/c/page/39) para conectarse con la comunidad y obtener soporte.

## Conclusión

En este tutorial, exploramos cómo aprovechar Aspose.Page para .NET e incorporar imágenes de manera fluida en documentos XPS. Esta guía paso a paso garantiza un proceso de integración sin problemas, mejora sus capacidades de desarrollo .NET y le ayuda a **create XPS document .NET** con riqueza visual.

---

**Última actualización:** 2026-02-28  
**Probado con:** Aspose.Page para .NET 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}