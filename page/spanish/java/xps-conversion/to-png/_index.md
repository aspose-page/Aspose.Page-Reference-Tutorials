---
date: 2025-12-23
description: Convierte sin esfuerzo **XPS a PNG** en Java usando Aspose.Page. Esta
  guía muestra cómo renderizar XPS a archivos de imagen con una solución fiable y
  amigable para desarrolladores.
linktitle: Convert XPS to PNG in Java
second_title: Aspose.Page Java API
title: Convertir XPS a PNG en Java
url: /es/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir XPS a PNG en Java

## Introducción
En el dinámico mundo del desarrollo de software, la necesidad de **convertir XPS a PNG** (XML Paper Specification a Portable Network Graphics) surge con frecuencia. Para lograr esta tarea sin problemas en Java, Aspose.Page ofrece una solución potente. En este tutorial, recorreremos el proceso de conversión de XPS a PNG usando Aspose.Page para Java.

## Respuestas rápidas
- **¿Qué biblioteca maneja la conversión?** Aspose.Page para Java  
- **¿Qué formatos están involucrados?** XPS (origen) → PNG (salida)  
- **¿Necesito una licencia para producción?** Sí, se requiere una licencia comercial  
- **¿Puedo establecer la resolución de la imagen?** Sí, usando `PngSaveOptions.setResolution()`  
- **¿Es posible seleccionar páginas específicas?** Absolutamente – proporcione los números de página en el objeto de opciones  

## ¿Por qué convertir XPS a PNG?
Renderizar XPS a archivos de imagen es útil cuando necesita mostrar documentos en la web, incrustarlos en informes o generar miniaturas para vista previa. PNG ofrece compresión sin pérdida y amplio soporte en navegadores, lo que lo convierte en una opción ideal para representaciones visuales de alta calidad del contenido XPS.

## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de tener los siguientes requisitos configurados:
1. Java Development Kit (JDK): Asegúrese de tener el JDK instalado en su sistema.  
2. Aspose.Page para Java: Descargue e instale la biblioteca Aspose.Page. Puede encontrar el enlace de descarga [aquí](https://releases.aspose.com/page/java/).  
3. Entorno de Desarrollo Integrado (IDE): Elija un IDE compatible con Java como IntelliJ IDEA o Eclipse.  

## Cómo convertir XPS a PNG en Java
A continuación se muestra una guía paso a paso que explica **cómo convertir documentos XPS** en imágenes PNG, incluyendo fragmentos de código que puede copiar directamente a su proyecto.

### Importar paquetes
En su proyecto Java, importe los paquetes necesarios para utilizar las funcionalidades de Aspose.Page. Añada las siguientes sentencias de importación al comienzo de su archivo Java:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

### Paso 1: Establecer el directorio del documento
Defina la carpeta que contiene su archivo XPS de origen y donde se guardarán los archivos PNG.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Paso 2: Cargar el documento XPS
Cree una instancia de `XpsDocument` que cargue el archivo XPS de origen.

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Paso 3: Inicializar opciones
Configure las opciones de salida PNG. Aquí puede establecer suavizado, resolución y especificar qué páginas renderizar.

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Paso 4: Crear el dispositivo de renderizado
Cree un `ImageDevice` que contendrá los datos de la imagen renderizada.

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

### Paso 5: Guardar e iterar
Renderice el documento XPS y luego escriba cada matriz de bytes PNG generada en un archivo en disco.

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

Al seguir estos pasos, podrá **renderizar XPS a archivos de imagen** en formato PNG usando Aspose.Page para Java de manera sencilla.

## Conclusión
En conclusión, Aspose.Page para Java simplifica el proceso de conversión de XPS a PNG, proporcionando a los desarrolladores una herramienta fiable y eficiente. Incorpore esta biblioteca en sus proyectos Java para optimizar las tareas de manipulación de documentos.

## Preguntas frecuentes adicionales

**P: ¿Puedo convertir solo páginas seleccionadas de un archivo XPS?**  
R: Absolutamente. Use el método `setPageNumbers` en `PngSaveOptions` para especificar las páginas que desea renderizar.

**P: ¿Qué resolución de imagen se recomienda para PNG de alta calidad?**  
R: Una resolución de 300 dpi es un buen equilibrio entre calidad y tamaño de archivo, pero puede ajustarla mediante `options.setResolution()`.

**P: ¿La API admite conversión multihilo para documentos grandes?**  
R: Sí, puede invocar la lógica de conversión en hilos paralelos, cada uno manejando una página diferente o una partición del documento.

**P: ¿Cómo manejo el uso de memoria al convertir archivos XPS muy grandes?**  
R: Procese las páginas secuencialmente y libere el `FileOutputStream` después de cada escritura, como se muestra en el código de ejemplo.

**P: ¿Existe una forma de agregar metadatos personalizados a los archivos PNG generados?**  
R: Aunque `PngSaveOptions` no expone directamente campos de metadatos, puede post‑procesar el PNG usando bibliotecas de imágenes estándar para incrustar metadatos.

---

**Última actualización:** 2025-12-23  
**Probado con:** Aspose.Page para Java 24.12 (última)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}