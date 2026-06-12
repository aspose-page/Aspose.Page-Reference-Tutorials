---
date: 2026-01-15
description: Scopri come unire documenti XPS usando Aspose.Page per .NET – una guida
  passo‑passo per una fusione di documenti senza interruzioni.
linktitle: Merge XPS Documents
second_title: Aspose.Page .NET API
title: Come unire documenti XPS con Aspose.Page per .NET
url: /it/net/document-merging/merge-xps-documents/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come unire documenti XPS con Aspose.Page per .NET

## Introduzione

Stai cercando un modo affidabile **per unire file XPS** in modo programmatico? In questo tutorial ti guideremo passo passo attraverso le procedure esatte per unire documenti XPS usando Aspose.Page per .NET. Che tu debba combinare report, fatture o qualsiasi altro contenuto basato su XPS, il processo è semplice e completamente automatizzato. Immergiamoci e scopri come ottenere un output XPS unito e pulito con poche righe di codice C#.

## Risposte rapide
- **Quale libreria gestisce l'unione di XPS?** Aspose.Page per .NET  
- **Quanto tempo richiede l'implementazione?** Tipicamente meno di 10 minuti  
- **È necessaria una licenza?** È richiesta una licenza per l'uso in produzione; è disponibile una versione di prova gratuita  
- **Versioni .NET supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Posso unire file XPS crittografati?** Sì – Aspose.Page può gestire documenti crittografati

## Che cos'è l'unione di documenti XPS?
XPS (XML Paper Specification) è un formato di documento a layout fisso creato da Microsoft. Unire file XPS significa concatenare più documenti XPS in un unico file continuo, preservando il layout originale, i caratteri e la grafica.

## Perché usare Aspose.Page per .NET?
- **Controllo totale** sul processo di unione senza la necessità di Microsoft XPS Viewer  
- **Nessuna dipendenza esterna** – tutto gira all'interno della tua applicazione .NET  
- **Alte prestazioni** – funziona in modo efficiente anche con documenti di grandi dimensioni  
- **Cross‑platform** – compatibile con .NET Framework, .NET Core e .NET 5+  

## Prerequisiti

Prima di iniziare, assicurati di avere:

- Una conoscenza di base di C# e dell'ecosistema .NET.  
- **Aspose.Page per .NET** installato – puoi scaricarlo [qui](https://releases.aspose.com/page/net/).  
- Uno o più file XPS che desideri combinare.

## Importare gli spazi dei nomi

Nel tuo progetto C#, importa lo spazio dei nomi che ti dà accesso all'API XPS:

```csharp
using Aspose.Page.XPS;
```

## Passo 1: Configura il tuo progetto

Crea un nuovo progetto console o libreria C# in Visual Studio, Rider o nel tuo IDE preferito. Aggiungi un riferimento al DLL di Aspose.Page (o installa il pacchetto NuGet `Aspose.Page`). Questo ti fornisce l'accesso alla classe `XpsDocument` utilizzata successivamente.

## Passo 2: Inizializzare gli stream

Apri i file XPS di origine come stream di input e crea uno stream di output per il documento unito. Le istruzioni `using` garantiscono che tutti gli stream vengano chiusi correttamente al termine dell'operazione.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Initialize XPS output stream
using (System.IO.Stream outStream = System.IO.File.Open(dataDir + "mergedXPSfiles.xps", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream inStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

## Passo 3: Caricare il documento XPS

Crea un'istanza di `XpsDocument` dallo stream di input principale. L'oggetto `XpsLoadOptions` ti permette di personalizzare il comportamento di caricamento se necessario.

```csharp
XpsDocument document = new XpsDocument(inStream, new XpsLoadOptions());
```

## Passo 4: Creare un array di file XPS

Prepara un array di stringhe che elenca tutti i file XPS che desideri unire. L'ordine dell'array determina l'ordine nel documento finale.

```csharp
string[] filesToMerge = new string[] { dataDir + "Demo.xps", dataDir + "sample.xps" };
```

## Passo 5: Unire i file XPS

Chiama il metodo `Merge`, passando l'array di percorsi dei file e lo stream di output. Aspose.Page gestisce tutto il lavoro pesante—unendo le pagine, preservando le risorse e scrivendo il file XPS finale.

```csharp
document.Merge(filesToMerge, outStream);
```

## Problemi comuni e consigli

- **File non trovato** – Verifica nuovamente i percorsi in `filesToMerge`. Usare `Path.Combine` può aiutare a evitare errori di separatore di percorso.  
- **Uso della memoria** – Quando unisci un gran numero di file, considera di elaborarli in batch per mantenere basso il consumo di memoria.  
- **Documenti crittografati** – Se qualche XPS di origine è protetto da password, caricalo con le credenziali appropriate prima dell'unione.

## Domande frequenti

**Q1: Posso unire file XPS di dimensioni di pagina diverse?**  
A: Sì. Aspose.Page normalizza automaticamente le dimensioni delle pagine durante l'unione.

**Q2: Esiste un limite al numero di file XPS che posso combinare?**  
A: Non c'è un limite rigido, ma collezioni molto grandi possono influire sulle prestazioni; monitora l'uso della memoria.

**Q3: È necessaria una licenza speciale per unire documenti XPS crittografati?**  
A: È richiesta una licenza completa di Aspose.Page per qualsiasi funzionalità a livello di produzione, inclusa la gestione di documenti crittografati.

**Q4: Come aggiungere un piè di pagina personalizzato a ogni pagina dopo l'unione?**  
A: Dopo l'unione, puoi riaprire l'XPS risultante con `XpsDocument` e usare l'API di disegno per inserire i piè di pagina.

**Q5: Aspose.Page supporta .NET Core?**  
A: Assolutamente. La libreria è compatibile con .NET Core 3.1 e versioni successive, così come con .NET 5/6/7.

## Conclusione

Ora hai imparato **come unire documenti XPS** in modo efficiente usando Aspose.Page per .NET. Seguendo i passaggi sopra, puoi automatizzare la consolidazione dei documenti in qualsiasi applicazione .NET, risparmiando tempo e riducendo lo sforzo manuale. Esplora ulteriormente l'API per aggiungere filigrane, crittografare il file finale o manipolare le singole pagine secondo necessità.

---

**Ultimo aggiornamento:** 2026-01-15  
**Testato con:** Aspose.Page for .NET (latest version)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}