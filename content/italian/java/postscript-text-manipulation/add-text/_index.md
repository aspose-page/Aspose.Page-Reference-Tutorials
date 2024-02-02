---
title: Aspose.Page Manipolazione del testo Java
linktitle: Aggiungi testo in Java PostScript
second_title: API Java Aspose.Page
description: Esplora la potenza di Aspose.Page per Java nel nostro tutorial sull'aggiunta di testo ai documenti PostScript. Impara a utilizzare facilmente i caratteri di sistema e personalizzati.
type: docs
weight: 10
url: /it/java/postscript-text-manipulation/add-text/
---
## introduzione
Benvenuti nella nostra guida passo passo sull'aggiunta di testo in Java PostScript utilizzando Aspose.Page per Java. Aspose.Page per Java è una potente libreria che consente agli sviluppatori di manipolare facilmente i documenti PostScript. In questo tutorial ti guideremo attraverso il processo di aggiunta di testo, utilizzando caratteri di sistema e personalizzati, delineando il testo e incorporando tratti per un risultato visivamente accattivante.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:
- Conoscenza base della programmazione Java.
-  Aspose.Page per la libreria Java installata. Puoi scaricarlo da[Aspose.Page per la pagina di download di Java](https://releases.aspose.com/page/java/).
-  Caratteri necessari disponibili nella cartella specificata. Puoi trovare ulteriori informazioni in[Aspose.Page per la documentazione Java](https://reference.aspose.com/page/java/).
## Importa pacchetti
Nel tuo progetto Java, importa i pacchetti necessari per Aspose.Page per Java:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```
## Passaggio 1: impostare il documento
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Crea flusso di output per il documento PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Crea opzioni di salvataggio con il formato A4
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// Un testo da scrivere nel file PS
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Crea un nuovo documento PS di 1 pagina
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Passaggio 2: utilizzo del carattere di sistema per riempire il testo
```java
// Utilizzo del carattere di sistema per riempire il testo
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Riempi il testo con il colore predefinito o già definito (nero)
document.fillText(str, font, 50, 100);
// Riempi il testo con il colore blu
document.fillText(str, font, 50, 150, Color.BLUE);
```
## Passaggio 3: utilizzo del carattere personalizzato per il riempimento del testo
```java
// Utilizzo di caratteri personalizzati per riempire il testo
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Riempi il testo con il colore predefinito o già definito (nero)
document.fillText(str, drFont, 50, 200);
// Riempi il testo con il colore blu
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## Passaggio 4: delineare il testo con il carattere di sistema
```java
// Utilizzo del carattere di sistema per delineare il testo
document.outlineText(str, font, 50, 300);
// Delineare il testo con penna a 2 punti di colore blu-viola
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Riempi il testo con il colore arancione e traccia con una penna di larghezza 2 punti di colore blu
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## Passaggio 5: delineare il testo con carattere personalizzato
```java
// Utilizzo di caratteri personalizzati per delineare il testo
document.outlineText(str, drFont, 50, 450);
// Delineare il testo con penna a 2 punti di colore blu-viola
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Riempi il testo con il colore arancione e traccia con una penna di larghezza 2 punti di colore blu
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## Passaggio 6: salva il documento
```java
// Chiudi la pagina corrente
document.closePage();
// Salva il documento
document.save();
```
## Conclusione
Congratulazioni! Hai imparato con successo come aggiungere testo in Java PostScript utilizzando Aspose.Page per Java. Sperimenta diversi tipi di carattere, colori e opzioni di struttura per migliorare ulteriormente il tuo documento.
## Domande frequenti
### Posso utilizzare i miei caratteri personalizzati con Aspose.Page per Java?
 Sì, puoi utilizzare caratteri personalizzati specificando il nome e la dimensione del carattere nel file`DrFont` classe.
### Come posso cambiare il colore del testo?
 È possibile impostare il colore desiderato utilizzando`Color` classe durante la compilazione o la delineazione del testo.
### È possibile aggiungere più pagine a un documento PostScript?
Assolutamente! È possibile creare più pagine ripetendo i passaggi di creazione e salvataggio del documento.
###  Qual è lo scopo del`ExternalFontCache` class?
`ExternalFontCache` viene utilizzato per recuperare caratteri personalizzati, assicurandosi che siano disponibili per la manipolazione del testo.
### Posso applicare tratti diversi al testo delineato?
 Sì, puoi personalizzare la larghezza e il colore del tratto utilizzando il file`Stroke` classe e`Color` classe, rispettivamente.