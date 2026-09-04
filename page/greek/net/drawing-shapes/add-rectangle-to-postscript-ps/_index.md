---
date: 2026-06-30
description: Μάθετε πώς να δημιουργήσετε έγγραφο postscript .NET και να προσθέσετε
  ορθογώνια χρησιμοποιώντας το Aspose.Page για .NET. Οδηγός βήμα‑βήμα με παραδείγματα
  κώδικα.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: Προσθήκη Ορθογωνίου στο PostScript (PS)
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Δημιουργία Εγγράφου PostScript .NET – Προσθήκη Ορθογωνίου Aspose.Page
url: /el/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη Ορθογωνίου στο PostScript (PS) με Aspose.Page για .NET

## Εισαγωγή

Το Aspose.Page για .NET είναι μια βιβλιοθήκη που επιτρέπει τη δημιουργία και τη διαχείριση αρχείων PostScript, EPS και XPS προγραμματιστικά. Εάν θέλετε να **create postscript document .net**, αυτό το tutorial σας καθοδηγεί στη προσθήκη ορθογωνίων σε ένα έγγραφο PostScript χρησιμοποιώντας το Aspose.Page, παρέχοντάς σας μια ισχυρή βάση για πιο πλούσια δημιουργία γραφικών.

## Γρήγορες Απαντήσεις
- **Τι βιβλιοθήκη χρειάζομαι;** Aspose.Page for .NET.  
- **Μπορώ να δημιουργήσω ένα έγγραφο PostScript από το μηδέν;** Yes – the API lets you build PS files programmatically.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Χρειάζομαι άδεια για ανάπτυξη;** A free trial works for testing; a license is required for production.  
- **Πόσο διαρκεί η υλοποίηση;** Typically under 10 minutes for basic shapes.

## Τι είναι η δημιουργία εγγράφου postscript .net;
Η δημιουργία ενός εγγράφου PostScript σε .NET σημαίνει την προγραμματιστική παραγωγή ενός `.ps` αρχείου που περιγράφει το περιεχόμενο της σελίδας—κείμενο, γραφικά ή σχήματα—χρησιμοποιώντας το Aspose.Page API. Αυτή η προσέγγιση είναι ιδανική για δημιουργία γραφικών στο διακομιστή, αυτοματοποιημένη δημιουργία αναφορών ή οποιοδήποτε σενάριο που απαιτεί ακριβή έλεγχο του μορφότυπου εξόδου.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για .NET;
Το Aspose.Page υποστηρίζει **30+ graphics primitives** και μπορεί να δημιουργήσει αρχεία έως **500 MB** χωρίς να φορτώνει ολόκληρο το έγγραφο στη μνήμη, παρέχοντας υψηλής απόδοσης απόδοση σε Windows, Linux και macOS. Σας δίνει πλήρη έλεγχο πάνω σε σχήματα, χρώματα και γραμμές, εξαλείφοντας την ανάγκη να γράψετε κώδικα χαμηλού επιπέδου PostScript.

- **Πλήρης έλεγχος των γραφικών** – draw shapes, set colors, and apply strokes without dealing with low‑level PS syntax.  
- **Cross‑platform** – works on Windows, Linux, and macOS runtimes.  
- **No external dependencies** – the library handles all PS generation internally.  
- **Rich documentation & examples** – get up‑and‑running quickly.

## Προαπαιτούμενα

