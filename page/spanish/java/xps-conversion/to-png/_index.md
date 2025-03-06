---
title: Convertir XPS a PNG en Java
linktitle: Convertir XPS a PNG en Java
second_title: API de Java de Aspose.Page
description: Convierta XPS a PNG sin esfuerzo en Java usando Aspose.Page. Optimice las tareas de documentos con esta solución confiable y fácil de usar para desarrolladores.
weight: 13
url: /es/java/xps-conversion/to-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir XPS a PNG en Java

## Introducción
En el dinámico mundo del desarrollo de software, surge con frecuencia la necesidad de convertir documentos XPS (Especificación de papel XML) a imágenes PNG (Portable Network Graphics). Para realizar esta tarea sin problemas en Java, Aspose.Page proporciona una solución poderosa. En este tutorial, recorreremos el proceso de conversión de XPS a PNG usando Aspose.Page para Java.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de tener configurados los siguientes requisitos previos:
1. Kit de desarrollo de Java (JDK): asegúrese de tener JDK instalado en su sistema.
2.  Aspose.Page para Java: descargue e instale la biblioteca Aspose.Page. Puedes encontrar el enlace de descarga.[aquí](https://releases.aspose.com/page/java/).
3. Entorno de desarrollo integrado (IDE): elija un IDE compatible con Java como IntelliJ IDEA o Eclipse.
## Importar paquetes
En su proyecto Java, importe los paquetes necesarios para utilizar las funcionalidades de Aspose.Page. Agregue las siguientes declaraciones de importación al comienzo de su archivo Java:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Paso 1: configurar el directorio de documentos
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
```
## Paso 2: cargar el documento XPS
```java
// Cargar documento XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Paso 3: inicializar opciones
```java
// Inicialice el objeto de opciones con los parámetros necesarios.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Paso 4: crear un dispositivo de renderizado
```java
// Crear dispositivo de renderizado para formato PDF
ImageDevice device = new ImageDevice();
```
## Paso 5: guardar e iterar
```java
// Guarde el documento XPS en PNG usando las opciones y el dispositivo
document.save(device, options);
//Iterar a través de particiones de documentos (documentos fijos, en términos XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterar a través de páginas de partición
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Inicializar flujo de salida de imagen
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Escribir imagen
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Cerrar la transmisión
        imageStream.close();
    }
}
```
Siguiendo estos pasos, puede convertir fácilmente documentos XPS a imágenes PNG utilizando Aspose.Page para Java.
## Conclusión
En conclusión, Aspose.Page para Java simplifica el proceso de conversión de XPS a PNG, proporcionando a los desarrolladores una herramienta confiable y eficiente. Incorpore esta biblioteca en sus proyectos Java para agilizar las tareas de manipulación de documentos.
## Preguntas frecuentes
### ¿Puedo utilizar Aspose.Page para Java en proyectos comerciales?
 Sí, Aspose.Page es un producto comercial. Puede encontrar información sobre licencias.[aquí](https://purchase.aspose.com/buy).
### ¿Hay una prueba gratuita disponible?
 Sí, puedes explorar una prueba gratuita.[aquí](https://releases.aspose.com/).
### ¿Dónde puedo encontrar la documentación de Aspose.Page para Java?
 La documentación completa está disponible.[aquí](https://reference.aspose.com/page/java/).
### ¿Cómo obtengo una licencia temporal para realizar pruebas?
 Puedes obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Existen foros comunitarios para discusiones sobre Aspose.Page?
 Sí, visita los foros de la comunidad.[aquí](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
