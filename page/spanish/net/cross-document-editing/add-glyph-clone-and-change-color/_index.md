---
date: 2026-01-07
description: Aprenda cómo crear un documento XPS, agregar clones de glifos, usar un
  pincel de color sólido y guardar el archivo XPS con Aspose.Page para .NET.
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
title: Crear documento XPS – Añadir clon de glifo y cambiar color con Aspose.Page
  para .NET
url: /es/net/cross-document-editing/add-glyph-clone-and-change-color/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear documento XPS – Añadir clon de glifo y cambiar color con Aspose.Page para .NET

## Introducción

Bienvenido a esta guía paso a paso que le muestra **cómo crear documentos XPS**, clonar glifos y cambiar sus colores usando Aspose.Page para .NET. Ya sea que esté creando informes dinámicos, facturas o gráficos personalizados, dominar estas técnicas le permite producir una salida XPS visualmente rica sin salir del ecosistema .NET.

## Respuestas rápidas
- **¿Cuál es el objetivo principal?** Crear un documento XPS, añadir clones de glifos y cambiar sus colores.  
- **¿Qué biblioteca se utiliza?** Aspose.Page para .NET.  
- **¿Necesito una licencia?** Hay una licencia temporal disponible para evaluación; se requiere una licencia completa para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **¿Cómo guardo el resultado?** Use el método `Save` para escribir el archivo XPS en disco.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de contar con los siguientes requisitos:

- Una comprensión básica del lenguaje de programación C#.  
- Visual Studio o cualquier otro entorno de desarrollo C# preferido instalado.  
- Bibliotheca Aspose.Page para .NET. Puede descargarla [aquí](https://releases.aspose.com/page/net/).  
- Familiaridad con el formato de documento XPS.

## Importar espacios de nombres

Para comenzar, incluya los espacios de nombres necesarios en su proyecto C#:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Cómo crear un documento XPS y añadir clones de glifos

### Paso 1: Configurar el directorio de sus documentos

Comience configurando el directorio donde se almacenarán sus documentos:

```csharp
string dataDir = "Your Document Directory";
```

### Paso 2: Crear el primer documento XPS

Ahora, vamos a crear el primer documento XPS:

```csharp
XpsDocument doc1 = new XpsDocument();
```

### Paso 3: Añadir glifos al primer documento

Añada glifos al primer documento usando los parámetros especificados:

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Paso 4: Rellenar los glifos con un pincel de color sólido

Rellene los glifos en el primer documento con un **pincel de color sólido**, por ejemplo, verde:

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### Paso 5: Crear el segundo documento XPS

Ahora, cree el segundo documento XPS:

```csharp
XpsDocument doc2 = new XpsDocument();
```

### Paso 6: Cómo añadir un clon de glifo a otro documento

Clone glifos del primer documento y añádalos al segundo documento:

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### Paso 7: Cómo cambiar el color del glifo clonado

Cambie el color de los glifos clonados en el segundo documento, por ejemplo, a rojo. Esto demuestra **cómo cambiar el color** de un glifo después de clonarlo:

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### Paso 8: Guardar archivo XPS – Primer documento

Guarde el primer documento XPS en la carpeta que definió anteriormente:

```csharp
doc1.Save(dataDir + "out1.xps");
```

### Paso 9: Guardar archivo XPS – Segundo documento

Guarde el segundo documento XPS:

```csharp
doc2.Save(dataDir + "out2.xps");
```

¡Felicidades! Ha creado con éxito **documentos XPS**, añadido clones de glifos y cambiado sus colores usando Aspose.Page para .NET.

## ¿Por qué usar clonación de glifos y cambios de color?

- **Reutilización:** Clone glifos existentes para reutilizar formas vectoriales complejas sin redefinirlas.  
- **Rendimiento:** Reduce el tiempo de procesamiento comparado con recrear glifos desde cero.  
- **Flexibilidad de diseño:** Aplique diferentes instancias de `SolidColorBrush` al mismo glifo para lograr temas visuales variados.  
- **Edición cruzada de documentos:** Clone glifos entre varios archivos XPS, permitiendo una marca consistente en los informes.

## Problemas comunes y solución de problemas

| Problema | Solución |
|----------|----------|
| **El clon devuelve null** | Asegúrese de que el glifo fuente (`glyphs`) se haya añadido al primer documento antes de clonarlo. |
| **El color no cambia** | Convierta `glyphs.Fill` a `XpsSolidColorBrush` antes de establecer la propiedad `Color` (como se muestra en el Paso 7). |
| **Archivo no guardado** | Verifique que `dataDir` apunte a una carpeta válida y con permisos de escritura y que tenga los permisos adecuados del sistema de archivos. |
| **Tamaño de glifo inesperado** | Ajuste el parámetro de tamaño de fuente (segundo argumento en `AddGlyphs`) para escalar el glifo adecuadamente. |

## Preguntas frecuentes

**P1: ¿Puedo usar Aspose.Page para .NET con otros formatos de documento?**  
R1: Aspose.Page para .NET está diseñado específicamente para trabajar con documentos XPS. Si necesita manipular otros formatos, puede explorar otras bibliotecas Aspose diseñadas para esos formatos.

**P2: ¿Está disponible una licencia temporal para Aspose.Page para .NET?**  
R2: Sí, puede obtener una licencia temporal para propósitos de prueba. Visite [aquí](https://purchase.aspose.com/temporary-license/) para más información.

**P3: ¿Cómo puedo obtener soporte o buscar asistencia para cualquier problema?**  
R3: No dude en visitar el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para conectarse con la comunidad y buscar asistencia.

**P4: ¿Hay limitaciones en la versión de prueba gratuita?**  
R4: La versión de prueba gratuita tiene algunas limitaciones, y se recomienda revisar la documentación para obtener detalles antes de usarla.

**P5: ¿Dónde puedo encontrar documentación completa para Aspose.Page para .NET?**  
R5: Puede consultar la documentación [aquí](https://reference.aspose.com/page/net/) para obtener información detallada y ejemplos.

**P6: ¿Cómo cambio el color del trazo de un glifo en lugar del relleno?**  
R6: Use `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);` para establecer un pincel de trazo.

**P7: ¿Puedo añadir varios clones de glifo al mismo documento?**  
R7: Sí, llame a `doc2.Add(glyphs.Clone());` repetidamente, ajustando las posiciones según sea necesario.

---

**Última actualización:** 2026-01-07  
**Probado con:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}