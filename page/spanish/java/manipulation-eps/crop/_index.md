---
date: 2025-11-30
description: 'Aprende a recortar archivos EPS en Java con Aspose.Page: un tutorial
  claro, paso a paso, sobre cómo recortar EPS usando la biblioteca Aspose.Page.'
linktitle: Crop EPS File in Java
second_title: Aspose.Page Java API
title: Cómo recortar archivos EPS en Java – Guía de Aspose.Page
url: /es/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo recortar archivos EPS en Java – Guía paso a paso con Aspose.Page

## Introducción
Si necesitas **cómo recortar eps** archivos de forma programática en una aplicación Java, has llegado al lugar correcto. En este tutorial recorreremos todo el proceso de recortar una imagen EPS usando la potente biblioteca Aspose.Page para Java. Al final de la guía comprenderás por qué el recorte de EPS es importante, verás el código exacto que necesitas y estarás listo para integrar la solución en tus propios proyectos.

## Respuestas rápidas
- **¿Qué biblioteca maneja el recorte de EPS en Java?** Aspose.Page for Java.  
- **¿Cuánto tiempo lleva implementar un recorte básico?** Aproximadamente 5‑10 minutos.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para evaluación; se requiere una licencia comercial para producción.  
- **¿Qué versiones de Java son compatibles?** Java 8 y posteriores.  
- **¿Puedo definir cualquier cuadro delimitador personalizado?** Sí – proporcionas las coordenadas que necesites.

## ¿Qué es el recorte de EPS y por qué usarlo?
Encapsulated PostScript (EPS) es un formato gráfico que almacena imágenes vectoriales junto con un cuadro delimitador que define el área visible. Recortar un archivo EPS significa crear un nuevo cuadro delimitador de modo que solo se conserve la región que te interesa. Esto es útil cuando deseas eliminar márgenes blancos, extraer un logotipo o ajustar el gráfico a un diseño más ajustado sin volver a crear el archivo original.

## Requisitos previos
Antes de sumergirnos en el código, asegúrate de tener:

- Biblioteca **Aspose.Page for Java** instalada – descárgala desde la página oficial [aquí](https://releases.aspose.com/page/java/).  
- **Java Development Kit (JDK)** 8 o posterior instalado en tu máquina.  
- **Una carpeta** para almacenar tu EPS de entrada (`input.eps`) y el archivo recortado resultante (`output_crop.eps`).

## Importar paquetes
Primero, importa las clases Java necesarias. Este fragmento permanece exactamente igual que en el tutorial original:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

### Paso 1: Establecer el directorio del documento y el flujo de entrada
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
Aquí indicamos al código la carpeta que contiene nuestro archivo EPS fuente y abrimos un flujo para leerlo.

### Paso 2: Inicializar el objeto PsDocument
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
La clase `PsDocument` representa el documento EPS en memoria, permitiéndonos consultar y manipular sus propiedades.

### Paso 3: Extraer el cuadro delimitador inicial
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
Extraer el cuadro delimitador original te brinda las coordenadas del área visible actual, lo cual es útil para decidir cuánto necesitas recortar.

### Paso 4: Crear el flujo de salida
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
Abrimos un flujo donde se escribirá el EPS recortado.

### Paso 5: Definir nuevo cuadro delimitador y recortar
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
Proporciona las cuatro coordenadas (x inferior‑izquierda, y inferior‑izquierda, x superior‑derecha, y superior‑derecha) que definen el área que deseas conservar. El método `cropEps` realiza el recorte y escribe el resultado en `output_crop.eps`.

## Problemas comunes y soluciones
- **Coordenadas incorrectas:** EPS usa puntos (1/72 pulgada). Si el recorte se ve desalineado, verifica la conversión de unidades.  
- **Errores de archivo no encontrado:** Asegúrate de que `dataDir` termine con el separador de ruta apropiado (`/` o `\`).  
- **Excepciones de licencia:** Ejecutar el código sin una licencia válida puede añadir una marca de agua al resultado. Aplica tu licencia temporal o permanente antes de usarlo en producción.

## Preguntas frecuentes

**P: ¿Aspose.Page es compatible con Java 8?**  
R: Sí, Aspose.Page funciona con Java 8 y cualquier versión posterior.

**P: ¿Puedo usar Aspose.Page en proyectos comerciales?**  
R: Absolutamente. Se requiere una licencia comercial para despliegues en producción. Puedes obtener una [aquí](https://purchase.aspose.com/buy).

**P: ¿Dónde puedo encontrar recursos adicionales y soporte de la comunidad?**  
R: Visita el foro oficial de [Aspose.Page](https://forum.aspose.com/c/page/39) para discusiones, ejemplos de código y consejos de solución de problemas.

**P: ¿Hay una prueba gratuita disponible para pruebas?**  
R: Sí, puedes descargar una prueba gratuita de Aspose.Page desde la página de lanzamientos [aquí](https://releases.aspose.com/).

**P: ¿Cómo obtengo una licencia temporal para evaluación a corto plazo?**  
R: Una licencia temporal puede solicitarse desde el portal de licencias [aquí](https://purchase.aspose.com/temporary-license/).

## Conclusión
Ahora sabes **cómo recortar eps** archivos en Java usando Aspose.Page. Definiendo un cuadro delimitador personalizado e invocando `cropEps`, puedes eliminar márgenes no deseados o aislar partes específicas de un gráfico EPS con solo unas pocas líneas de código. Integra este fragmento en tus flujos de procesamiento de documentos más amplios para automatizar la manipulación de EPS y mantener tus recursos visuales ordenados.

---

**Última actualización:** 2025-11-30  
**Probado con:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}