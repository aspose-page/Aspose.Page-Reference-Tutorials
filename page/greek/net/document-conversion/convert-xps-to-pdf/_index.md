---
title: Μετατροπή XPS σε PDF με το Aspose.Page για .NET
linktitle: Μετατροπή XPS σε PDF
second_title: Aspose.Page .NET API
description: Μετατρέψτε εύκολα XPS σε PDF σε .NET με το Aspose.Page. Κατεβάστε τη βιβλιοθήκη, εξερευνήστε την τεκμηρίωση και αποκτήστε μια δωρεάν δοκιμή.
weight: 11
url: /el/net/document-conversion/convert-xps-to-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Μετατροπή XPS σε PDF με το Aspose.Page για .NET

## Εισαγωγή

Σε αυτό το σεμινάριο, θα εμβαθύνουμε στη διαδικασία μετατροπής εγγράφων XPS (XML Paper Specification) σε PDF (Portable Document Format) χρησιμοποιώντας την ισχυρή βιβλιοθήκη Aspose.Page για .NET. Το Aspose.Page για .NET παρέχει ένα ισχυρό σύνολο δυνατοτήτων για εργασία με αρχεία XPS, επιτρέποντας στους προγραμματιστές να τα μετατρέπουν απρόσκοπτα σε μορφή PDF με διάφορες επιλογές προσαρμογής.

## Προαπαιτούμενα

Προτού ξεκινήσουμε αυτό το ταξίδι μετατροπής, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

-  Aspose.Page για .NET Library: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Page για .NET στο περιβάλλον ανάπτυξης σας. Μπορείτε να το κατεβάσετε από το[Τεκμηρίωση Aspose.Page](https://reference.aspose.com/page/net/).

- Περιβάλλον ανάπτυξης: Ρυθμίστε ένα περιβάλλον ανάπτυξης .NET με το Visual Studio ή οποιοδήποτε άλλο συμβατό IDE.

- Έγγραφο XPS: Προετοιμάστε το έγγραφο XPS που θέλετε να μετατρέψετε σε PDF. Αυτό θα μπορούσε να είναι το δείγμα αρχείου XPS που είναι αποθηκευμένο σε έναν καθορισμένο κατάλογο.

## Εισαγωγή χώρων ονομάτων

Πριν βουτήξουμε στον κώδικα, ας εισαγάγουμε τους απαραίτητους χώρους ονομάτων για να κάνουμε τη Aspose.Page για λειτουργίες .NET προσβάσιμη στον κώδικά μας:

```csharp
using Aspose.Page.XPS;
```

## Βήμα 1: Εκκίνηση του Καταλόγου Εγγράφων

```csharp
string dataDir = "Your Document Directory";
```

Αντικαταστήστε το "Your Document Directory" με τη διαδρομή προς τον κατάλογο που περιέχει το έγγραφό σας XPS.

## Βήμα 2: Αρχικοποιήστε τις ροές PDF και XPS

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Ανοίξτε ροές τόσο για το αρχείο PDF εξόδου όσο και για το αρχείο εισόδου XPS. Βεβαιωθείτε ότι έχετε ορίσει τις κατάλληλες διαδρομές αρχείων.

## Βήμα 3: Φόρτωση εγγράφου XPS

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Φορτώστε το έγγραφο XPS χρησιμοποιώντας τη βιβλιοθήκη Aspose.Page για .NET.

## Βήμα 4: Εκκίνηση των επιλογών αποθήκευσης PDF

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

Ρυθμίστε τις επιλογές αποθήκευσης PDF, συμπεριλαμβανομένων παραμέτρων όπως το επίπεδο ποιότητας JPEG, η συμπίεση εικόνας, η συμπίεση κειμένου και συγκεκριμένοι αριθμοί σελίδων που θα συμπεριληφθούν.

## Βήμα 5: Δημιουργήστε συσκευή απόδοσης PDF

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

Δημιουργήστε μια συσκευή απόδοσης για τη μορφή PDF χρησιμοποιώντας τη βιβλιοθήκη Aspose.Page για .NET.

## Βήμα 6: Αποθήκευση εγγράφου σε PDF

```csharp
document.Save(device, options);
```

Αποθηκεύστε το έγγραφο XPS σε PDF χρησιμοποιώντας την καθορισμένη συσκευή απόδοσης και επιλογές.

## συμπέρασμα

Συγχαρητήρια! Μετατρέψατε επιτυχώς ένα έγγραφο XPS σε PDF χρησιμοποιώντας το Aspose.Page για .NET. Αυτή η ευέλικτη βιβλιοθήκη παρέχει στους προγραμματιστές ένα ισχυρό σύνολο εργαλείων για το χειρισμό διαφόρων μορφών εγγράφων χωρίς κόπο.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να μετατρέψω πολλά αρχεία XPS σε ένα μόνο PDF χρησιμοποιώντας το Aspose.Page για .NET;

A1: Ναι, μπορείτε να κάνετε επαναφορά πολλών αρχείων XPS και να ακολουθήσετε τα ίδια βήματα για να τα συγχωνεύσετε σε ένα μόνο PDF.

### Ε2: Υπάρχουν άλλες μορφές εξόδου που υποστηρίζονται από το Aspose.Page για .NET;

A2: Ναι, το Aspose.Page για .NET υποστηρίζει διάφορες μορφές εξόδου, συμπεριλαμβανομένων των TIFF, JPEG, PNG και άλλων.

### Ε3: Πώς μπορώ να προσαρμόσω την εμφάνιση του εγγράφου PDF που έχει μετατραπεί;

A3: Μπορείτε να τροποποιήσετε τις παραμέτρους των αντικειμένων επιλογών, όπως η συμπίεση εικόνας και η συμπίεση κειμένου, για να επιτύχετε την επιθυμητή εμφάνιση.

### Ε4: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Page για .NET;

 A4: Ναι, μπορείτε να εξερευνήσετε τις δυνατότητες του Aspose.Page για .NET αποκτώντας μια δωρεάν δοκιμή από[εδώ](https://releases.aspose.com/).

### Ε5: Πού μπορώ να λάβω υποστήριξη κοινότητας για το Aspose.Page για .NET;

 A5: Επισκεφθείτε το[Aspose.Page φόρουμ](https://forum.aspose.com/c/page/39) για κοινοτικές συζητήσεις και υποστήριξη.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
