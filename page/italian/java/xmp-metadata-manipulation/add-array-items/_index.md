---
date: 2026-03-05
description: Scopri come aggiungere elementi dell'array dc:title nei metadati XMP
  dei file EPS usando Aspose.Page per Java. Segui questa guida passo passo per risultati
  rapidi.
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Come aggiungere elementi dell'array dc:title nei metadati XMP usando Java
url: /it/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere elementi di array nei metadati XMP usando Java

## Introduzione
In questo tutorial scoprirai **come aggiungere dc:title** (e altri elementi di array) ai metadati XMP all'interno di un file EPS con Aspose.Page for Java. Aggiornare i metadati XMP è utile quando è necessario incorporare informazioni ricercabili — come titoli, autori o parole chiave — direttamente nei tuoi file grafici. Ti guideremo passo passo, spiegheremo perché ogni riga è importante e ti mostreremo come verificare le modifiche.

## Risposte rapide
- **Cosa rappresenta “dc:title”?** È la proprietà titolo di Dublin Core memorizzata come un array XMP.  
- **Perché modificare i metadati XMP?** Consente una migliore gestione delle risorse, ricercabilità e conformità agli standard.  
- **È necessario un blocco XMP esistente?** No — Aspose.Page ne genererà uno dai commenti PS se mancante.  
- **Quale versione della libreria è richiesta?** Qualsiasi versione recente di Aspose.Page for Java (testata con l'ultima build 2026).  
- **Posso aggiungere altre proprietà di array?** Sì — usa lo stesso metodo `addArrayItem` per proprietà come `dc:creator`.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Libreria Aspose.Page for Java installata (aggiungi il JAR al classpath del tuo progetto).  
- Esperienza di base nello sviluppo Java (JDK 8+ consigliato).  
- Un file EPS che contenga già metadati XMP o almeno commenti di metadati PS (ad esempio `%%Title`, `%%Creator`).  

## Importare i pacchetti
Per iniziare, importa le classi necessarie per leggere, manipolare e salvare file EPS:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Passo 1: Caricare il documento EPS e recuperare i metadati XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Qui apriamo il file EPS e chiediamo ad Aspose.Page il suo blocco XMP. Se il file non contiene XMP, la libreria lo crea automaticamente usando i commenti PS esistenti, garantendo di avere sempre un contenitore di metadati con cui lavorare.

## Passo 2: Aggiungere un nuovo elemento di array **dc:title**
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

Questa riga dimostra **come aggiungere dc:title**. Sostituisci `"NewTitle"` con il titolo effettivo che desideri incorporare. Il metodo aggiunge il valore all'array di titoli esistente, preservando eventuali titoli precedenti.

## Passo 3: Aggiungere un nuovo elemento di array **dc:creator**
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

Allo stesso modo, puoi arricchire la proprietà `dc:creator`. È possibile memorizzare più autori; ogni chiamata aggiunge una nuova voce.

## Passo 4: Preparare lo stream di output
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

Creiamo uno stream per il file EPS modificato. Usare un nome file diverso (`xmp3_changed.eps`) mantiene intatto il file originale.

## Passo 5: Salvare il documento con i metadati XMP aggiornati
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

La chiamata `save` scrive i dati EPS insieme al blocco XMP aggiornato. Il blocco `finally` garantisce che il gestore del file venga rilasciato anche in caso di eccezione.

## Perché è importante
Incorporare valori accurati di `dc:title` e `dc:creator` migliora:

- **Ricercabilità** nei sistemi di gestione delle risorse digitali (DAM).  
- **Conformità** agli standard editoriali che richiedono metadati.  
- **Collaborazione**, poiché i colleghi possono identificare rapidamente il contenuto del file senza aprire l'EPS.

## Problemi comuni e consigli
- **Problema:** Sovrascrivere involontariamente gli elementi di array esistenti.  
  **Consiglio:** Usa `xmp.getArrayItems("dc:title")` per ispezionare i valori attuali prima di aggiungere nuovi elementi.  
- **Problema:** Dimenticare di chiudere gli stream, causando blocchi dei file.  
  **Consiglio:** Avvolgi sempre I/O in try‑with‑resources o in un blocco `finally` come mostrato.  
- **Consiglio:** Puoi concatenare più chiamate `addArrayItem` per aggiungere diversi titoli o autori in un'unica operazione.

## Domande frequenti

### Posso usare Aspose.Page for Java con altri formati di documento?
Sì, Aspose.Page supporta vari formati di documento, tra cui EPS, PDF e XPS.

### È disponibile una versione di prova gratuita per Aspose.Page for Java?
Sì, puoi accedere alla versione di prova gratuita [qui](https://releases.aspose.com/).

### Dove posso trovare la documentazione per Aspose.Page for Java?
La documentazione è disponibile [qui](https://reference.aspose.com/page/java/).

### Come posso acquistare Aspose.Page for Java?
Puoi acquistare il prodotto [qui](https://purchase.aspose.com/buy).

### Sono disponibili licenze temporanee per Aspose.Page for Java?
Sì, puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Page for Java (latest 2026 release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}