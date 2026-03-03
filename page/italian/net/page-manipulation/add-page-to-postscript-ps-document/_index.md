---
date: 2026-03-03
description: Impara a impostare una dimensione di pagina personalizzata e aggiungere
  una seconda pagina PS a un documento PostScript usando Aspose.Page per .NET.
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Imposta dimensione pagina personalizzata in documento PS con Aspose.Page
url: /it/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere una pagina a un documento PostScript (PS) con Aspose.Page

## Introduzione

Nello sviluppo .NET, la possibilità di **impostare una dimensione di pagina personalizzata** e **aggiungere una seconda pagina PS** a un documento PostScript (PS) ti offre un controllo dettagliato sul layout di stampe, report o grafiche generate. Aspose.Page per .NET rende questo compito semplice con una API pulita e orientata agli oggetti. In questo tutorial imparerai a creare un file PS multi‑pagina, definire una dimensione personalizzata per ogni pagina e salvare il risultato — il tutto con poche righe di codice C#.

## Risposte rapide
- **Posso impostare una dimensione di pagina personalizzata?** Sì – basta passare larghezza e altezza quando si apre una pagina.  
- **Come aggiungo una seconda pagina PS?** Chiama `document.OpenPage(width, height)` una seconda volta.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **È necessaria una licenza?** Una licenza temporanea funziona per i test; è necessaria una licenza completa per la produzione.  
- **Dove posso scaricare Aspose.Page?** Dalla pagina di download ufficiale indicata di seguito.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti pronti:

- Una buona conoscenza dello sviluppo .NET.  
- Visual Studio installato sulla tua macchina.  
- La libreria Aspose.Page per .NET, che puoi scaricare [qui](https://releases.aspose.com/page/net/).  
- La tua directory di documenti preferita per i test.

## Importare gli spazi dei nomi

Assicurati di includere gli spazi dei nomi necessari nel tuo progetto per accedere alle funzionalità fornite da Aspose.Page. Nell'esempio fornito, gli spazi dei nomi sono inclusi implicitamente, ma è fondamentale ricontrollare e apportare le modifiche necessarie in base alla struttura del tuo progetto.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Passo 1: Configura il tuo progetto

Crea un nuovo progetto .NET in Visual Studio e configura le impostazioni necessarie. Assicurati di aggiungere un riferimento alla libreria Aspose.Page nel tuo progetto.

## Imposta la dimensione della pagina personalizzata e aggiungi una seconda pagina PS

Questa sezione dimostra esattamente come **impostare una dimensione di pagina personalizzata** per ogni pagina e come **aggiungere una seconda pagina ps** allo stesso documento.

### Passo 2: Inizializzare il documento

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### Passo 3: Aggiungere la prima pagina (dimensione predefinita)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### Passo 4: Aggiungere la seconda pagina con una dimensione diversa (personalizzata)

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### Passo 5: Salvare il documento

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

Segui questi passaggi con attenzione, e riuscirai a **impostare una dimensione di pagina personalizzata** e aggiungere una **seconda pagina PS** a un documento PostScript usando Aspose.Page per .NET.

## Perché è importante

- **Layout preciso** – Le dimensioni di pagina personalizzate ti consentono di corrispondere alle specifiche della stampante o di creare formati di brochure unici.  
- **Pagine multiple** – Aggiungere una seconda pagina (o più) consente report multi‑pagina senza strumenti di fusione esterni.  
- **Cross‑Platform** – Il file PS generato può essere visualizzato su qualsiasi dispositivo compatibile con PostScript o convertito in PDF in seguito.

## Problemi comuni e risoluzione

- **Percorso errato** – Assicurati che `dataDir` termini con un separatore di percorso o utilizza `Path.Combine`.  
- **Problemi di licenza** – Senza una licenza valida, la libreria potrebbe aggiungere una filigrana o limitare il numero di pagine.  
- **Confusione sulle unità** – Larghezza e altezza sono misurate in punti (1 punto = 1/72 di pollice). Regola di conseguenza.

## Domande frequenti

**D1: Aspose.Page è compatibile con diversi formati di documento?**  
R1: Aspose.Page si concentra principalmente sulla manipolazione di documenti PostScript. Per altri formati, puoi esplorare le librerie Aspose specifiche per le esigenze.

**D2: Posso personalizzare la dimensione della pagina in Aspose.Page?**  
R2: Assolutamente! Come mostrato nel tutorial, puoi specificare dimensioni diverse per ogni pagina in base alle tue esigenze.

**D3: Dove posso trovare più esempi e documentazione?**  
R3: Visita la [documentazione](https://reference.aspose.com/page/net/) per informazioni complete e una varietà di esempi.

**D4: Come posso ottenere una licenza temporanea per Aspose.Page?**  
R4: Vai a [questo link](https://purchase.aspose.com/temporary-license/) per ottenere una licenza temporanea a scopo di test.

**D5: Dove posso trovare supporto della community o fare domande?**  
R5: Unisciti al [forum della community Aspose.Page](https://forum.aspose.com/c/page/39) per entrare in contatto con altri sviluppatori, condividere esperienze e chiedere assistenza.

---

**Ultimo aggiornamento:** 2026-03-03  
**Testato con:** Aspose.Page 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}