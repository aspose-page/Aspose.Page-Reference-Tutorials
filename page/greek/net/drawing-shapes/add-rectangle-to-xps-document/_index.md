---
title: Προσθήκη Rectangle στο έγγραφο XPS με το Aspose.Page για .NET
linktitle: Προσθήκη ορθογώνιου στο έγγραφο XPS
second_title: Aspose.Page .NET API
description: Βελτιώστε τη δημιουργία εγγράφων με το Aspose.Page για .NET. Μάθετε πώς να προσθέτετε ορθογώνια σε έγγραφα XPS σε αυτό το βήμα προς βήμα σεμινάριο.
weight: 13
url: /el/net/drawing-shapes/add-rectangle-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη Rectangle στο έγγραφο XPS με το Aspose.Page για .NET

## Εισαγωγή

Το Aspose.Page για .NET είναι μια ισχυρή βιβλιοθήκη που παρέχει μια ποικιλία δυνατοτήτων για εργασία με έγγραφα XPS (XML Paper Specification) σε εφαρμογές .NET. Σε αυτό το σεμινάριο, θα επικεντρωθούμε στην προσθήκη ενός ορθογωνίου σε ένα έγγραφο XPS χρησιμοποιώντας το Aspose.Page για .NET. Ακολουθήστε αυτόν τον οδηγό βήμα προς βήμα για να βελτιώσετε τη διαδικασία δημιουργίας εγγράφων.

## Προαπαιτούμενα

Πριν ξεκινήσετε με αυτό το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1.  Aspose.Page για .NET Library: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Page για .NET στο περιβάλλον ανάπτυξης σας. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/page/net/).

2. Κατάλογος εγγράφων: Ρυθμίστε έναν κατάλογο όπου θέλετε να αποθηκεύσετε τα έγγραφά σας XPS.

## Εισαγωγή χώρων ονομάτων

Στην εφαρμογή σας .NET, συμπεριλάβετε τους απαραίτητους χώρους ονομάτων για να χρησιμοποιήσετε τις λειτουργίες Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Βήμα 1: Ορίστε τον Κατάλογο εγγράφων

```csharp
// ExStart: 3
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "Your Document Directory";
// ExEnd: 3
```

## Βήμα 2: Δημιουργήστε ένα νέο έγγραφο XPS

```csharp
// ExStart: 4
// Δημιουργία νέου εγγράφου XPS
XpsDocument doc = new XpsDocument();
// ExEnd: 4
```

## Βήμα 3: Προσθέστε ένα ορθογώνιο

```csharp
// ExStart: 5
// CMYK (μπλε) μονόχρωμο παραλληλόγραμμο χαραγμένο κάτω αριστερά
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// Παράταση: 5
```

## Βήμα 4: Αποθηκεύστε το έγγραφο

```csharp
// ExStart: 6
// Αποθηκεύστε το προκύπτον έγγραφο XPS
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// Παράταση: 6
```

Συγχαρητήρια! Προσθέσατε με επιτυχία ένα ορθογώνιο σε ένα έγγραφο XPS χρησιμοποιώντας το Aspose.Page για .NET.

## συμπέρασμα

Το Aspose.Page για .NET απλοποιεί τις εργασίες χειρισμού εγγράφων, επιτρέποντας στους προγραμματιστές να δημιουργούν και να τροποποιούν έγγραφα XPS χωρίς κόπο. Αυτός ο οδηγός βήμα προς βήμα δείχνει πώς να προσθέσετε ένα ορθογώνιο στο έγγραφό σας XPS, παρέχοντας μια σταθερή βάση για περαιτέρω εξερεύνηση.

## Συχνές ερωτήσεις

### Ε1: Είναι το Aspose.Page συμβατό με όλες τις εφαρμογές .NET;

A1: Ναι, το Aspose.Page έχει σχεδιαστεί για να λειτουργεί απρόσκοπτα με όλες τις εφαρμογές .NET.

### Ε2: Πού μπορώ να βρω την τεκμηρίωση για το Aspose.Page για .NET;

 A2: Η τεκμηρίωση είναι διαθέσιμη[εδώ](https://reference.aspose.com/page/net/).

### Ε3: Μπορώ να δοκιμάσω το Aspose.Page για .NET δωρεάν πριν το αγοράσω;

 A3: Ναι, μπορείτε να λάβετε μια δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).

### Ε4: Πώς μπορώ να αποκτήσω μια προσωρινή άδεια χρήσης για το Aspose.Page για .NET;

 Α4: Επίσκεψη[αυτός ο σύνδεσμος](https://purchase.aspose.com/temporary-license/) για την απόκτηση προσωρινής άδειας.

### Ε5: Πού μπορώ να αναζητήσω υποστήριξη από την κοινότητα ή να κάνω ερωτήσεις σχετικά με το Aspose.Page για .NET;

 A5: Επισκεφθείτε το[Aspose.Page φόρουμ](https://forum.aspose.com/c/page/39) για κοινοτική υποστήριξη.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
