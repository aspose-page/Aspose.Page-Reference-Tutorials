---
date: 2026-03-03
description: Aprenda a usar Aspose.Page para .NET para mosaicar imágenes en documentos
  XPS. Esta guía paso a paso muestra cómo mosaicar imágenes de manera eficiente y
  mejorar el atractivo visual.
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: Cómo usar Aspose.Page para añadir una imagen en mosaico a un documento XPS
url: /es/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo usar Aspose.Page para agregar una imagen en mosaico a un documento XPS

## Introducción

Si te preguntas **cómo usar Aspose** para darle a tus archivos XPS un estilo visual más rico, has llegado al lugar correcto. En este tutorial recorreremos los pasos exactos necesarios para **colocar una imagen en mosaico** dentro de un documento XPS usando Aspose.Page para .NET. Al final tendrás un fragmento reutilizable que podrás insertar en cualquier proyecto .NET para crear gráficos de imágenes en mosaico al instante.

## Respuestas rápidas
- **¿Qué biblioteca se necesita?** Aspose.Page for .NET  
- **¿Qué método crea el pincel en mosaico?** `CreateImageBrush` con `TileMode = XpsTileMode.Tile`  
- **¿Puedo controlar la opacidad?** Sí – establece `path.Fill.Opacity` (p. ej., 0.5f)  
- **¿Necesito una licencia para pruebas?** Una licencia temporal funciona para evaluación; se requiere una licencia completa para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## ¿Qué es Aspose.Page y por qué mosaicar imágenes?

Aspose.Page es una API potente que permite a los desarrolladores generar, editar y renderizar XPS, PDF y otros formatos basados en páginas sin depender de Microsoft Office. Colocar una imagen en mosaico —repetir un mapa de bits a lo largo de una forma— te ayuda a rellenar áreas grandes con patrones, marcas de agua o texturas de fondo mientras mantienes el tamaño del archivo bajo.

## Cómo usar Aspose.Page para mosaicar imágenes en documentos XPS

A continuación encontrarás un ejemplo completo y listo para ejecutar. Cada paso se explica en lenguaje sencillo antes del bloque de código correspondiente, para que puedas ver **por qué** cada línea es importante.

### Requisitos previos

- **Aspose.Page for .NET** – descarga y referencia la biblioteca desde el sitio oficial [here](https://reference.aspose.com/page/net/).  
- **Entorno de desarrollo** – Visual Studio (cualquier edición) u otro IDE .NET que prefieras.

### Importar espacios de nombres

Primero, incluye los espacios de nombres requeridos para que el compilador sepa dónde encontrar las clases XPS.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### Paso 1: Definir el directorio del documento

Especifica dónde se guardarán el archivo XPS generado y la imagen de origen. Reemplaza el marcador de posición con una carpeta real en tu máquina.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Paso 2: Crear un nuevo documento XPS

Instancia un documento XPS vacío que contendrá el gráfico en mosaico.

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Paso 3: Agregar una imagen en mosaico

Aquí creamos una ruta rectangular, la rellenamos con un `ImageBrush` y configuramos el pincel en modo mosaico. La propiedad `TileMode` indica al motor que repita la imagen tanto horizontal como verticalmente. Ajusta las coordenadas del rectángulo o la imagen de origen según sea necesario para tu caso.

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### Paso 4: Guardar el documento XPS resultante

Finalmente, escribe el documento en disco. El archivo de salida puede abrirse con cualquier visor XPS o procesarse más con Aspose.Page.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## Problemas comunes y consejos

- **Errores de ruta** – Asegúrate de que `dataDir` termine con una barra diagonal o usa `Path.Combine` para evitar problemas de separador faltante.  
- **Desajustes de tamaño de imagen** – La imagen de origen debe ser lo suficientemente grande para el área de mosaico; de lo contrario el patrón puede aparecer estirado.  
- **Opacidad no visible** – Algunos visores ignoran la opacidad en XPS; prueba con un visor que soporte completamente el renderizado XPS (p. ej., XPS Viewer en Windows).

## Preguntas frecuentes

### Q1: ¿Es Aspose.Page compatible con todos los entornos de desarrollo .NET?
A: Sí, Aspose.Page funciona con Visual Studio, Rider, VS Code y cualquier IDE que soporte .NET.

### Q2: ¿Puedo ajustar la opacidad de la imagen en mosaico?
A: Por supuesto. El ejemplo establece `path.Fill.Opacity = 0.5f;`—puedes cambiar el valor flotante entre 0 (transparente) y 1 (opaco).

### Q3: ¿Hay otros modos de mosaico disponibles en Aspose.Page para .NET?
A: Sí. Además de `XpsTileMode.Tile`, puedes usar `FlipX`, `FlipY` y `FlipXY` para crear patrones reflejados.

### Q4: ¿Cómo manejo las licencias temporales para Aspose.Page?
A: Consulta la página de [temporary license](https://purchase.aspose.com/temporary-license/) en el sitio web de Aspose para obtener detalles sobre cómo obtener y aplicar una licencia de prueba.

### Q5: ¿Dónde puedo buscar ayuda o conectarme con la comunidad de Aspose.Page?
A: Visita el [Aspose.Page forum](https://forum.aspose.com/c/page/39) para hacer preguntas, compartir fragmentos y aprender de otros desarrolladores.

### Q6: ¿Puedo usar este enfoque para crear un efecto de marca de agua?
A: Sí. Al reducir la opacidad y elegir una imagen semitransparente, el pincel en mosaico funciona perfectamente como una marca de agua repetida.

## Conclusión

Ahora sabes **cómo usar Aspose** para agregar una imagen en mosaico a un documento XPS, controlar su opacidad y guardar el resultado para uso posterior. Esta técnica es ideal para patrones de fondo, marcas de agua o cualquier situación donde un gráfico repetido añade interés visual sin inflar el tamaño del archivo. Siéntete libre de experimentar con diferentes formas, imágenes y modos de mosaico para adaptarlos a las necesidades de tu proyecto.

---

**Última actualización:** 2026-03-03  
**Probado con:** Aspose.Page for .NET (última versión)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}