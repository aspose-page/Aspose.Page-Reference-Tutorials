---
date: 2025-12-21
description: Scopri come leggere i metadati XMP usando Java con Aspose.Page. Questa
  guida passo passo ti mostra come leggere il formato XMP del documento ed estrarre
  le proprietà chiave.
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: Come leggere i metadati XMP con Java – Guida Aspose.Page
url: /it/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ottieni Metadati da XMP usando Java

## Come leggere i metadati XMP usando Java

Benvenuti al nostro tutorial passo‑a‑passo che mostra **come leggere XMP** metadati con Java e la libreria Aspose.Page. XMP (Extensible Metadata Platform) è uno standard ampiamente adottato per incorporare metadati ricchi all'interno dei documenti. Alla fine di questa guida sarete in grado di leggere il formato XMP dei documenti, estrarre le informazioni sul creatore, i timestamp, le miniature e altro ancora—consentendovi di creare soluzioni di analisi dei documenti più intelligenti.

## Risposte rapide
- **Cosa significa “come leggere xmp”?** Si riferisce all'estrazione dei metadati XMP dai file in modo programmatico.  
- **Quale libreria è necessaria?** Aspose.Page per Java (disponibile dalla pagina di download di Aspose).  
- **Ho bisogno di una licenza?** È necessaria una licenza temporanea o completa per l'uso in produzione; è disponibile una prova gratuita.  
- **Quale versione di Java è supportata?** Java 8 o superiore.  
- **Posso leggere XMP da altri formati?** Sì, Aspose.Page può gestire EPS, PDF e diversi tipi di immagine che incorporano XMP.

## Prerequisiti
Prima di immergervi nel codice, assicuratevi di avere:

- **Java Development Kit (JDK)** – Java 8+ installato e configurato sulla vostra macchina.  
- **Aspose.Page per Java** – Scaricate la libreria dal sito ufficiale [qui](https://releases.aspose.com/page/java/).  
- Un file EPS che contiene metadati XMP (ad esempio `xmp1.eps`).  

## Importa pacchetti
Nel vostro progetto Java, importate i pacchetti necessari:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Passo 1: Inizializza lo stream del file EPS di input
Iniziate impostando il percorso della vostra directory dei documenti e inizializzando lo stream del file EPS di input.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Passo 2: Ottieni i metadati XMP
Recuperate i metadati XMP dal file EPS. Se il file non contiene metadati XMP, ne verrà generato uno nuovo con i valori dai commenti di metadati PS.
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Passo 3: Estrai le informazioni CreatorTool
Verificate e stampate il valore "CreatorTool" dai metadati XMP.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Passo 4: Estrai le informazioni CreateDate
Verificate e stampate il valore "CreateDate" dai metadati XMP.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Passo 5: Recupera la larghezza della miniatura
Se esistono miniature, estrarre e stampare la larghezza della prima miniatura.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Passo 6: Estrai le informazioni sul formato
Verificate e stampate il valore "format" dai metadati XMP.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Passo 7: Ottieni il DocumentID
Verificate e stampate il valore "DocumentID" dai metadati XMP.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Perché è importante
Leggere i metadati XMP vi consente di scoprire programmaticamente l'origine, la data di creazione e altri attributi essenziali di un documento senza aprirlo in un visualizzatore. Questo è particolarmente utile per l'elaborazione batch, i sistemi di gestione dei contenuti e le pipeline di asset digitali dove i metadati guidano l'indicizzazione e la ricerca.

## Problemi comuni e consigli
- **XMP mancante:** Alcuni file EPS potrebbero non contenere XMP. La chiamata `getXmpMetadata()` sintetizzerà un set minimo basato sui commenti PS esistenti, ma non otterrete metadati completi a meno che non siano incorporati.  
- **Array di miniature:** La chiave `xmp:Thumbnails` può contenere più voci. L'esempio estrae solo la prima; iterate l'array se avete bisogno di tutte le miniature.  
- **Consapevolezza dei namespace:** Le chiavi XMP usano namespace (ad esempio `xmp:`, `dc:`). Assicuratevi di fare riferimento al nome esatto della chiave; altrimenti `containsKey` restituirà false.

## Domande frequenti
### Posso usare Aspose.Page per Java con altri linguaggi di programmazione?
Sì, Aspose.Page supporta più linguaggi, tra cui Java, .NET e altri. Consultate la [documentazione](https://reference.aspose.com/page/java/) per i dettagli.

### È disponibile una prova gratuita per Aspose.Page per Java?
Sì, potete accedere alla prova gratuita [qui](https://releases.aspose.com/).

### Dove posso trovare supporto per Aspose.Page per Java?
Visitate il [forum Aspose.Page](https://forum.aspose.com/c/page/39) per il supporto della community.

### Come posso ottenere una licenza temporanea per Aspose.Page per Java?
Potete ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

### Ci sono risorse aggiuntive per Aspose.Page per Java?
Esplorate la completa [documentazione](https://reference.aspose.com/page/java/) e scaricate la libreria [qui](https://releases.aspose.com/page/java/).

## FAQ aggiuntive
**D: Questo approccio funziona con file PDF che contengono XMP?**  
**R:** Sì, Aspose.Page può leggere XMP da PDF, EPS e diversi formati immagine.

**D: Posso modificare i metadati XMP dopo averli letti?**  
**R:** Assolutamente. L'oggetto `XmpMetadata` è mutabile; potete aggiungere, aggiornare o rimuovere chiavi e poi salvare il documento.

**D: Esiste un modo per estrarre tutte le immagini miniature, non solo le dimensioni?**  
**R:** Potete recuperare i dati binari dalla proprietà `xmpGImg:data` di ogni voce di miniatura e scriverli su un file.

## Conclusione
Ora avete padroneggiato **come leggere i metadati XMP** usando Java e Aspose.Page. Seguendo questi passaggi potete estrarre gli strumenti del creatore, i timestamp, le miniature, le informazioni sul formato e gli ID dei documenti—ottenendo una visione completa dei metadati incorporati nei vostri file EPS. Sentitevi liberi di sperimentare con namespace XMP aggiuntivi per estrarre dati ancora più ricchi per le vostre applicazioni.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
