---
date: 2025-12-21
description: Scopri come Aspose.Page modifica XMP nei documenti EPS usando Java. Migliora
  rapidamente i metadati con Aspose.Page per Java.
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page modifica xmp – Modifica i valori in XMP usando Java
url: /it/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modificare i valori in XMP usando Java

## Introduzione
Se hai bisogno di **aspose.page modify xmp** dati all'interno di un file EPS, sei nel posto giusto. In questo tutorial percorreremo passo passo le operazioni necessarie per leggere, aggiornare e salvare i valori XMP (Extensible Metadata Platform) utilizzando la libreria Aspose.Page per Java. Alla fine, sarai in grado di personalizzare i metadati del documento — come creatore, titolo e data di modifica — per soddisfare i requisiti del tuo progetto.

## Risposte rapide
- **Cosa fa “aspose.page modify xmp”?** Consente di leggere e scrivere metadati XMP nei file EPS tramite l'API Java di Aspose.Page.  
- **Quale versione della libreria è necessaria?** Qualsiasi rilascio recente di Aspose.Page per Java (l'API è stabile tra le versioni).  
- **È necessaria una licenza per eseguire il campione?** Una versione di prova gratuita è sufficiente per la valutazione; è richiesta una licenza commerciale per la produzione.  
- **Posso modificare più campi XMP contemporaneamente?** Sì — chiama `put` per ciascun campo prima di salvare il documento.  
- **È necessario gestire il fuso orario?** Impostare il fuso orario predefinito (ad es. UTC) garantisce valori di data coerenti.

## Cos'è XMP e perché modificarlo?
XMP (Extensible Metadata Platform) è un metodo standardizzato per incorporare metadati ricchi direttamente all'interno di file come EPS, PDF e immagini. Aggiornare XMP ti permette di controllare come i documenti vengono indicizzati, visualizzati e ricercati — fondamentale per branding, conformità e automazione dei flussi di lavoro.

## Perché usare Aspose.Page per Java?
- **API completa** – Nessun bisogno di strumenti esterni; tutto è gestito in‑processo.  
- **Cross‑platform** – Funziona su qualsiasi OS che supporta Java.  
- **Nessuna dipendenza nativa** – Implementazione pura Java che semplifica il deployment.  
- **Supporto robusto** – Gestisce sia blocchi XMP esistenti sia ne crea di nuovi dai commenti PS quando mancanti.

## Prerequisiti
Prima di iniziare questo tutorial, assicurati di avere i seguenti prerequisiti:
1. **Ambiente di sviluppo Java** – Un JDK (8 o successivo) e un IDE o uno strumento di build a tua scelta.  
2. **Libreria Aspose.Page per Java** – Scarica e installa la libreria Aspose.Page per Java. Puoi trovare il pacchetto necessario [qui](https://releases.aspose.com/page/java/).

## Importare i pacchetti
Inizia importando i pacchetti richiesti nel tuo progetto Java. Questi pacchetti sono fondamentali per interagire e manipolare i documenti EPS.

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

## Passo 1: Ottenere i metadati XMP
Recupera i metadati XMP dal documento EPS. Se il file EPS non contiene metadati XMP, ne verrà creato uno nuovo con i valori provenienti dai commenti PS come %%Creator, %%CreateDate e %%Title.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Passo 2: Modificare il valore “ModifyDate”
Modifica il valore “ModifyDate” nei metadati XMP per riflettere la data desiderata.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Passo 3: Modificare il valore “Creator”
Aggiorna il valore “Creator” nei metadati XMP per specificare il creatore del documento.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Passo 4: Modificare il valore “Title”
Modifica il valore “Title” nei metadati XMP per impostare un titolo appropriato per il documento.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Passo 5: Salvare il documento con i metadati XMP modificati
Salva il documento con i metadati XMP aggiornati in un nuovo file EPS.

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

## Problemi comuni e soluzioni
- **Blocco XMP mancante** – L'API crea automaticamente uno dai commenti PS, ma è possibile istanziare manualmente `XmpMetadata` se necessario.  
- **Discrepanze di fuso orario** – Imposta sempre `TimeZone.setDefault` prima di creare l'oggetto `Date` per evitare offset inattesi.  
- **Errori di accesso al file** – Verifica che i percorsi di input e output siano corretti e che l'applicazione disponga dei permessi di lettura/scrittura.

## Domande frequenti

**D: Come gestire le considerazioni sul fuso orario quando si modificano i valori XMP?**  
R: Utilizza `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` per garantire coerenza nelle impostazioni del fuso orario.

**D: Posso cambiare più valori XMP in un'unica operazione?**  
R: Sì, usando il metodo `put` per ciascun valore desiderato, è possibile modificare più valori XMP contemporaneamente.

**D: Dove posso trovare documentazione aggiuntiva per Aspose.Page per Java?**  
R: Consulta la documentazione completa [qui](https://reference.aspose.com/page/java/).

**D: È disponibile una versione di prova gratuita per Aspose.Page per Java?**  
R: Sì, puoi accedere alla prova gratuita [qui](https://releases.aspose.com/).

**D: Come posso ottenere una licenza temporanea per Aspose.Page per Java?**  
R: Ottieni una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

**D: La modifica di XMP influisce sul contenuto visivo dell'EPS?**  
R: No. Le modifiche a XMP riguardano solo i metadati e non alterano gli elementi grafici del file EPS.

**D: Posso leggere programmaticamente i valori aggiornati per verificare la modifica?**  
R: Assolutamente — chiama semplicemente `xmp.get("dc:creator")` (o la chiave pertinente) dopo il salvataggio e prima di chiudere il documento.

## Conclusione
Congratulazioni! Hai completato con successo la procedura di **aspose.page modify xmp** nei documenti EPS usando Aspose.Page per Java. Questo tutorial ti ha fornito le conoscenze necessarie per modificare i metadati, garantendo che i tuoi documenti siano allineati ai requisiti specifici in modo fluido.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Ultimo aggiornamento:** 2025-12-21  
**Testato con:** Aspose.Page per Java (ultima release)  
**Autore:** Aspose  

---