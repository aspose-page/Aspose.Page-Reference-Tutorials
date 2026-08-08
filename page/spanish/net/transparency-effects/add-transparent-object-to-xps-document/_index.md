---
date: 2026-03-29
description: Aprende cómo agregar objetos transparentes a documentos XPS y luego exportar
  XPS a PDF usando Aspose.Page para .NET. Guía paso a paso con consejos prácticos.
linktitle: Add Transparent Object to XPS Document
second_title: Aspose.Page .NET API
title: Exportar XPS a PDF – Añadir objeto transparente con Aspose.Page
url: /es/net/transparency-effects/add-transparent-object-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exportar XPS a PDF – Agregar objeto transparente con Aspose.Page

## Introducción

En este tutorial aprenderá cómo agregar objetos transparentes a un documento XPS y luego **exportar XPS a PDF** con Aspose.Page para .NET. La transparencia puede hacer que sus documentos se vean más modernos y ayudarle a resaltar información importante. Recorreremos cada paso, explicaremos la lógica detrás del código y le mostraremos cómo finalizar el flujo de trabajo convirtiendo el archivo XPS a un PDF para compartir fácilmente.

## Respuestas rápidas
- **¿Qué significa “exportar XPS a PDF”?** Convertir un archivo XPS en un archivo PDF manteniendo el diseño, los colores y la transparencia.  
- **¿Por qué agregar transparencia primero?** Los objetos transparentes le permiten crear gráficos en capas que se ven geniales en el PDF final.  
- **¿Necesito una licencia?** Sí, se requiere una licencia válida de Aspose.Page para uso en producción.  
- **¿Puede ejecutarse esto en .NET Core?** Absolutamente – Aspose.Page es compatible con .NET Core, .NET 5/6 y el .NET Framework completo.  
- **¿Dónde puedo encontrar más ejemplos?** Consulte la documentación de Aspose.Page y el foro de la comunidad enlazado a continuación.  

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de que tiene los siguientes requisitos previos:

- Aspose.Page para .NET: Asegúrese de que tiene la biblioteca Aspose.Page para .NET instalada. Puede descargarla desde [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

## Importar espacios de nombres

Para comenzar, incluya los espacios de nombres necesarios en su proyecto:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Ahora, procedamos con la guía paso a paso.

## Paso 1: Crear un nuevo documento XPS

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Este código inicializa un nuevo documento XPS usando Aspose.Page para .NET.

## Paso 2: Demostrar la transparencia

```csharp
// Just to demonstrate transparency
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

Estas líneas crean dos rutas grises que servirán como fondo para las formas transparentes que agregaremos más adelante.

## Paso 3: Crear una ruta con una geometría de rectángulo cerrado

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Aquí creamos un rectángulo azul. Como más adelante cambiaremos su opacidad, el rectángulo aparecerá semitransparente en el PDF final.

## Paso 4: Manipular rutas y colores

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

Clonamos el primer rectángulo, lo añadimos a la página y cambiamos su color de relleno a verde. Esto demuestra lo fácil que es reutilizar geometrías existentes.

## Paso 5: Clonar y transformar rutas

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

La ruta clonada se desplaza 300 unidades hacia abajo y se pinta de rojo, proporcionando un efecto de capas apiladas.

## Paso 6: Repetir y modificar rutas

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Reutilizamos los datos de geometría de `path2`, los movemos a la derecha y aplicamos nuevamente un relleno azul.

## Paso 7: Gestionar la opacidad

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

Establecer la propiedad `Opacity` a 0.8 hace que este rectángulo sea 80 % opaco, ilustrando cómo puede ajustar finamente la transparencia de cada elemento.

## Paso 8: Guardar el documento XPS

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

El archivo XPS ahora está guardado con todos los objetos transparentes aplicados.  

**Exportar a PDF:** Para **exportar XPS a PDF**, simplemente llame a `doc.Save` nuevamente con una extensión `.pdf`, por ejemplo, `doc.Save(dataDir + "TransparentDocument.pdf");`. La misma fidelidad visual, incluidos los ajustes de opacidad, se conserva en el PDF resultante.

## ¿Por qué exportar XPS a PDF después de agregar transparencia?

- **Compatibilidad universal:** PDF es ampliamente compatible en todas las plataformas, mientras que XPS es más especializado.  
- **Efectos visuales preservados:** Aspose.Page mantiene la transparencia, los degradados y las transformaciones de matriz intactas durante la conversión.  
- **Facilidad de compartir:** Los PDFs pueden abrirse en navegadores, dispositivos móviles y muchos lectores de terceros sin complementos adicionales.  

## Casos de uso comunes

- **Folletos de marketing** donde los gráficos en capas brindan una sensación premium.  
- **Diagramas técnicos** que necesitan secciones resaltadas sin saturar el diseño.  
- **Generación de informes** donde desea superponer marcas de agua o logotipos con opacidad parcial.  

## Consejos y advertencias

- **Consejo profesional:** Siempre establezca el valor `Opacity` entre 0 y 1. Los valores fuera de este rango se limitan y pueden producir resultados inesperados.  
- **Consejo de rendimiento:** Reutilizar geometría (`path2.Data`) reduce el uso de memoria cuando necesita muchas formas similares.  
- **Trampa:** Guardar directamente a PDF después de agregar transparencia funciona de inmediato, pero si luego edita el PDF con otras herramientas, algunos visores antiguos pueden no renderizar la opacidad correctamente.  

## Conclusión

Agregar objetos transparentes a documentos XPS usando Aspose.Page para .NET proporciona una forma versátil de mejorar presentaciones visuales. Una vez que su archivo XPS tenga el aspecto deseado, puede **exportar XPS a PDF** en una sola línea de código, preservando todos los efectos de transparencia para una amplia distribución.

## Preguntas frecuentes

### Q1: ¿Puedo aplicar transparencia a cualquier objeto en un documento XPS?

A1: Sí, la transparencia se puede aplicar a varios objetos como rutas, formas e imágenes en un documento XPS.  

### Q2: ¿Cómo puedo ajustar la opacidad de un elemento específico?

A2: Puede establecer la propiedad de opacidad del Fill o Stroke para ajustar la transparencia de un elemento específico.  

### Q3: ¿Es Aspose.Page compatible con .NET Core?

A3: Sí, Aspose.Page es compatible con .NET Core, lo que permite el desarrollo multiplataforma.  

### Q4: ¿Puedo exportar documentos XPS a otros formatos usando Aspose.Page?

A4: Aspose.Page ofrece funcionalidad para exportar documentos XPS a varios formatos, incluidos PDF e imágenes.  

### Q5: ¿Dónde puedo encontrar soporte adicional y discusiones de la comunidad?

A5: Para obtener soporte adicional y discusiones de la comunidad, visite el [Aspose.Page Forum](https://forum.aspose.com/c/page/39).  

### Q6: ¿La conversión a PDF mantiene mis configuraciones de transparencia?

A6: Absolutamente. Cuando exporta XPS a PDF con Aspose.Page, todas las configuraciones de opacidad y mezcla se conservan.  

### Q7: ¿Puedo procesar por lotes varios archivos XPS a PDF?

A7: Sí, puede iterar a través de una colección de archivos XPS y llamar a `doc.Save(...".pdf")` para cada uno, automatizando conversiones masivas.  

---

**Última actualización:** 2026-03-29  
**Probado con:** Aspose.Page 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}