- **Aspose.Page for .NET Library** – download and install from [here](https://releases.aspose.com/page/net/).  
- **Development Environment** – Visual Studio, VS Code, or any .NET‑compatible IDE.

## Εισαγωγή Namespaces

Το namespace `Aspose.Page` εκθέτει τις βασικές κλάσεις που θα χρειαστείτε, όπως `Document`, `Page`, `SolidBrush` και `Pen`. Εισάγετέ το πριν ξεκινήσετε τον κώδικα.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Τώρα ας χωρίσουμε το παράδειγμα σε σαφή, αριθμημένα βήματα.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφου σας

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Αντικαταστήστε `"Your Document Directory"` με το φάκελο όπου θέλετε να αποθηκευτεί το παραγόμενο αρχείο PS.

## Βήμα 2: Δημιουργήστε Ροή Εξόδου για το Έγγραφο PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Αυτή η ροή δείχνει στο **AddRectangle_outPS.ps**. Μπορείτε ελεύθερα να μετονομάσετε το αρχείο ή να αλλάξετε την τοποθεσία όπως χρειάζεται.

## Βήμα 3: Ορίστε τις Επιλογές Αποθήκευσης και Δημιουργήστε το Έγγραφο PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Εδώ λέμε στο Aspose.Page να χρησιμοποιήσει μέγεθος σελίδας A4 και να δημιουργήσει ένα έγγραφο μίας σελίδας.

## Βήμα 4: Προσθέστε Ένα Γεμισμένο Ορθογώνιο

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Ορίζουμε ένα ορθογώνιο στο (250, 100) με πλάτος 150 και ύψος 100, ορίζουμε μια πορτοκαλί βούρτσα και γεμίζουμε το σχήμα.

## Βήμα 5: Προσθέστε Ένα Περιγραμμένο Ορθογώνιο

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Δημιουργείται ένα δεύτερο ορθογώνιο πιο χαμηλά στη σελίδα, αυτή τη φορά με κόκκινη γραμμή 3 σημείων.

## Βήμα 6: Κλείστε τη Σελίδα και Αποθηκεύστε το Έγγραφο

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Το κλείσιμο της σελίδας ολοκληρώνει το σχέδιο, και η μέθοδος `Save()` γράφει το αρχείο PS στο δίσκο.

## Πώς να δημιουργήσετε έγγραφο postscript .net;
Η κλάση `Document` είναι η κύρια κλάση που αντιπροσωπεύει ένα αρχείο PostScript στο Aspose.Page. Η `SaveOptions` καθορίζει ρυθμίσεις όπως το μέγεθος σελίδας και τη μορφή εξόδου του εγγράφου. Φορτώστε το αντικείμενο `Document`, διαμορφώστε τις `SaveOptions` για σελίδα A4, σχεδιάστε τα σχήματά σας με `SolidBrush` ή `Pen`, και καλέστε `document.Save()`—η πλήρης ροή εργασίας απαιτεί μόνο λίγες γραμμές κώδικα και εκτελείται σε οποιοδήποτε υποστηριζόμενο .NET runtime. Αυτό το μοτίβο σας επιτρέπει να δημιουργήσετε πλήρως συμβατά αρχεία PostScript χωρίς να αγγίζετε την ακατέργαστη σύνταξη PS.

## Πώς να δημιουργήσετε αρχείο postscript
Χρησιμοποιήστε την κλάση `SaveOptions` του Aspose.Page για να ορίσετε τη μορφή εξόδου ως PostScript (`SaveFormat.PS`). Η βιβλιοθήκη μεταβιβάζει το περιεχόμενο απευθείας σε αρχείο ή ροή μνήμης, επιτρέποντάς σας να δημιουργήσετε μεγάλα έγγραφα αποδοτικά χωρίς υπερβολική κατανάλωση μνήμης.

## Κοινά Προβλήματα & Συμβουλές

- **Incorrect file path** – Ensure `dataDir` ends with a path separator (`\\` or `/`) or use `Path.Combine`.  
- **Missing license** – In a production environment, apply your Aspose license before creating the document to avoid evaluation watermarks.  
- **Color visibility** – If the rectangle appears blank, verify that the brush or pen colors contrast with the page background.

## Συχνές Ερωτήσεις

**Q:** Μπορώ να προσαρμόσω τα χρώματα των ορθογωνίων;  
**A:** Absolutely. Change the `Color.Orange` or `Color.Red` values in the `SolidBrush` and `Pen` constructors to any `System.Drawing.Color` you prefer.

**Q:** Είναι το Aspose.Page συμβατό με άλλες μορφές εγγράφων;  
**A:** Yes. Besides PostScript, Aspose.Page also supports XPS and EPS generation.

**Q:** Πώς μπορώ να προσθέσω κείμενο στο ίδιο έγγραφο;  
**A:** Use the `TextFragment` class to place text at desired coordinates, then call `document.Draw(textFragment)`.

**Q:** Πού μπορώ να βρω επιπλέον παραδείγματα και πλήρη αναφορά API;  
**A:** Explore the documentation [here](https://reference.aspose.com/page/net/) and join the community at the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Μπορώ να δοκιμάσω το Aspose.Page πριν το αγοράσω;  
**A:** Yes, download a free trial [here](https://releases.aspose.com/). For extended evaluation, consider a [temporary license](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-06-30  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Πώς να Δημιουργήσετε Έγγραφο PostScript με το Aspose.Page για .NET](/page/net/document-creation/create-postscript-document/)
- [Προσθήκη Εικόνας σε Έγγραφο PostScript (PS) με το Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Προσθήκη Κειμένου σε Έγγραφο PostScript (PS) με το Aspose.Page](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}