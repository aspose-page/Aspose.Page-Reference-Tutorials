---
date: 2026-05-25
description: Scopri come leggere XMP usando Aspose.Page con Java. Questa guida passo‑passo
  mostra come estrarre i metadati XMP, le informazioni sul creatore, i timestamp,
  le miniature e altro ancora.
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: Come leggere i metadati XMP usando Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: Leggi XMP usando Aspose.Page – Guida Java
url: /it/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ottieni metadati da XMP usando Java

## Come leggere XMP usando Aspose.Page (Java)?

Carica il file EPS con `new Document("file.eps")` — la classe `Document` rappresenta un file caricato. Chiama `getXmpMetadata()`, che estrae il pacchetto XMP, e poi interroga l'oggetto `XmpMetadata` restituito — un'interfaccia simile a una mappa per le proprietà XMP — per recuperare le chiavi di cui hai bisogno. Questo è tutto ciò che serve per leggere XMP usando Aspose.Page. L'API astrae l'analisi a basso livello, così ottieni una mappa di proprietà pronta all'uso in sole due righe di codice.

Benvenuti al nostro tutorial passo‑passo che mostra **come leggere i metadati XMP** con Java e la libreria Aspose.Page. XMP (Extensible Metadata Platform) è uno standard ampiamente adottato per incorporare metadati ricchi all'interno dei documenti. Alla fine di questa guida sarai in grado di leggere l'XMP del formato del documento, estrarre le informazioni sul creatore, i timestamp, le miniature e altro — consentendoti di creare soluzioni di analisi dei documenti più intelligenti.

