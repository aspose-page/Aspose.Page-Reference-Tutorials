---
date: 2026-07-19
description: Μάθετε πώς να δημιουργήσετε έγγραφο XPS .NET και να προσθέσετε ένα rectangle
  χρησιμοποιώντας το Aspose.Page για .NET σε έναν σύντομο οδηγό βήμα‑βήμα.
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: Προσθήκη Rectangle σε έγγραφο XPS
og_description: Δημιουργήστε έγγραφο XPS .NET γρήγορα. Αυτό το tutorial δείχνει πώς
  να προσθέσετε ένα rectangle σε αρχείο XPS χρησιμοποιώντας το Aspose.Page για .NET,
  με σαφή code και tips.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: Δημιουργία εγγράφου XPS .NET – Προσθήκη Rectangle με Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: Δημιουργία εγγράφου XPS .NET – Προσθήκη Rectangle με Aspose.Page
url: /el/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία εγγράφου XPS .NET – Προσθήκη ορθογωνίου με Aspose.Page

## Εισαγωγή

Σε αυτό το tutorial θα μάθετε πώς να **δημιουργήσετε έγγραφο XPS .NET** και να σχεδιάσετε ένα ορθογώνιο μέσα του χρησιμοποιώντας το Aspose.Page for .NET. Είτε δημιουργείτε μια μηχανή αναφορών, ένα εκτυπώσιμο τιμολόγιο ή ένα προσαρμοσμένο επίπεδο γραφικών, η δυνατότητα δημιουργίας αρχείων XPS προγραμματιστικά σας δίνει πλήρη έλεγχο πάνω στη διάταξη και την πιστότητα. Ακολουθήστε τα παρακάτω βήματα και θα έχετε ένα έτοιμο προς χρήση αρχείο XPS σε λίγα λεπτά.

## Γρήγορες Απαντήσεις
- **Ποιος είναι ο κύριος στόχος;** Δημιουργία εγγράφου XPS .NET και προσθήκη σχήματος ορθογωνίου.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page for .NET (διαθέσιμη για λήψη από την επίσημη ιστοσελίδα).  
- **Χρειάζομαι άδεια για δοκιμές;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **Πόσο διαρκεί η υλοποίηση;** Περίπου 5‑10 λεπτά για ένα βασικό ορθογώνιο.

## Τι είναι το Aspose.Page for .NET;
Το Aspose.Page for .NET είναι ένα υψηλής απόδοσης, πλήρως διαχειριζόμενο API που επιτρέπει στους προγραμματιστές να δημιουργούν, να επεξεργάζονται και να αποδίδουν έγγραφα XPS (XML Paper Specification) προγραμματιστικά χωρίς εξωτερικά εξαρτήματα. Προσφέρει ένα πλούσιο αντικειμενοστραφές μοντέλο για σχεδίαση σχημάτων, κειμένου και εικόνων, και υποστηρίζει προχωρημένες λειτουργίες όπως διαχείριση χρωμάτων, συμπίεση και μετατροπή σε PDF, καθιστώντας το κατάλληλο για ένα ευρύ φάσμα σεναρίων δημιουργίας εγγράφων.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για τη δημιουργία εγγράφου XPS .NET;
Το Aspose.Page υποστηρίζει **30+ δυνατότητες XPS**—συμπεριλαμβανομένων των διανυσματικών γραφικών, της διάταξης κειμένου και της διαχείρισης χρωμάτων—και μπορεί να δημιουργήσει αρχεία έως **500 MB** χωρίς να φορτώνει ολόκληρο το έγγραφο στη μνήμη. Αυτή η ποσοτικοποιημένη δυνατότητα εξασφαλίζει ομαλή απόδοση ακόμη και για μεγάλες εργασίες εκτύπωσης.

## Προαπαιτούμενα

Πριν ξεκινήσετε αυτό το tutorial, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:

