---
date: 2026-03-16
description: Scopri come ritagliare le immagini EPS e ridimensionare i file immagine
  EPS in .NET usando Aspose.Page. Segui questa guida passo passo per ritagliare EPS
  e ridimensionare le immagini EPS senza sforzo.
linktitle: Crop EPS Images
second_title: Aspose.Page .NET API
title: Come ritagliare immagini EPS con Aspose.Page per .NET
url: /it/net/image-manipulation/crop-eps-images/
weight: 10
---

: translate column headers and content.

FAQs: translate Q1 etc.

Make sure to keep code block placeholders unchanged.

Let's craft.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come ritagliare immagini EPS con Aspose.Page per .NET

## Introduzione

Se devi sapere **come ritagliare immagini EPS** in un'applicazione .NET, sei nel posto giusto. In questo tutorial ti guideremo attraverso il ritaglio e il ridimensionamento di file EPS usando la potente libreria Aspose.Page per .NET. Che tu stia perfezionando uno strumento di reporting o preparando grafiche per un servizio web, padroneggiare questa tecnica ti farà risparmiare tempo e ti garantirà risultati pixel‑perfect.

## Risposte rapide
- **Quale libreria gestisce il ritaglio EPS?** Aspose.Page per .NET  
- **Metodo principale?** `doc.CropEps(outputStream, newBoundingBox)`  
- **Posso anche ridimensionare l'EPS?** Sì – usa `ResizeEps` con pollici, millimetri o percentuali.  
- **Prerequisiti?** .NET (Framework 4.5+ / .NET Core 3.1+), Aspose.Page installato, un file EPS.  
- **Tempo tipico di implementazione?** Circa 10 minuti per un flusso di lavoro base di ritaglio‑e‑ridimensionamento.

## Prerequisiti

Prima di immergerti nel codice, assicurati di avere:

- Una buona conoscenza dello sviluppo .NET.  
- La libreria Aspose.Page per .NET installata. Se non lo è, puoi scaricarla [qui](https://releases.aspose.com/page/net/).  
- Un'immagine EPS di esempio (sostituisci `"input.eps"` nel codice con il tuo file reale).

## Importare gli spazi dei nomi

Iniziamo importando gli spazi dei nomi che ci danno accesso alle classi di gestione EPS.

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## Come ritagliare immagini EPS – Guida passo‑passo

### Passo 1: Inizializzare `PsDocument`

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

Creiamo un'istanza di `PsDocument` dallo stream EPS di input. Questo oggetto rappresenta il file EPS in memoria e ci dà accesso ai metodi di ritaglio e ridimensionamento.

### Passo 2: Estrarre il Bounding Box originale

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

Il bounding box ti indica le dimensioni attuali della tela EPS. Conoscere questi valori ti aiuta a definire un rettangolo di ritaglio sicuro.

### Passo 3: Creare uno stream di output

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Apriamo uno stream scrivibile dove verrà salvato l'EPS ritagliato. L'uso di un blocco `using` garantisce che lo stream venga chiuso correttamente.

### Passo 4: Definire un nuovo Bounding Box

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Sostituisci i numeri con le coordinate che desideri conservare. Assicurati che i nuovi valori rimangano all'interno del bounding box originale; altrimenti l'operazione fallirà.

### Passo 5: Ritagliare e salvare l'EPS

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Questa singola riga esegue il ritaglio e scrive il risultato in `output_crop.eps`. Il metodo modifica il documento in‑memoria, così puoi concatenare ulteriori operazioni se necessario.

## Ridimensionare l'immagine EPS

Dopo il ritaglio, spesso si vuole cambiare le dimensioni dell'EPS per visualizzazione o stampa. Aspose.Page supporta tre unità di misura.

### Ridimensionare in pollici

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

### Ridimensionare in millimetri

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

### Ridimensionare in percentuali

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Ogni chiamata sovrascrive l'output precedente, quindi assicurati di creare uno stream nuovo se ti servono file separati per ogni dimensione.

## Problemi comuni e risoluzione

| Sintomo | Probabile causa | Soluzione |
|---------|----------------|-----------|
| **Valori del bounding box fuori intervallo** | Il nuovo box supera le dimensioni originali | Verifica i valori di `initialBoundingBox` e scegli coordinate all'interno di quell'intervallo. |
| **Il file di output è vuoto** | Lo stream di output non è stato svuotato o chiuso | Assicurati che il blocco `using` termini prima di accedere al file, o chiama `outputEpsStream.Flush()`. |
| **Scalatura inattesa** | Miscelazione di unità (es. pollici vs. millimetri) | Specifica sempre l'enum `Units` corretto che corrisponde ai valori di dimensione. |

## FAQ

### Q1: Posso usare Aspose.Page per .NET con altri formati immagine?

A1: Aspose.Page si concentra principalmente su immagini EPS, ma Aspose offre varie librerie per formati diversi. Consulta la loro documentazione per i formati specifici.

### Q2: Come posso ottenere una licenza temporanea per Aspose.Page per .NET?

A2: Visita [questo link](https://purchase.aspose.com/temporary-license/) per ottenere una licenza temporanea per i test.

### Q3: Ci sono limitazioni alle dimensioni dell'immagine che posso elaborare con Aspose.Page per .NET?

A3: Aspose.Page è progettato per gestire immagini di varie dimensioni. Tuttavia, le prestazioni possono variare in base alla complessità dell'immagine.

### Q4: Esiste un forum della community per le discussioni su Aspose.Page?

A5: Sì, puoi interagire con la community di Aspose.Page [qui](https://forum.aspose.com/c/page/39).

### Q5: Dove posso trovare la documentazione dettagliata per Aspose.Page per .NET?

A5: Consulta la documentazione [qui](https://reference.aspose.com/page/net/).

---

**Ultimo aggiornamento:** 2026-03-16  
**Testato con:** Aspose.Page 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}