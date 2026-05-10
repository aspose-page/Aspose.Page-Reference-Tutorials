---
date: 2026-01-12
description: Scopri come creare documenti XPS con Aspose.Page per .NET – una guida
  passo passo per generare documenti elettronici di alta qualità.
linktitle: Create XPS Document
second_title: Aspose.Page .NET API
title: Crea documento XPS con Aspose.Page per .NET
url: /it/net/document-creation/create-xps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea documento XPS con Aspose.Page per .NET

## Introduzione

Benvenuti alla nostra guida passo‑passo su **come creare un documento XPS** utilizzando Aspose.Page per .NET. In questo tutorial, esploreremo il processo di generazione di file XPS, un formato ampiamente utilizzato per documenti elettronici. Che siate sviluppatori esperti o alle prime armi con Aspose.Page, questa guida è pensata per aiutarvi a creare documenti XPS in modo fluido, con esempi chiari e spiegazioni dettagliate.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page for .NET  
- **Posso eseguirlo su .NET Core?** Yes, the library fully supports .NET Core and .NET 5/6  
- **Quante righe di codice?** Less than 20 lines to produce a basic XPS file  
- **È necessaria una licenza per i test?** A free trial is available; a license is required for production  
- **Qual è il formato dell'output?** XPS (XML Paper Specification)  

## Come creare un documento XPS usando Aspose.Page per .NET

Di seguito troverete tutto il necessario prima di iniziare a programmare, seguito da una guida concisa e numerata.

## Prerequisiti

Prima di immergerci nel tutorial, assicuratevi di avere i seguenti prerequisiti:

1. Libreria Aspose.Page per .NET: scaricate e installate la libreria Aspose.Page dal [link di download](https://releases.aspose.com/page/net/).

2. La vostra directory dei documenti: scegliete o create una cartella sul vostro sistema dove salvare i file XPS di output.

Ora, passiamo al tutorial!

## Importa spazi dei nomi

Per utilizzare Aspose.Page per .NET, è necessario importare gli spazi dei nomi necessari nel vostro progetto. Seguite questi passaggi:

### Passo 1: Aggiungi riferimento ad Aspose.Page

Nel vostro progetto, aggiungete un riferimento alla libreria Aspose.Page per .NET. Potete trovare il DLL necessario nel pacchetto scaricato.

### Passo 2: Importa spazi dei nomi

Includete i seguenti spazi dei nomi nel vostro file di codice:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Ora che abbiamo configurato i prerequisiti e importato gli spazi dei nomi necessari, suddividiamo il processo di creazione di un documento XPS in più passaggi.

## Passo 1: Imposta la directory del documento

```csharp
string dir = "Your Document Directory";
```

Assicuratevi di sostituire `"Your Document Directory"` con il percorso reale dove desiderate salvare il file XPS di output.

## Passo 2: Crea documento XPS

```csharp
XpsDocument xDocs = new XpsDocument();
```

Inizializzate un nuovo documento XPS usando la classe `XpsDocument`.

## Passo 3: Aggiungi glyphs al documento

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

Utilizzate il metodo `AddGlyphs` per aggiungere glyphs (testo) al documento. Personalizzate il font, la dimensione, lo stile e la posizione secondo necessità.

## Passo 4: Imposta il colore di riempimento dei glyphs

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

Specificate il colore di riempimento per i glyphs aggiunti. In questo esempio, usiamo il nero, ma potete scegliere qualsiasi colore.

## Passo 5: Salva il risultato

```csharp
xDocs.Save(dir + "output.xps");
```

Infine, salvate il documento XPS nella directory specificata con il nome file desiderato. Il file XPS risultante conterrà il testo "Hello World!".

Congratulazioni! Avete creato con successo un documento XPS usando Aspose.Page per .NET.

## Consigli comuni e trappole

- **Percorso della directory** – Utilizzate `Path.Combine(dir, "output.xps")` per evitare la mancanza di separatori di percorso su diversi OS.  
- **Disponibilità del font** – Il font specificato deve essere installato sulla macchina in cui il codice viene eseguito; altrimenti, Aspose sostituirà con un font predefinito.  
- **Pagine multiple** – Per creare file XPS multi‑pagina, istanziate ulteriori oggetti `XpsPage` e aggiungete contenuti a ciascuna pagina prima di salvare.

## Conclusione

In questo tutorial, abbiamo illustrato il processo di creazione di documenti XPS usando Aspose.Page per .NET. Questa potente libreria offre un modo fluido per generare documenti elettronici con facilità. Sperimentate con diversi font, stili e contenuti per personalizzare i vostri file XPS secondo le vostre esigenze.

## FAQ

### Q1: Posso usare font personalizzati nel mio documento XPS?

A1: Sì, potete specificare la famiglia e la dimensione del font quando aggiungete glyphs al vostro documento XPS.

### Q2: Aspose.Page è compatibile con .NET Core?

A2: Sì, Aspose.Page supporta .NET Core, consentendovi di usarlo in applicazioni cross‑platform.

### Q3: Come posso aggiungere immagini a un documento XPS?

A3: Aspose.Page fornisce metodi per aggiungere immagini al vostro documento XPS. Consultate la documentazione per esempi dettagliati.

### Q4: Posso creare documenti XPS multi‑pagina?

A4: Assolutamente! Potete aggiungere più pagine a un documento XPS usando la libreria Aspose.Page.

### Q5: È disponibile una versione di prova?

A5: Sì, potete esplorare le funzionalità di Aspose.Page scaricando la [versione di prova gratuita](https://releases.aspose.com/).

---

**Ultimo aggiornamento:** 2026-01-12  
**Testato con:** Aspose.Page 24.11 for .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}