---
date: 2025-12-18
description: Scopri come aggiungere metadati inserendo elementi di array nei metadati
  XMP dei file EPS usando Aspose.Page per Java. Segui la nostra guida passo‑passo.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Come aggiungere metadati – Aggiungere elementi di array in XMP (Java)
url: /it/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere elementi di array nei metadati XMP usando Java

## Come aggiungere metadati
Benvenuti alla nostra guida passo‑passo su **come aggiungere metadati** ai file EPS con Aspose.Page per Java. In questo tutorial vi guideremo nell'aggiungere elementi di array ai metadati XMP—una necessità comune quando è necessario arricchire le informazioni del documento, come titoli o autori. Alla fine, comprenderete perché XMP è prezioso, come manipolarlo programmaticamente e come salvare il file EPS aggiornato.

## Risposte rapide
- **Quale libreria viene utilizzata?** Aspose.Page for Java  
- **Quale formato di file è l'obiettivo?** EPS (Encapsulated PostScript)  
- **Posso aggiungere più titoli?** Sì, usa `xmp.addArrayItem("dc:title", ...)` ripetutamente  
- **È necessaria una licenza per la produzione?** Sì, è richiesta una licenza valida di Aspose.Page  
- **Il codice è compatibile con Java 8+?** Assolutamente, funziona con tutte le versioni moderne di Java  

## Prerequisiti
Prima di immergerci nel tutorial, assicuratevi di avere i seguenti prerequisiti:
- Libreria Aspose.Page for Java installata.  
- Conoscenza di base della programmazione Java.  
- Un file EPS valido con metadati XMP esistenti o commenti di metadati PS.

## Importare i pacchetti
Per iniziare, è necessario importare i pacchetti necessari per lavorare con Aspose.Page. Includete le seguenti righe all'inizio del vostro file Java:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Passo 1: Ottenere i metadati XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
In questo passaggio, recuperiamo i metadati XMP esistenti dal file EPS. Se il file EPS non contiene già metadati XMP, Aspose.Page ne genera di nuovi e li popola con i valori provenienti dai commenti di metadati PS.

## Passo 2: Aggiungere l'elemento di array "dc:title"
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Ora aggiungiamo un nuovo elemento di array alla proprietà **dc:title** nei metadati XMP. Sostituite `"NewTitle"` con il titolo desiderato.

## Passo 3: Aggiungere l'elemento di array "dc:creator"
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Allo stesso modo, aggiungiamo un nuovo elemento di array alla proprietà **dc:creator** nei metadati XMP. Sostituite `"NewCreator"` con le informazioni sull'autore desiderate.

## Passo 4: Inizializzare lo stream del file EPS di output
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Preparate lo stream del file EPS di output dove verrà salvato il documento modificato con i metadati XMP aggiornati.

## Passo 5: Salvare il documento con i metadati XMP modificati
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Salvate il documento con i metadati XMP aggiornati nel file EPS di output.

## Conclusione
Congratulazioni! Avete appreso con successo **come aggiungere metadati** inserendo elementi di array nei metadati XMP usando Aspose.Page per Java. Questa potente libreria semplifica il processo di manipolazione dei file EPS e offre funzionalità estese per l'elaborazione dei documenti.

## Domande frequenti

### Posso usare Aspose.Page per Java con altri formati di documento?
Sì, Aspose.Page supporta vari formati di documento, inclusi EPS, PDF e XPS.

### È disponibile una versione di prova gratuita per Aspose.Page per Java?
Sì, potete accedere alla versione di prova gratuita [qui](https://releases.aspose.com/).

### Dove posso trovare la documentazione per Aspose.Page per Java?
La documentazione è disponibile [qui](https://reference.aspose.com/page/java/).

### Come posso acquistare Aspose.Page per Java?
Potete acquistare il prodotto [qui](https://purchase.aspose.com/buy).

### Sono disponibili licenze temporanee per Aspose.Page per Java?
Sì, potete ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

## Altre domande frequenti

**Q: Posso aggiungere più di un elemento di array alla stessa proprietà?**  
**A:** Assolutamente. Chiamate `xmp.addArrayItem` più volte per la stessa proprietà per costruire un elenco di valori.

**Q: Questo approccio funziona con schemi XMP esistenti diversi da Dublin Core?**  
**A:** Sì, potete aggiungere elementi di array a qualsiasi proprietà XMP purché lo spazio dei nomi sia correttamente referenziato.

**Q: Come posso verificare che i metadati siano stati aggiunti correttamente?**  
**A:** Aprite il file EPS risultante in un visualizzatore che supporta XMP (ad esempio Adobe Bridge) o estrarre i metadati programmaticamente usando i metodi di `XmpMetadata`.

---

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}