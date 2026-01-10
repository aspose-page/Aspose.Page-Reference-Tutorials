---
date: 2026-01-10
description: Aprenda a combinar documentos XPS con Aspose.Page para .NET. Esta guía
  paso a paso muestra técnicas de manipulación de páginas para obtener resultados
  eficientes.
linktitle: Manipulate Pages
second_title: Aspose.Page .NET API
title: Combinar documentos XPS con Aspose.Page para .NET
url: /es/net/cross-document-editing/manipulate-pages/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fusionar documentos XPS con Aspose.Page para .NET

## Introducción

## Respuestas rápidas
- **¿Qué puedo hacer con Aspose.Page?** Fusionar documentos XPS, insertar, agregar o eliminar páginas, y guardar el resultado.  
- **¿Necesito una licencia para pruebas?** Hay una licencia temporal disponible para evaluación.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **¿Se requiere Visual Studio?** No, cualquier IDE que soporte C# funciona, pero se recomienda Visual Studio.  
- **¿Cuánto tiempo lleva la fusión?** Normalmente unos pocos segundos para archivos XPS de tamaño estándar.

## ¿Qué es la fusión de documentos XPS?
Fusionar documentos XPS significa tomar páginas de dos o más archivos XPS existentes y combinarlas en un solo documento XPS. Esto es útil para crear informes consolidados, compilar manuales multipágina o preparar paquetes listos para imprimir sin convertir a otro formato.

## ¿Por qué usar Aspose.Page para .NET?
Aspose.Page ofrece una **API puramente .NET** que trabaja directamente con archivos XPS—no se necesita herramientas externas ni componentes de terceros. Le brinda un control fino sobre el orden de las páginas, los puntos de inserción y la preservación del contenido, haciendo que el proceso de fusión sea fiable y rápido.

## Requisitos previos

- **Aspose.Page for .NET** – download from the [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).  
- **Entorno de desarrollo** – Visual Studio, Rider, o cualquier IDE que soporte C#.  
- **Archivos XPS de entrada** – tres archivos de muestra (`input1.xps`, `input2.xps`, `input3.xps`) ubicados en una carpeta conocida.

## Importar espacios de nombres

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Estos espacios de nombres le dan acceso a las clases principales de documentos XPS, modelos de página y utilidades básicas de dibujo.

## Paso 1: Establecer el directorio de documentos

```csharp
string dataDir = "Your Document Directory";
```

Reemplace **Your Document Directory** con la ruta completa donde se almacenan sus archivos XPS, por ejemplo, `C:\\Docs\\XpsFiles\\`.

## Paso 2: Crear instancias de documentos XPS

```csharp
XpsDocument doc1 = new XpsDocument(dataDir + "input1.xps");
XpsDocument doc2 = new XpsDocument(dataDir + "input2.xps");
XpsDocument doc3 = new XpsDocument(dataDir + "input3.xps");
XpsDocument doc4 = new XpsDocument();
```

- `doc1`, `doc2` y `doc3` representan los documentos fuente que desea fusionar.  
- `doc4` es un documento XPS vacío que contendrá el resultado fusionado.

## Paso 3: Insertar, agregar y eliminar páginas

```csharp
doc4.InsertPage(1, doc2.Page, false);
doc4.AddPage(doc3.Page, false);
doc4.RemovePageAt(2);
doc4.InsertPage(2, doc1.SelectActivePage(3), false);
```

Esto es lo que hace cada línea:

1. **InsertPage(1, doc2.Page, false)** – coloca la primera página de `doc2` en la posición 1 de `doc4`.  
2. **AddPage(doc3.Page, false)** – agrega la primera página de `doc3` al final de `doc4`.  
3. **RemovePageAt(2)** – elimina la página que ahora está en el índice 2 (útil para eliminar páginas no deseadas).  
4. **InsertPage(2, doc1.SelectActivePage(3), false)** – inserta la tercera página de `doc1` en la posición 2, completando la fusión.

Estas operaciones ilustran cómo puede **fusionar documentos XPS** mientras reordena o descarta páginas según sea necesario.

## Paso 4: Guardar el documento fusionado

```csharp
doc4.Save(dataDir + "out.xps");
```

El archivo XPS final fusionado (`out.xps`) se escribe en el mismo directorio. Ahora puede abrirlo en cualquier visor XPS o procesarlo más con Aspose.Page.

## Problemas comunes y soluciones
- **Archivo no encontrado** – verifique la ruta `dataDir` y asegúrese de que los archivos de entrada existan.  
- **Índice de página no válido** – los índices de página comienzan en 1; intentar insertar una página inexistente lanza una excepción.  
- **Errores de licencia** – use una licencia temporal o completa antes de desplegar a producción.

## Preguntas frecuentes

### P1: ¿Puedo manipular páginas de diferentes documentos XPS?

A1: Sí, como se muestra en el tutorial, puede insertar páginas de varios documentos XPS en un nuevo documento.

### P2: ¿Cómo puedo eliminar una página específica de un documento?

A2: Utilice el método `RemovePageAt`, especificando el índice de la página que desea eliminar.

### P3: ¿Aspose.Page es compatible con Visual Studio?

A3: Sí, Aspose.Page es totalmente compatible con Visual Studio, lo que facilita su integración en sus proyectos .NET.

### P4: ¿Hay opciones de licencia disponibles?

A4: Sí, puede explorar las opciones de licencia y obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

### P5: ¿Dónde puedo obtener soporte o hacer preguntas?

A5: Visite el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para obtener soporte y participar con la comunidad.

## Preguntas frecuentes

**P: ¿Puedo fusionar más de tres archivos XPS?**  
A: Absolutamente. Cree instancias adicionales de `XpsDocument` y use `InsertPage` o `AddPage` repetidamente para crear un documento fusionado más grande.

**P: ¿La fusión conserva el formato y los gráficos originales?**  
A: Sí. Aspose.Page copia el contenido de la página byte por byte, por lo que el texto, imágenes y gráficos vectoriales permanecen sin cambios.

**P: ¿Cómo inserto una página al final sin especificar un índice?**  
A: Utilice `AddPage(sourcePage, false)` que agrega la página al final del documento.

**P: ¿Es posible fusionar documentos XPS en un servidor sin UI?**  
A: La API es completamente sin cabeza; puede ejecutar el mismo código en ASP.NET, Azure Functions o cualquier entorno .NET del lado del servidor.

**P: ¿Qué pasa si mis archivos XPS están protegidos con contraseña?**  
A: Aspose.Page actualmente no soporta archivos XPS encriptados; debe desencriptarlos antes de fusionarlos.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Page for .NET 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}