1. Βιβλιοθήκη Aspose.Page for .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Page for .NET στο περιβάλλον ανάπτυξής σας. Μπορείτε να τη κατεβάσετε [εδώ](https://releases.aspose.com/page/net/).
2. Κατάλογος εγγράφων: Δημιουργήστε έναν φάκελο όπου θα αποθηκεύετε τα έγγραφα XPS.

## Εισαγωγή ονοματοχώρων

Στην εφαρμογή .NET, συμπεριλάβετε τους απαραίτητους ονοματοχώρους για να χρησιμοποιήσετε τις λειτουργίες του Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Πώς να προσθέσετε ένα ορθογώνιο σε έγγραφο XPS στο .NET;

Φορτώστε το έγγραφο XPS, δημιουργήστε ένα αντικείμενο `Graphics`, ορίστε ένα `RectangleF` με το επιθυμητό μέγεθος και καλέστε `DrawRectangle`. Αυτή η ακολουθία σχεδιάζει ένα ορθογώνιο σε μία γραμμή κώδικα και διαχειρίζεται αυτόματα την κλιμάκωση DPI. Για τυπικές σελίδες A4, ένα ορθογώνιο 200 × 100 pt εμφανίζεται κεντραρισμένο χωρίς επιπλέον υπολογισμούς.

### Βήμα 1: Ορισμός του καταλόγου εγγράφων

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### Βήμα 2: Δημιουργία νέου εγγράφου XPS

Η κλάση `XpsDocument` αντιπροσωπεύει το αρχείο XPS που δημιουργείτε και παρέχει μεθόδους για προσθήκη σελίδων, γραφικών και άλλων πόρων.

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### Βήμα 3: Προσθήκη ορθογωνίου

Το `XpsPath` ορίζει ένα αντικείμενο διαδρομής που μπορεί να σχεδιαστεί μέσα στο έγγραφο XPS, επιτρέποντάς σας να ορίσετε γεωμετρία, περίγραμμα, γέμισμα και άλλες οπτικές ιδιότητες.

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### Βήμα 4: Αποθήκευση του εγγράφου

Η μέθοδος `Save` γράφει το κατασκευασμένο έγγραφο XPS στη συγκεκριμένη διαδρομή αρχείου στο δίσκο.

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Συγχαρητήρια! Έχετε προσθέσει επιτυχώς ένα ορθογώνιο σε έγγραφο XPS χρησιμοποιώντας το Aspose.Page for .NET.

## Συχνά Προβλήματα και Συμβουλές

- **Λείπουν γραμματοσειρές:** Βεβαιωθείτε ότι οι γραμματοσειρές που αναφέρετε είναι εγκατεστημένες στον διακομιστή· διαφορετικά το Aspose.Page θα αντικαταστήσει με προεπιλεγμένη γραμματοσειρά, η οποία μπορεί να αλλάξει τη διάταξη.  
- **Μεγάλα έγγραφα:** Κατά τη δημιουργία αρχείων μεγαλύτερων από 200 MB, σκεφτείτε να καλέσετε `document.SaveOptions.Compress = true` για μείωση της χρήσης μνήμης.  
- **Σύστημα συντεταγμένων:** Το XPS χρησιμοποιεί μονάδες σημείων (1/72 ίντσα). Θυμηθείτε να μετατρέψετε τα pixel σε σημεία εάν εργάζεστε με διαστάσεις βάσει οθόνης.

## Συχνές Ερωτήσεις

**Q: Είναι το Aspose.Page συμβατό με όλες τις εφαρμογές .NET;**  
A: Ναι, το Aspose.Page λειτουργεί άψογα με εφαρμογές .NET σε desktop, web και cloud.

**Q: Πού μπορώ να βρω την τεκμηρίωση για το Aspose.Page for .NET;**  
A: Η πλήρης αναφορά API είναι διαθέσιμη [εδώ](https://reference.aspose.com/page/net/).

**Q: Μπορώ να δοκιμάσω το Aspose.Page for .NET δωρεάν πριν την αγορά;**  
A: Ναι, μπορείτε να λάβετε δωρεάν δοκιμή [εδώ](https://releases.aspose.com/).

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page for .NET;**  
A: Επισκεφθείτε [αυτόν τον σύνδεσμο](https://purchase.aspose.com/temporary-license/) για να αποκτήσετε προσωρινή άδεια.

**Q: Πού μπορώ να βρω υποστήριξη κοινότητας ή να θέσω ερωτήσεις σχετικά με το Aspose.Page for .NET;**  
A: Επισκεφθείτε το [φόρουμ Aspose.Page](https://forum.aspose.com/c/page/39) για υποστήριξη κοινότητας.

---

**Τελευταία ενημέρωση:** 2026-07-19  
**Δοκιμή με:** Aspose.Page for .NET 24.9  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Δημιουργία εγγράφου XPS με Aspose.Page for .NET](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – Σχεδίαση Σχημάτων](/page/net/drawing-shapes/)
- [Προσθήκη κειμένου σε έγγραφο XPS με Aspose.Page for .NET](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}