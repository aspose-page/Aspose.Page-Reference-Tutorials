---
date: 2026-01-25
description: Aprenda a configurar XMP y cambiar valores nombrados en archivos EPS
  usando Aspose.Page para .NET. Personalice los metadatos XMP sin esfuerzo para un
  procesamiento de documentos a medida.
linktitle: Change Named Value
second_title: Aspose.Page .NET API
title: Cómo establecer XMP y cambiar el valor nombrado con Aspose.Page para .NET
url: /es/net/eps-metadata-management/modify-eps-metadata-change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer XMP y cambiar valores nombrados con Aspose.Page para .NET

## Introducción

Si necesita **cómo establecer XMP** dentro de un archivo EPS y también **cambiar valores nombrados** en sus metadatos, ha llegado al lugar correcto. En este tutorial recorreremos un escenario del mundo real donde modifica los metadatos XMP usando Aspose.Page para .NET, dándole control total sobre las propiedades del documento, la marca y el procesamiento posterior.

## Respuestas rápidas
- **¿Qué es XMP?** Un formato estandarizado para incrustar metadatos en archivos gráficos y de documentos.  
- **¿Por qué cambiar un valor nombrado?** Para actualizar campos de metadatos específicos, como el tamaño de página o etiquetas personalizadas, sin reescribir todo el archivo.  
- **¿Qué biblioteca ayuda?** Aspose.Page para .NET proporciona una API sencilla para ambas tareas.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Plataformas compatibles?** .NET Framework, .NET Core y .NET 5/6+.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de contar con los siguientes requisitos:

- Aspose.Page para .NET: Asegúrese de que tiene la biblioteca Aspose.Page para .NET instalada. Si no, puede descargarla [aquí](https://releases.aspose.com/page/net/).

- Directorio de documentos: Tenga un directorio designado para sus archivos EPS donde pueda realizar los cambios de valores nombrados.

## Importar espacios de nombres

En su proyecto .NET, necesita importar los espacios de nombres necesarios para acceder a la funcionalidad proporcionada por Aspose.Page. Añada los siguientes espacios de nombres a su código:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ahora, desglosaremos el código en varios pasos para una comprensión completa:

## Paso 1: Inicializar el flujo de entrada del archivo EPS

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:1
```

En este paso, configuramos el flujo de entrada para el archivo EPS que desea modificar. Asegúrese de reemplazar "Your Document Directory" con la ruta real a su directorio de documentos.

## Paso 2: Obtener los metadatos XMP

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Recupere los metadatos XMP existentes del archivo EPS. Si el archivo EPS no contiene metadatos XMP, se generará uno nuevo con valores de los comentarios de metadatos PS.

## Paso 3: Cambiar los valores de los metadatos XMP

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Aquí demostramos cómo **cambiar valores nombrados** dentro de la estructura `xmpTPg:MaxPageSize`. Puede adaptar los nombres de propiedades y valores para ajustarlos a sus propios requisitos de metadatos.

## Paso 4: Guardar el archivo EPS con los metadatos XMP modificados

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Guarde el archivo EPS modificado en el flujo de salida. El archivo reflejará ahora los cambios realizados en los metadatos XMP.

## Problemas comunes y soluciones

- **Sección XMP faltante** – Si el EPS de origen no contiene XMP, Aspose.Page crea automáticamente un bloque XMP mínimo. Luego puede agregar sus valores nombrados personalizados como se muestra arriba.  
- **Prefijo de espacio de nombres incorrecto** – Asegúrese de que el espacio de nombres (p. ej., `xmpTPg`) coincida con el presente en los metadatos originales; de lo contrario, la API lo tratará como una nueva propiedad.  
- **Errores de acceso al archivo** – Verifique que la aplicación tenga permisos de lectura/escritura para el directorio que especifica en `dataDir`.

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Page para .NET con otros formatos de documento?**  
A: Sí, Aspose.Page admite varios formatos de documento, incluidos EPS, XPS y PDF.

**Q: ¿Hay una versión de prueba disponible para Aspose.Page para .NET?**  
A: Sí, puede acceder a una prueba gratuita [aquí](https://releases.aspose.com/).

**Q: ¿Dónde puedo encontrar más documentación sobre Aspose.Page para .NET?**  
A: Consulte la documentación [aquí](https://reference.aspose.com/page/net/).

**Q: ¿Cómo puedo obtener una licencia temporal para Aspose.Page para .NET?**  
A: Puede obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

**Q: ¿Qué opciones de soporte están disponibles para los usuarios de Aspose.Page para .NET?**  
A: Visite el foro de la comunidad [aquí](https://forum.aspose.com/c/page/39) para soporte y discusiones.

---

**Última actualización:** 2026-01-25  
**Probado con:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}