---
title: Aggiungi proprietà semplici con Aspose.Page per .NET
linktitle: Aggiungi proprietà semplici
second_title: API Aspose.Page .NET
description: Migliora i file EPS con Aspose.Page per .NET. Aggiungi proprietà semplici senza sforzo per metadati di documenti personalizzati.
type: docs
weight: 14
url: /it/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---
## introduzione

Nel campo della manipolazione e del miglioramento dei documenti, Aspose.Page per .NET emerge come un potente strumento, fornendo agli sviluppatori la capacità di aggiungere e modificare metadati XMP all'interno dei file EPS senza soluzione di continuità. Questo tutorial ti guiderà attraverso il processo di aggiunta di proprietà semplici a un file EPS utilizzando Aspose.Page per .NET.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:

1.  Aspose.Page per .NET: assicurati di avere Aspose.Page per .NET installato nel tuo ambiente di sviluppo. In caso contrario, puoi scaricarlo[Qui](https://releases.aspose.com/page/net/).

2.  Directory dei documenti: imposta una directory per archiviare i file EPS. Aggiorna il`dataDir` variabile nello snippet di codice fornito con il percorso della directory dei documenti.

## Importa spazi dei nomi

Per iniziare, importare gli spazi dei nomi necessari per abilitare la comunicazione con Aspose.Page per .NET. Aggiungi le seguenti righe all'inizio del file di codice:

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

```csharp
// Inizio ex:1
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";
// Inizializza il flusso di input del file EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Crea un'istanza PsDocument dal flusso
PsDocument document = new PsDocument(psStream);
```

## Passaggio 2: ottieni i metadati XMP

```csharp
// Ottieni metadati XMP. Se il file EPS non contiene metadati XMP, ne otteniamo uno nuovo pieno di valori dai commenti sui metadati PS (%%Creator, %%CreateDate, %%Title, ecc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Passaggio 3: modifica i valori dei metadati XMP

```csharp
// Modifica i valori dei metadati XMP
DateTime now = DateTime.UtcNow;

// Aggiungi la proprietà Intero
xmp.Add("xmp:Intg1", new XmpValue(111));

// Aggiungi la proprietà DateTime
xmp.Add("xmp:Date1", new XmpValue(now));

// Aggiungi la proprietà Double
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//Aggiungi la proprietà String
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## Passaggio 4: salva il file EPS con i metadati XMP modificati

```csharp
// Salva il file EPS con i metadati XMP modificati

// Crea flusso di output
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Salva il file EPS
    document.Save(outPsStream);
}
```

## Passaggio 5: chiudere FileStream

```csharp
finally
{
    psStream.Close();
}
```

Seguendo questi passaggi, puoi incorporare facilmente proprietà semplici nei tuoi file EPS utilizzando Aspose.Page per .NET.

## Conclusione

In conclusione, Aspose.Page per .NET si rivela una risorsa inestimabile per gli sviluppatori che cercano di migliorare i file EPS con metadati XMP personalizzati. Aggiungendo semplici proprietà, puoi personalizzare e arricchire i tuoi documenti per soddisfare requisiti specifici, aprendo un mondo di possibilità per la manipolazione dei documenti.

## Domande frequenti

### Q1: Aspose.Page per .NET è compatibile con tutti i file EPS?

A1: Aspose.Page per .NET supporta un'ampia gamma di file EPS. Tuttavia, la compatibilità può variare in base alla complessità e alla struttura dei singoli file.

### Q2: Posso modificare i metadati XMP esistenti con Aspose.Page per .NET?

A2: Assolutamente! Come dimostrato in questo tutorial, puoi modificare facilmente i valori dei metadati XMP esistenti o aggiungerne di nuovi in base alle tue esigenze.

### Q3: Esistono limitazioni ai tipi di proprietà che posso aggiungere?

A3: Aspose.Page per .NET supporta vari tipi di dati per le proprietà, inclusi numeri interi, date, doppi e stringhe. Hai flessibilità nella scelta del tipo appropriato per i tuoi metadati.

### Q4: Come posso ottenere supporto tecnico per Aspose.Page per .NET?

 R4: Per assistenza tecnica, visitare il[Aspose.Page Forum](https://forum.aspose.com/c/page/39) o esplora il[documentazione](https://reference.aspose.com/page/net/) per una guida completa.

### Q5: È disponibile una prova gratuita per Aspose.Page per .NET?

 R5: Sì, puoi accedere a una prova gratuita[Qui](https://releases.aspose.com/).