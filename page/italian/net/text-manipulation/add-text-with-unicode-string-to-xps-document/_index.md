---
title: Aggiungi testo con stringa Unicode al documento XPS con Aspose.Page
linktitle: Aggiungi testo con stringa Unicode al documento XPS
second_title: API Aspose.Page .NET
description: Esplora la potenza di Aspose.Page per .NET con la nostra guida passo passo sull'aggiunta di testo Unicode ai documenti XPS.
weight: 12
url: /it/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi testo con stringa Unicode al documento XPS con Aspose.Page

## introduzione

Nel panorama in continua evoluzione dello sviluppo .NET, Aspose.Page si distingue come un potente strumento per la gestione dei documenti XPS. Tra le sue numerose funzionalità, la possibilità di aggiungere testo con stringhe Unicode a un documento XPS è una funzionalità preziosa. Questa guida passo passo ti guiderà attraverso il processo, assicurandoti di sfruttare questa funzionalità in modo efficace.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:

- Una conoscenza di base dello sviluppo .NET.
- Visual Studio installato sul tuo computer.
-  Aspose.Page per la libreria .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/page/net/).

## Importa spazi dei nomi

Per iniziare, assicurati di importare gli spazi dei nomi necessari nel tuo progetto. Ciò fornirà le classi e le funzionalità richieste per lavorare con Aspose.Page. Ecco gli spazi dei nomi essenziali:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Passaggio 1: impostare il documento

Innanzitutto, crea un nuovo documento XPS in cui aggiungerai il testo Unicode. Segui lo snippet di codice riportato di seguito:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";
// Crea un nuovo documento XPS
XpsDocument doc = new XpsDocument();
```

## Passaggio 2: aggiungi testo Unicode

Ora aggiungiamo il testo Unicode al documento XPS. Questo esempio utilizza il carattere Arial, imposta la dimensione del carattere su 20 e posiziona il testo alle coordinate (400f, 200f). La stringa Unicode in questo caso è "TEN. rof SPX.esopsA". Controlla lo snippet di codice qui sotto:

```csharp
// Aggiungi testo
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Passaggio 3: salva il documento

Una volta aggiunto il testo Unicode, salva il documento XPS risultante. Ecco il passaggio finale:

```csharp
// Salva il documento XPS risultante
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Congratulazioni! Hai aggiunto con successo testo Unicode a un documento XPS utilizzando Aspose.Page per .NET.

## Conclusione

In questo tutorial, abbiamo esplorato il processo di aggiunta di testo Unicode ai documenti XPS utilizzando Aspose.Page per .NET. Questa funzionalità apre le porte alla creazione di documenti diversificata e dinamica all'interno dell'ambiente .NET.

## Domande frequenti

### Q1: Aspose.Page è compatibile con gli ultimi framework .NET?

A1: Sì, Aspose.Page viene regolarmente aggiornato per garantire la compatibilità con gli ultimi framework .NET.

### Q2: Posso personalizzare lo stile e la dimensione del carattere quando aggiungo testo?

A2: Assolutamente! Il codice di esempio fornito ti consente di personalizzare facilmente lo stile, la dimensione e altri attributi del carattere.

### Q3: Dove posso trovare documentazione aggiuntiva per Aspose.Page?

 R3: È possibile fare riferimento alla documentazione[Qui](https://reference.aspose.com/page/net/) per informazioni complete ed esempi.

### Q4: Esistono risorse gratuite per iniziare con Aspose.Page?

 A4: Sì, puoi esplorare il[Forum Aspose.Page](https://forum.aspose.com/c/page/39) per il supporto e le discussioni della comunità.

### Q5: È disponibile una versione di prova prima di effettuare un acquisto?

 A5: Certamente! Puoi accedere alla versione di prova gratuita[Qui](https://releases.aspose.com/) prima di effettuare un acquisto.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