## Risposte rapide
- **Cosa significa “leggere XMP”?** Significa estrarre programmaticamente il pacchetto XMP che memorizza i metadati all'interno di un file.  
- **Quale libreria è necessaria?** Aspose.Page per Java (scarica dalla pagina ufficiale [qui](https://releases.aspose.com/page/java/)).  
- **Ho bisogno di una licenza?** È necessaria una licenza temporanea o completa per la produzione; una prova gratuita è sufficiente per la valutazione.  
- **Quale versione di Java è supportata?** Java 8 o superiore.  
- **Posso leggere XMP da altri formati?** Sì – Aspose.Page estrae XMP da EPS, PDF, JPEG, PNG e oltre 20 altri formati.

## Prerequisiti
Prima di immergerti nel codice, assicurati di avere:

- **Java Development Kit (JDK)** – Java 8+ installato e configurato sulla tua macchina.  
- **Aspose.Page per Java** – Scarica la libreria dal sito ufficiale [qui](https://releases.aspose.com/page/java/).  
- Un file EPS che contiene metadati XMP (ad es., `xmp1.eps`).  

## Importa pacchetti
La classe `XmpMetadata` si trova nello spazio dei nomi `com.aspose.page.xmp`, mentre la classe `Document` è in `com.aspose.page`. Importa entrambe così potrai lavorare con il file EPS e i suoi metadati.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Passo 1: Inizializza lo stream del file EPS di input
Inizia impostando il percorso della tua directory dei documenti e inizializzando lo stream del file EPS di input.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Passo 2: Ottieni i metadati XMP
`XmpMetadata` è l'oggetto di Aspose.Page che contiene il pacchetto XMP estratto da un documento. Recuperalo con `document.getXmpMetadata()`. Se il file non contiene XMP, l'API sintetizza un pacchetto minimo dai commenti PostScript esistenti.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Passo 3: Estrai le informazioni CreatorTool
La chiave `CreatorTool` si trova nello spazio dei nomi `xmp` e registra l'applicazione che ha generato il file. Verifica la sua presenza e stampa il valore.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Passo 4: Estrai le informazioni CreateDate
`CreateDate` memorizza il timestamp di quando il documento è stato originariamente creato. Usa lo stesso schema `containsKey`/`get` per leggerlo.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Passo 5: Recupera la larghezza della miniatura
Se le miniature esistono, l'array `xmp:Thumbnails` contiene una o più voci. Ogni voce contiene `width`, `height` e dati binari. L'esempio estrae la larghezza della prima miniatura.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Passo 6: Estrai le informazioni sul formato
La chiave `format` indica il formato originale del file (ad es., “application/postscript”). Questo è utile quando devi registrare o convalidare i tipi di origine.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Passo 7: Ottieni DocumentID
`DocumentID` è un identificatore unico assegnato dall'applicazione creatrice. Può essere usato per la deduplicazione in grandi librerie di risorse.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Perché è importante
Aspose.Page può leggere XMP da **oltre 20** formati di file e processa documenti fino a **500 MB** senza caricare l'intero file in memoria, fornendoti un accesso rapido e a basso overhead ai metadati essenziali. Questa capacità è fondamentale per pipeline di elaborazione batch, sistemi di gestione delle risorse digitali e qualsiasi soluzione che si basi su attributi di documento ricercabili e leggibili da macchine.

## Problemi comuni e consigli
- **XMP mancante:** Alcuni file EPS potrebbero non contenere XMP. La chiamata `getXmpMetadata()` sintetizzerà un set minimo basato sui commenti PS esistenti, ma non otterrai metadati completi a meno che non siano incorporati.  
- **Array di miniature:** La chiave `xmp:Thumbnails` può contenere più voci. L'esempio estrae solo la prima; itera l'array se ti servono tutte le miniature.  
- **Consapevolezza dei namespace:** Le chiavi XMP usano namespace (es., `xmp:`, `dc:`). Assicurati di fare riferimento al nome esatto della chiave; altrimenti `containsKey` restituirà false.  

## Domande frequenti
### Posso usare Aspose.Page per Java con altri linguaggi di programmazione?
Sì, Aspose.Page supporta Java, .NET e diversi altri linguaggi. Vedi l'elenco completo nella [documentazione](https://reference.aspose.com/page/java/).

### È disponibile una prova gratuita per Aspose.Page per Java?
Sì, puoi accedere alla prova gratuita [qui](https://releases.aspose.com/).

### Dove posso trovare supporto per Aspose.Page per Java?
Visita il [forum Aspose.Page](https://forum.aspose.com/c/page/39) per assistenza della community e supporto ufficiale.

### Come posso ottenere una licenza temporanea per Aspose.Page per Java?
Puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

### Ci sono risorse aggiuntive per Aspose.Page per Java?
Esplora la [documentazione](https://reference.aspose.com/page/java/) completa e scarica la libreria [qui](https://releases.aspose.com/page/java/).

## FAQ aggiuntive
**Q: Questo approccio funziona con file PDF che contengono XMP?**  
A: Sì, Aspose.Page può leggere XMP da PDF, EPS e diversi formati immagine.

**Q: Posso modificare i metadati XMP dopo averli letti?**  
A: Assolutamente. L'oggetto `XmpMetadata` è modificabile; puoi aggiungere, aggiornare o rimuovere chiavi e poi salvare il documento.

**Q: Esiste un modo per estrarre tutte le immagini miniature, non solo le dimensioni?**  
A: Puoi recuperare i dati binari dalla proprietà `xmpGImg:data` di ogni voce di miniatura e scriverli su un file.

## Conclusione
Ora hai padroneggiato **come leggere i metadati XMP** usando Java e Aspose.Page. Seguendo questi passaggi puoi estrarre gli strumenti del creatore, i timestamp, le miniature, le informazioni sul formato e gli ID del documento — offrendoti una visione completa dei metadati incorporati nei tuoi file EPS. Sentiti libero di sperimentare con namespace XMP aggiuntivi per ottenere dati ancora più ricchi per le tue applicazioni.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose

## Tutorial correlati

- [Aspose Page Java Tutorial – Aggiungi metadati XMP ai file EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page xmp tutorial – Aggiungi namespace in XMP usando Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [aspose page xmp tutorial – Modifica valore nominato in XMP usando Java](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}