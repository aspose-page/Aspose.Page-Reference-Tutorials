---
date: 2025-12-21
description: Aprende a modificar XMP en documentos EPS con Aspose.Page y Java. Mejora
  los metadatos rápidamente con Aspose.Page para Java.
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page modificar xmp – Cambiar valores en XMP usando Java
url: /es/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cambiar valores en XMP usando Java

## Introducción
Si necesita **aspose.page modify xmp** datos dentro de un archivo EPS, ha llegado al lugar correcto. En este tutorial recorreremos los pasos exactos necesarios para leer, actualizar y guardar valores XMP (Extensible Metadata Platform) usando la biblioteca Aspose.Page para Java. Al final, podrá personalizar los metadatos del documento —como creador, título y fecha de modificación— para que coincidan con los requisitos de su proyecto.

## Respuestas rápidas
- **¿Qué hace “aspose.page modify xmp”?** Permite leer y escribir metadatos XMP en archivos EPS a través de la API Java de Aspose.Page.  
- **¿Qué versión de la biblioteca se requiere?** Cualquier versión reciente de Aspose.Page para Java (la API es estable entre versiones).  
- **¿Necesito una licencia para ejecutar el ejemplo?** Una prueba gratuita funciona para evaluación; se requiere una licencia comercial para producción.  
- **¿Puedo cambiar varios campos XMP a la vez?** Sí—llame a `put` para cada campo antes de guardar el documento.  
- **¿Se necesita manejar la zona horaria?** Configurar la zona horaria predeterminada (p. ej., UTC) garantiza valores de fecha consistentes.

## ¿Qué es XMP y por qué modificarlo?
XMP (Extensible Metadata Platform) es una forma estandarizada de incrustar metadatos enriquecidos directamente dentro de archivos como EPS, PDF e imágenes. Actualizar XMP le permite controlar cómo se indexan, muestran y buscan los documentos —algo crucial para la marca, el cumplimiento y la automatización de flujos de trabajo.

## ¿Por qué usar Aspose.Page para Java?
- **API completa** – No necesita herramientas externas; todo se maneja en proceso.  
- **Multiplataforma** – Funciona en cualquier SO que soporte Java.  
- **Sin dependencias nativas** – Implementación pura en Java que simplifica el despliegue.  
- **Soporte robusto** – Maneja tanto bloques XMP existentes como crea nuevos a partir de comentarios PS cuando faltan.

## Requisitos previos
Antes de comenzar este tutorial, asegúrese de contar con los siguientes requisitos:
1. **Entorno de desarrollo Java** – Un JDK (8 o superior) y un IDE o herramienta de compilación de su elección.  
2. **Biblioteca Aspose.Page para Java** – Descargue e instale la biblioteca Aspose.Page para Java. Puede encontrar el paquete necesario [aquí](https://releases.aspose.com/page/java/).

## Importar paquetes
Comience importando los paquetes necesarios en su proyecto Java. Estos paquetes son vitales para interactuar y manipular documentos EPS.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Paso 1: Obtener metadatos XMP
Recupere los metadatos XMP del documento EPS. Si el archivo EPS no contiene metadatos XMP, se creará uno nuevo con valores de los comentarios de metadatos PS como %%Creator, %%CreateDate y %%Title.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Paso 2: Cambiar el valor de "ModifyDate"
Modifique el valor de "ModifyDate" en los metadatos XMP para reflejar la fecha deseada.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Paso 3: Cambiar el valor de "Creator"
Actualice el valor de "Creator" en los metadatos XMP para especificar el creador del documento.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Paso 4: Cambiar el valor de "Title"
Modifique el valor de "Title" en los metadatos XMP para establecer un título apropiado para el documento.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Paso 5: Guardar el documento con los metadatos XMP modificados
Guarde el documento con los metadatos XMP actualizados en un nuevo archivo EPS.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Problemas comunes y soluciones
- **Bloque XMP ausente** – La API crea automáticamente uno a partir de los comentarios PS, pero también puede instanciar manualmente `XmpMetadata` si es necesario.  
- **Desajustes de zona horaria** – Siempre configure `TimeZone.setDefault` antes de crear el objeto `Date` para evitar desplazamientos inesperados.  
- **Errores de acceso a archivos** – Asegúrese de que las rutas de entrada y salida sean correctas y de que su aplicación tenga permisos de lectura/escritura.

## Preguntas frecuentes

**Q: ¿Cómo puedo manejar consideraciones de zona horaria al modificar valores XMP?**  
A: Utilice `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` para garantizar la consistencia en la configuración de la zona horaria.

**Q: ¿Puedo cambiar varios valores XMP en una sola operación?**  
A: Sí, usando el método `put` para cada valor deseado, puede modificar varios valores XMP simultáneamente.

**Q: ¿Dónde puedo encontrar documentación adicional para Aspose.Page para Java?**  
A: Explore la documentación completa [aquí](https://reference.aspose.com/page/java/).

**Q: ¿Hay una prueba gratuita disponible para Aspose.Page para Java?**  
A: Sí, puede acceder a la prueba gratuita [aquí](https://releases.aspose.com/).

**Q: ¿Cómo puedo obtener una licencia temporal para Aspose.Page para Java?**  
A: Obtenga una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

**Q: ¿Modificar XMP afecta el contenido visual del EPS?**  
A: No. Los cambios en XMP son solo de metadatos y no alteran los elementos gráficos del archivo EPS.

**Q: ¿Puedo leer programáticamente los valores actualizados para verificar el cambio?**  
A: Por supuesto—simplemente llame a `xmp.get("dc:creator")` (o la clave correspondiente) después de guardar y antes de cerrar el documento.

## Conclusión
¡Felicidades! Ha navegado con éxito el proceso de **aspose.page modify xmp** valores en documentos EPS usando Aspose.Page para Java. Este tutorial le ha proporcionado el conocimiento para modificar metadatos, asegurando que sus documentos se ajusten a sus requisitos específicos sin problemas.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Última actualización:** 2025-12-21  
**Probado con:** Aspose.Page for Java (latest release)  
**Autor:** Aspose  

---