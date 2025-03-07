---
title: Aggiungi valore denominato con Aspose.Page
linktitle: Aggiungi valore denominato
second_title: API Aspose.Page .NET
description: Scopri come aggiungere valori denominati ai file EPS in .NET utilizzando Aspose.Page. Questo tutorial completo ti guida attraverso il processo passo dopo passo.
weight: 12
url: /it/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi valore denominato con Aspose.Page

## introduzione

Nell'ambito dell'elaborazione dei documenti con .NET, Aspose.Page si distingue come un potente strumento per la gestione dei file EPS. Aspose.Page consente agli sviluppatori di manipolare i metadati XMP, facilitando attività come l'aggiunta di valori denominati. Questo tutorial ti guiderà attraverso il processo di aggiunta di valori denominati a un file EPS utilizzando Aspose.Page in modo passo passo.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- È installato un ambiente di sviluppo integrato (IDE) come Visual Studio.
-  Aspose.Page per la libreria .NET. Se non è installato, puoi scaricarlo da[Qui](https://releases.aspose.com/page/net/).

## Importa spazi dei nomi

Innanzitutto, importiamo gli spazi dei nomi necessari nel codice C#. Questi spazi dei nomi sono vitali per accedere alle funzionalità fornite da Aspose.Page:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Passaggio 1: inizializzare il flusso di input del file EPS

 Il passaggio iniziale prevede l'inizializzazione del flusso di input per il file EPS. Sostituire`"Your Document Directory"` con il percorso della directory dei documenti:

```csharp
// Inizio ex:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Passaggio 2: ottieni i metadati XMP

Recupera i metadati XMP dal file EPS. Se il file EPS non dispone di metadati XMP, ne verrà creato uno nuovo, riempito con i valori dei commenti sui metadati PS:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Passaggio 3: modifica i valori dei metadati XMP

Ora apportiamo le modifiche ai metadati XMP. In questo esempio, aggiungeremo un valore denominato alla struttura "xmpTPg:MaxPageSize":

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Passaggio 4: salva il file EPS con i metadati XMP modificati

Salva il file EPS con i metadati XMP aggiornati. Crea un flusso di output e salva il file EPS modificato:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Conclusione

Congratulazioni! Hai aggiunto con successo un valore denominato a un file EPS utilizzando Aspose.Page in .NET. Questo tutorial ti ha guidato attraverso i passaggi essenziali, mostrando la semplicità e l'efficacia di Aspose.Page nella manipolazione dei documenti.

## Domande frequenti

### Q1: Aspose.Page è compatibile con diverse versioni di file EPS?

R1: Aspose.Page supporta varie versioni di file EPS, garantendo la compatibilità con un'ampia gamma di documenti.

### Q2: Posso utilizzare Aspose.Page per progetti commerciali?

 A2: Sì, Aspose.Page viene fornito con una licenza commerciale e puoi acquistarla[Qui](https://purchase.aspose.com/buy).

### Q3: È disponibile una prova gratuita per Aspose.Page?

 A3: Sì, puoi esplorare Aspose.Page con una prova gratuita disponibile[Qui](https://releases.aspose.com/).

### Q4: Come posso ottenere supporto o connettermi con la comunità Aspose?

 A4: Visita il[Forum Aspose.Page](https://forum.aspose.com/c/page/39) per ottenere supporto e connettersi con la comunità.

### Q5: Cos'è una licenza temporanea e come posso ottenerne una?

 R5: Se hai bisogno di una licenza temporanea per scopi di test o valutazione, puoi acquistarne una[Qui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
