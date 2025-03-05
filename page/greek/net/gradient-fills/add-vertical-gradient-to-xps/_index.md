---
title: Προσθήκη Vertical Gradient στο XPS με το Aspose.Page για .NET
linktitle: Προσθήκη Vertical Gradient στο XPS
second_title: Aspose.Page .NET API
description: Μάθετε πώς να βελτιώνετε έγγραφα XPS με κάθετες διαβαθμίσεις χρησιμοποιώντας το Aspose.Page για .NET. Ακολουθήστε τον βήμα προς βήμα οδηγό μας για απρόσκοπτη ενσωμάτωση.
type: docs
weight: 15
url: /el/net/gradient-fills/add-vertical-gradient-to-xps/
---
## Εισαγωγή

Καλώς ήρθατε σε αυτό το βήμα προς βήμα σεμινάριο σχετικά με τον τρόπο προσθήκης μιας κατακόρυφης διαβάθμισης σε ένα έγγραφο XPS χρησιμοποιώντας το Aspose.Page για .NET. Το Aspose.Page είναι ένα ισχυρό API που σας επιτρέπει να εργάζεστε με αρχεία XPS (XML Paper Specification) στις εφαρμογές σας .NET. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία δημιουργίας ενός νέου εγγράφου XPS, προσθήκης κάθετης διαβάθμισης σε μια διαδρομή και αποθήκευσης του αποτελέσματος.

## Προαπαιτούμενα

Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

-  Aspose.Page για .NET Library: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Page για .NET στο περιβάλλον ανάπτυξης σας. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/page/net/).

- Περιβάλλον ανάπτυξης: Ρυθμίστε ένα περιβάλλον ανάπτυξης .NET με το IDE που προτιμάτε, όπως το Visual Studio.

Τώρα, ας ξεκινήσουμε με την προσθήκη μιας κατακόρυφης διαβάθμισης σε ένα έγγραφο XPS χρησιμοποιώντας το Aspose.Page για .NET.

## Εισαγωγή χώρων ονομάτων

Στην εφαρμογή .NET, συμπεριλάβετε τους απαραίτητους χώρους ονομάτων για πρόσβαση σε κλάσεις και μεθόδους Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων σας

Πριν ξεκινήσετε, ορίστε τη διαδρομή προς τον κατάλογο εγγράφων σας όπου θέλετε να αποθηκεύσετε το έγγραφο XPS που προκύπτει.

```csharp
// ExStart: 3
string dataDir = "Your Document Directory";
// ExEnd: 3
```

## Βήμα 2: Δημιουργήστε ένα νέο έγγραφο XPS

Αρχικοποιήστε ένα νέο έγγραφο XPS χρησιμοποιώντας τον ακόλουθο κώδικα:

```csharp
// ExStart: 4
XpsDocument doc = new XpsDocument();
// ExEnd: 4
```

## Βήμα 3: Ορίστε στάσεις κλίσης

Δημιουργήστε μια λίστα με στάσεις κλίσης, καθορίζοντας το χρώμα και τη θέση για κάθε στάση. Σε αυτό το παράδειγμα, ορίζουμε μια κατακόρυφη κλίση με πέντε στάσεις.

```csharp
// ExStart: 5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// Παράταση: 5
```

## Βήμα 4: Δημιουργήστε μια διαδρομή με Gradient

Καθορίστε ένα μονοπάτι προσδιορίζοντας τη γεωμετρία του και εφαρμόστε ένα πινέλο γραμμικής κλίσης σε αυτό.

```csharp
// ExStart: 6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// Παράταση: 6
```

## Βήμα 5: Αποθηκεύστε το προκύπτον έγγραφο XPS

Αποθηκεύστε το τροποποιημένο έγγραφο XPS στον καθορισμένο κατάλογο.

```csharp
// ExStart: 7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// Παράταση: 7
```

Συγχαρητήρια! Προσθέσατε με επιτυχία μια κατακόρυφη διαβάθμιση σε ένα έγγραφο XPS χρησιμοποιώντας το Aspose.Page για .NET.

## συμπέρασμα

Σε αυτό το σεμινάριο, εξερευνήσαμε πώς να αξιοποιήσουμε το Aspose.Page για .NET για να βελτιώσουμε έγγραφα XPS με κάθετες διαβαθμίσεις. Το Aspose.Page απλοποιεί πολύπλοκες εργασίες, παρέχοντας στους προγραμματιστές έναν απρόσκοπτο τρόπο χειρισμού αρχείων XPS στις εφαρμογές τους .NET.

## Συχνές ερωτήσεις

### Ε1: Είναι το Aspose.Page συμβατό με το Visual Studio 2019;

A1: Ναι, το Aspose.Page είναι συμβατό με το Visual Studio 2019. Βεβαιωθείτε ότι έχετε εγκαταστήσει τη σωστή έκδοση της βιβλιοθήκης.

### Ε2: Μπορώ να χρησιμοποιήσω το Aspose.Page για εμπορικά έργα;

 A2: Ναι, το Aspose.Page μπορεί να χρησιμοποιηθεί για εμπορικά έργα. Επίσκεψη[εδώ](https://purchase.aspose.com/buy) για να εξερευνήσετε τις επιλογές αδειοδότησης.

### Ε3: Υπάρχει διαθέσιμη δωρεάν δοκιμή;

 A3: Ναι, μπορείτε να λάβετε μια δωρεάν δοκιμή του Aspose.Page[εδώ](https://releases.aspose.com/).

### Ε4: Πού μπορώ να βρω την τεκμηρίωση του Aspose.Page;

 A4: Η τεκμηρίωση είναι διαθέσιμη[εδώ](https://reference.aspose.com/page/net/).

### Ε5: Πώς μπορώ να λάβω υποστήριξη ή να κάνω ερωτήσεις;

 A5: Επισκεφθείτε το[Aspose.Page φόρουμ](https://forum.aspose.com/c/page/39) για κοινοτική υποστήριξη.