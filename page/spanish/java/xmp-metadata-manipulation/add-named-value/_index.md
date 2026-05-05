---
date: 2026-05-05
description: 'Aprende a agregar valores nombrados XMP a archivos EPS usando Aspose.Page
  para Java: una guía paso a paso con ejemplos de código.'
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
linktitle: Añadir valor nombrado en XMP usando Java
second_title: Aspose.Page Java API
title: Cómo añadir un valor nombrado XMP en archivos EPS usando Java
url: /es/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar Valor Nombrado en Metadatos XMP usando Java

## Introducción
En el desarrollo moderno de Java, aprender **cómo agregar XMP** metadata dentro de archivos EPS es esencial para preservar la procedencia del documento y mejorar la capacidad de búsqueda. Con **asp** (Aspose.Page for Java), puedes inyectar sin esfuerzo valores nombrados personalizados en el paquete XMP. Este tutorial te guía paso a paso—con fragmentos de código—para que puedas comenzar a agregar metadata XMP a tus documentos EPS hoy mismo.

## Respuestas Rápidas
- **¿Qué biblioteca se necesita?** Aspose.Page for Java (asp)  
- **¿Qué tipo de archivo es el objetivo?** EPS files containing XMP metadata  
- **¿Caso de uso principal?** Add custom named values (e.g., page size limits) to XMP  
- **¿Requisitos previos?** JDK 8+ and the Aspose.Page for Java library  
- **¿Tiempo típico de implementación?** 5–10 minutes once the library is set up  

## ¿Qué es asp?
*asp* es la forma corta de **Aspose**, una familia de APIs .NET y Java que simplifican el procesamiento de documentos. El componente Aspose.Page for Java te permite crear, editar y convertir archivos PostScript y EPS mientras brinda acceso programático completo a sus metadatos, incluido XMP.

## ¿Por qué agregar valores nombrados a los metadatos XMP?
- **Amigable para motores de búsqueda:** Custom tags improve discoverability.  
- **Automatización de flujo de trabajo:** Downstream tools can read your custom values to make decisions.  
- **Cumplimiento:** Embed regulatory information directly into the document package.  

## Por Qué Esto Importa
Agregar valores nombrados a XMP te permite almacenar pares clave‑valor arbitrarios que pueden leerse sin analizar todo el archivo EPS. Esta capacidad es especialmente valiosa en pipelines de publicación automatizada, sistemas de gestión de activos digitales y flujos de trabajo impulsados por cumplimiento donde los metadatos dirigen acciones posteriores.

## Requisitos Previos
Antes de comenzar, asegúrate de contar con lo siguiente:

- **Java Development Kit (JDK):** A recent JDK (8 or higher) installed on your machine.  
- **Aspose.Page for Java Library:** Download it from the official [download link](https://releases.aspose.com/page/java/). Add the JAR to your project’s classpath.  
- **Un archivo EPS** that either already contains XMP metadata or will have it generated automatically.

## Importar Paquetes
Comienza importando los paquetes Java necesarios. Estas importaciones te dan acceso a flujos de archivos, al modelo de documento EPS y a las clases de manejo de XMP.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Cómo Agregar un Valor Nombrado XMP en Archivos EPS Usando Java
A continuación se muestra una guía concisa, numerada, que indica exactamente **cómo agregar XMP** valores nombrados a un documento EPS.

### Paso 1: Inicializar el Flujo de Archivo EPS de Entrada
Carga el archivo EPS de origen en un `FileInputStream`. Este flujo alimenta el documento a la API de Aspose.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Consejo profesional:** Mantenga la variable `dataDir` configurable para que el mismo código funcione en diferentes entornos.

### Paso 2: Obtener Metadatos XMP
Recupera el paquete XMP existente. Si el archivo EPS no tiene uno, Aspose crea un nuevo objeto XMP poblado a partir de los comentarios PS.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Paso 3: Agregar Valor Nombrado
Inserta un valor nombrado personalizado en la estructura XMP. En este ejemplo añadimos una nueva clave bajo el espacio de nombres `xmpTPg:MaxPageSize`.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Por qué esto importa:** Los valores nombrados te permiten almacenar pares clave‑valor arbitrarios que las aplicaciones posteriores pueden leer sin analizar todo el documento.

### Paso 4: Inicializar el Flujo de Archivo EPS de Salida
Prepara un `FileOutputStream` donde se guardará el EPS modificado.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Paso 5: Guardar el Documento
Persistir los cambios. La llamada `save` escribe el paquete XMP actualizado de nuevo en el archivo EPS.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Paso 6: Cerrar el Flujo de Archivo EPS de Entrada
Libera el manejador del archivo original para evitar fugas de recursos.

```java
psStream.close();
```

Al seguir estos seis pasos, has **agregado exitosamente un valor nombrado en los metadatos XMP** usando **asp** (Aspose.Page for Java).

## Problemas Comunes y Soluciones
| Problema | Causa | Solución |
|----------|-------|----------|
| `NullPointerException` on `xmp` | El archivo EPS no tiene XMP y Aspose no pudo generar uno | Asegúrese de que el EPS contenga al menos un comentario PS o cree manualmente una nueva instancia `XmpMetadata`. |
| Output file is empty | El flujo de salida no se vació/cerró | Verifique que `outPsStream.close()` se llame en un bloque `finally` (como se muestra). |
| Duplicate key error | Se agregó el mismo valor nombrado dos veces | Compruebe si la clave ya existe con `xmp.containsNamedValue(...)` antes de agregarla. |

## Preguntas Frecuentes

**Q: ¿Puedo usar Aspose.Page for Java con otras bibliotecas Java?**  
A: Sí, Aspose.Page for Java está diseñado para trabajar sin problemas con otras bibliotecas Java, proporcionando flexibilidad en tu entorno de desarrollo.

**Q: ¿Hay una versión de prueba gratuita disponible para Aspose.Page for Java?**  
A: Sí, puedes acceder a una prueba gratuita de Aspose.Page for Java [aquí](https://releases.aspose.com/).

**Q: ¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?**  
A: Visita [este enlace](https://purchase.aspose.com/temporary-license/) para obtener una licencia temporal para Aspose.Page for Java.

**Q: ¿Dónde puedo encontrar más tutoriales y ejemplos para Aspose.Page for Java?**  
A: Explora la [documentación](https://reference.aspose.com/page/java/) para tutoriales y ejemplos completos.

**Q: ¿Aspose.Page for Java es adecuado para proyectos a gran escala?**  
A: Absolutamente, Aspose.Page for Java está diseñado para manejar proyectos a gran escala de manera eficiente, ofreciendo capacidades robustas de manipulación de documentos.

## Conclusión
En esta guía demostramos cómo **asp** (Aspose.Page for Java) facilita **agregar valores nombrados a los metadatos XMP** dentro de archivos EPS. Con los pasos anteriores, puedes enriquecer tus documentos con metadata personalizada, mejorar la capacidad de búsqueda y habilitar un procesamiento posterior más inteligente.

---

**Última actualización:** 2026-05-05  
**Probado con:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}