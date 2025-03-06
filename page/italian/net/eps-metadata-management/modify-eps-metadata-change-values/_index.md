---
title: Modificare i valori con Aspose.Page per .NET
linktitle: Modificare valori
second_title: API Aspose.Page .NET
description: Padroneggia la manipolazione dei file EPS con Aspose.Page per .NET. Modifica facilmente i valori dei metadati XMP.
weight: 17
url: /it/net/eps-metadata-management/modify-eps-metadata-change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modificare i valori con Aspose.Page per .NET

## introduzione

Nel dinamico mondo dell'elaborazione dei documenti, Aspose.Page per .NET si distingue come un potente strumento, offrendo agli sviluppatori la possibilità di manipolare i file EPS senza sforzo. In questo tutorial, approfondiremo il processo di modifica dei valori all'interno dei file EPS utilizzando Aspose.Page per .NET. Che tu sia uno sviluppatore esperto o un principiante curioso, questa guida passo passo ti fornirà le competenze necessarie per modificare in modo efficiente i metadati XMP nei tuoi file EPS.

## Prerequisiti

Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:

### 1. Aspose.Page per la libreria .NET

Assicurati di avere la libreria Aspose.Page per .NET installata nel tuo ambiente di sviluppo. In caso contrario, puoi scaricarlo[Qui](https://releases.aspose.com/page/net/).

### 2. Directory dei documenti

Configura una directory per i tuoi documenti. Questa sarà la posizione in cui verranno archiviati i file EPS.

Ora che abbiamo risolto i prerequisiti, passiamo ai passaggi cruciali successivi.

## Importa spazi dei nomi

In qualsiasi progetto .NET, è essenziale importare gli spazi dei nomi necessari per utilizzare le funzionalità di Aspose.Page. Ecco come puoi farlo:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Passaggio 1: inizializza il flusso di input del file EPS

```csharp
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";
// Inizializza il flusso di input del file EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## Passaggio 2: crea un'istanza PsDocument dal flusso

```csharp
//Crea un'istanza PsDocument dal flusso
PsDocument document = new PsDocument(psStream);
```

Ora che abbiamo preparato il terreno, passiamo al nocciolo del nostro tutorial: modificare i valori dei metadati XMP all'interno del file EPS.

## Passaggio 3: ottieni i metadati XMP

```csharp
// Ottieni metadati XMP. Se il file EPS non contiene metadati XMP, ne otteniamo uno nuovo pieno di valori dai commenti sui metadati PS (%%Creator, %%CreateDate, %%Title, ecc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Passaggio 4: modifica i valori dei metadati XMP

Ora modifichiamo alcuni valori chiave nei metadati XMP:

### Passaggio 4.1: modificare il valore ModifyDate

```csharp
// Modificare il valore ModifyDate
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### Passaggio 4.2: modifica il valore Creatore

```csharp
// Cambia il valore del Creatore
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Passaggio 4.3: modificare il valore del titolo

```csharp
// Modifica il valore del titolo
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

Una volta apportate queste modifiche, passiamo al passaggio finale: salvare il file EPS modificato.

## Passaggio 5: salva il file EPS con i metadati XMP modificati

### Passaggio 5.1: creazione del flusso di output

```csharp
// Crea flusso di output
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### Passaggio 5.2: salva il file EPS

```csharp
// Salva il file EPS
document.Save(outPsStream);
```

Infine, chiudi il flusso di input:

```csharp
finally
{
    psStream.Close();
}
```

Congratulazioni! Hai modificato con successo i valori dei metadati XMP in un file EPS utilizzando Aspose.Page per .NET.

## Conclusione

In questo tutorial, abbiamo esplorato il processo continuo di modifica dei valori all'interno dei file EPS utilizzando Aspose.Page per .NET. Come sviluppatore, ora hai a tua disposizione un potente strumento per una manipolazione efficiente dei documenti.

## Domande frequenti

### Q1: Posso utilizzare Aspose.Page per .NET con altri formati di file?

A1: Aspose.Page si concentra principalmente sulla manipolazione dei file EPS. Per altri formati, esplora la vasta gamma di prodotti Aspose.

### Q2: È disponibile una versione di prova?

 A2: Sì, puoi provare Aspose.Page per .NET con la versione di prova gratuita disponibile[Qui](https://releases.aspose.com/).

### Q3: Dove posso trovare la documentazione dettagliata?

 A3: È possibile trovare la documentazione completa[Qui](https://reference.aspose.com/page/net/).

### Q4: Come posso ottenere una licenza temporanea?

 A4: Puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).

### Q5: Posso acquistare Aspose.Page per .NET?

 A5: Assolutamente! Visita la pagina di acquisto[Qui](https://purchase.aspose.com/buy) per le opzioni di licenza.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
