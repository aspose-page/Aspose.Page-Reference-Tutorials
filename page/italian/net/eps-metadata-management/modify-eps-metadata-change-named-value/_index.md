---
title: Modificare il valore denominato con Aspose.Page per .NET
linktitle: Modifica valore denominato
second_title: API Aspose.Page .NET
description: Scopri come modificare i valori denominati nei file EPS utilizzando Aspose.Page per .NET. Personalizza facilmente i metadati XMP per un'elaborazione dei documenti su misura.
weight: 16
url: /it/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modificare il valore denominato con Aspose.Page per .NET

## introduzione

Nel mondo dell'elaborazione dei documenti, Aspose.Page per .NET si distingue come un potente strumento per manipolare file EPS. Una delle funzionalità chiave che offre è la possibilità di modificare i valori denominati all'interno dei metadati XMP. Questo tutorial ti guiderà attraverso il processo di modifica di un valore denominato utilizzando Aspose.Page per .NET, consentendoti di personalizzare i tuoi file EPS in base alle tue esigenze specifiche.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:

-  Aspose.Page per .NET: assicurati di avere la libreria Aspose.Page per .NET installata. In caso contrario, puoi scaricarlo[Qui](https://releases.aspose.com/page/net/).

- Directory dei documenti: dispone di una directory designata per i file EPS in cui è possibile eseguire le modifiche ai valori denominati.

## Importa spazi dei nomi

Nel tuo progetto .NET, devi importare gli spazi dei nomi necessari per accedere alle funzionalità fornite da Aspose.Page. Aggiungi i seguenti spazi dei nomi al tuo codice:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ora, suddividiamo il codice in più passaggi per una comprensione completa:

## Passaggio 1: inizializzare il flusso di input del file EPS

```csharp
// Inizio ex:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// Fine Estesa:1
```

In questo passaggio, impostiamo il flusso di input per il file EPS che desideri modificare. Assicurati di sostituire "La tua directory dei documenti" con il percorso effettivo della directory dei documenti.

## Passaggio 2: ottieni i metadati XMP

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Recupera i metadati XMP esistenti dal file EPS. Se il file EPS non contiene metadati XMP, ne verrà generato uno nuovo con i valori dei commenti dei metadati PS.

## Passaggio 3: modifica i valori dei metadati XMP

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Qui dimostriamo la modifica di due valori denominati all'interno della struttura "xmpTPg:MaxPageSize". Puoi personalizzarlo in base alle tue esigenze specifiche.

## Passaggio 4: salva il file EPS con i metadati XMP modificati

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Salva il file EPS modificato nel flusso di output. Il file ora rifletterà le modifiche apportate ai metadati XMP.

## Conclusione

Con questo tutorial hai imparato come sfruttare Aspose.Page per .NET per modificare i valori denominati all'interno dei metadati XMP nei file EPS. Questa funzionalità apre un mondo di possibilità per personalizzare e adattare i tuoi documenti per soddisfare requisiti specifici.

## Domande frequenti

### Q1: posso utilizzare Aspose.Page per .NET con altri formati di documenti?

R1: Sì, Aspose.Page supporta vari formati di documenti, inclusi EPS, XPS e PDF.

### Q2: È disponibile una versione di prova per Aspose.Page per .NET?

 R2: Sì, puoi accedere a una prova gratuita[Qui](https://releases.aspose.com/).

### Q3: Dove posso trovare ulteriore documentazione su Aspose.Page per .NET?

 R3: Fare riferimento alla documentazione[Qui](https://reference.aspose.com/page/net/).

### Q4: Come posso ottenere una licenza temporanea per Aspose.Page per .NET?

 A4: Puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).

### Q5: Quali opzioni di supporto sono disponibili per Aspose.Page per gli utenti .NET?

 A5: Visita il forum della community[Qui](https://forum.aspose.com/c/page/39) per supporto e discussioni.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
