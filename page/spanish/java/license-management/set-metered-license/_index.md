---
date: 2025-12-03
description: Aprenda a guardar EPS como PNG usando Aspose.Page para Java mientras
  configura una licencia medida. Guía paso a paso con ejemplo de código completo.
language: es
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Guardar EPS como PNG con Aspose.Page Java (licencia medida)
url: /java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Guardar EPS como PNG con Aspose.Page Java (Licencia Métrica)

## Introducción
Si necesitas **guardar EPS como PNG** en una aplicación Java y deseas una forma sin complicaciones de gestionar la licencia, estás en el lugar correcto. Este tutorial te guía a través de la configuración de una licencia por métricas para Aspose.Page, la carga de un archivo PostScript (EPS) y su conversión a una imagen PNG, todo con pasos claros y concisos que puedes seguir de inmediato.

## Respuestas rápidas
- **¿Qué significa “guardar EPS como PNG”?** Convierte un archivo EPS vectorial en una imagen PNG rasterizada.  
- **¿Por qué usar una licencia por métricas?** Te permite pagar solo por las páginas que procesas, ideal para cargas de trabajo variables.  
- **¿Necesito una conexión a internet?** No, las claves métricas se validan localmente.  
- **¿Qué versión de Java se requiere?** Java 8 o superior.  
- **¿Cuánto tiempo lleva la configuración?** Aproximadamente 10 minutos para una implementación básica.

## Qué es “guardar EPS como PNG”
Guardar EPS como PNG transforma un documento Encapsulated PostScript escalable en un formato de mapa de bits ampliamente compatible. PNG conserva la transparencia y ofrece compresión sin pérdida, lo que lo hace ideal para gráficos web, miniaturas y vistas previas de impresión.

## ¿Por qué usar Aspose.Page para esta tarea?
- **Pure Java API** – sin dependencias nativas.  
- **High fidelity** – los gráficos vectoriales se renderizan con precisión.  
- **Metered licensing** – solo pagas por lo que conviertes.  
- **Support for multiple output formats** – PNG, JPEG, TIFF, etc.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

- Conocimientos básicos de programación Java.  
- Biblioteca Aspose.Page instalada – descárgala desde [here](https://releases.aspose.com/page/java/).  
- Claves públicas y privadas métricas, que puedes obtener a través de tu cuenta Aspose.

## Importar paquetes
Primero, importa las clases que necesitaremos. Mantén el bloque de importación exactamente como se muestra para que el código compile sin cambios.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Paso 1: Inicializar el documento y el formato de imagen
Aquí establecemos las claves métricas y definimos el formato de salida (PNG). Esta es la base para la operación **guardar EPS como PNG**.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

## Paso 2: Inicializar el flujo de entrada PostScript
Abre el archivo EPS que deseas convertir. El flujo alimenta el documento en Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## Paso 3: Verificar la licencia del documento
Siempre verifica que la licencia métrica se haya aplicado correctamente antes de procesar.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## Paso 4: Inicializar opciones y dispositivo de imagen
Crea el objeto de opciones que controla la configuración de conversión y el dispositivo que recibirá la imagen renderizada.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## Paso 5: Guardar el archivo EPS como imagen
Esta es la llamada central **guardar EPS como PNG**. El documento se renderiza en el dispositivo de imagen usando las opciones que configuramos.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## Paso 6: Obtener y guardar los bytes de la imagen
Extrae los bytes PNG del dispositivo y escríbelos en un archivo en disco.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Problemas comunes y soluciones
| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| **Licencia no reconocida** | Las claves son incorrectas o están en el orden equivocado. | Verifica nuevamente las cadenas de claves públicas/privadas y asegúrate de que `setMeteredKey` se llame antes de cualquier procesamiento del documento. |
| **El archivo de salida está vacío** | `device.getImagesBytes()` devolvió `null`. | Verifica que el archivo EPS sea válido y que `ImageSaveOptions` no esté configurado con un lienzo de tamaño cero. |
| **OutOfMemoryError en EPS grande** | Renderizar archivos vectoriales grandes consume mucha memoria. | Procesa las páginas una a una o aumenta el heap de JVM (`-Xmx2g`). |

## Preguntas frecuentes

**Q: ¿Cómo obtengo las claves públicas y privadas métricas?**  
A: Puedes obtener estas claves a través de tu cuenta Aspose.

**Q: ¿La biblioteca Aspose.Page es gratuita?**  
A: Aspose.Page ofrece versiones de prueba gratuitas y versiones de pago. Visita [here](https://releases.aspose.com/) para una prueba gratuita.

**Q: ¿Puedo usar Aspose.Page en proyectos comerciales?**  
A: Sí, Aspose.Page ofrece licencias comerciales. Puedes adquirirlas [here](https://purchase.aspose.com/buy).

**Q: ¿Dónde puedo encontrar documentación adicional?**  
A: Consulta la documentación [here](https://reference.aspose.com/page/java/).

**Q: ¿Cómo puedo obtener licencias temporales?**  
A: Las licencias temporales pueden obtenerse [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2025-12-03  
**Probado con:** Aspose.Page 24.12 for Java  
**Autor:** Aspose  

---