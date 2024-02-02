---
title: Προσθέστε Horizontal Gradient στο XPS με το Aspose.Page για .NET
linktitle: Προσθήκη Horizontal Gradient στο XPS
second_title: Aspose.Page .NET API
description: Μάθετε πώς να προσθέτετε εκπληκτικές οριζόντιες διαβαθμίσεις στα έγγραφά σας XPS χρησιμοποιώντας το Aspose.Page για .NET. Αυξήστε την οπτική απήχηση χωρίς κόπο.
type: docs
weight: 13
url: /el/net/gradient-fills/add-horizontal-gradient-to-xps/
---
## Εισαγωγή

Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να βελτιώσετε έγγραφα XPS προσθέτοντας μια οριζόντια κλίση χρησιμοποιώντας το Aspose.Page για .NET. Το Aspose.Page για .NET είναι μια ισχυρή βιβλιοθήκη που παρέχει απρόσκοπτη διαχείριση εγγράφων XPS (XML Paper Specification) σε εφαρμογές .NET. Η προσθήκη διαβαθμίσεων μπορεί να προσελκύσει οπτικά τα έγγραφά σας και αυτός ο οδηγός θα σας καθοδηγήσει στη διαδικασία βήμα προς βήμα.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1.  Aspose.Page για .NET Library: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Page για .NET στο περιβάλλον ανάπτυξης σας. Μπορείτε να το κατεβάσετε από το[Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

2. Περιβάλλον ανάπτυξης: Ρυθμίστε ένα κατάλληλο περιβάλλον ανάπτυξης, συμπεριλαμβανομένου ενός προγράμματος επεξεργασίας κώδικα όπως το Visual Studio.

## Εισαγωγή χώρων ονομάτων

Ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων στο έργο σας. Αυτοί οι χώροι ονομάτων είναι απαραίτητοι για την εργασία με το Aspose.Page για .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Τώρα, ας αναλύσουμε το παρεχόμενο παράδειγμα σε πολλά βήματα.

## Βήμα 1: Ορίστε τη διαδρομή καταλόγου εγγράφων

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

## Βήμα 3: Αρχικοποιήστε τις στάσεις κλίσης

```csharp
// ExStart: 5
// Εκκίνηση λίστας XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// Παράταση: 5
```

## Βήμα 4: Δημιουργήστε μια νέα διαδρομή

```csharp
// ExStart: 6
//Δημιουργήστε νέα διαδρομή ορίζοντας τη γεωμετρία σε συντομογραφία
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// Παράταση: 6
```

## Βήμα 5: Αποθηκεύστε το προκύπτον έγγραφο XPS

```csharp
// ExStart: 7
// Αποθηκεύστε το προκύπτον έγγραφο XPS
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// Παράταση: 7
```

Τώρα, προσθέσατε με επιτυχία μια οριζόντια διαβάθμιση στο έγγραφό σας XPS χρησιμοποιώντας το Aspose.Page για .NET.

## συμπέρασμα

Η βελτίωση των εγγράφων XPS με διαβαθμίσεις όχι μόνο βελτιώνει την οπτική τους έλξη, αλλά παρέχει επίσης μια πιο ελκυστική εμπειρία χρήστη. Το Aspose.Page για .NET απλοποιεί αυτή τη διαδικασία, επιτρέποντάς σας να επιτύχετε επαγγελματικά αποτελέσματα χωρίς κόπο.

## Συχνές ερωτήσεις

### Ε1: Πού μπορώ να βρω την τεκμηρίωση του Aspose.Page για .NET;

 A1: Μπορείτε να βρείτε την τεκμηρίωση[εδώ](https://reference.aspose.com/page/net/).

### Ε2: Πώς μπορώ να κατεβάσω το Aspose.Page για .NET;

 A2: Μπορείτε να κάνετε λήψη της βιβλιοθήκης από το[Aspose.Page για σελίδα λήψης .NET](https://releases.aspose.com/page/net/).

### Ε3: Πού μπορώ να αγοράσω το Aspose.Page για .NET;

 A3: Μπορείτε να αγοράσετε το Aspose.Page για .NET από το[σελίδα αγοράς](https://purchase.aspose.com/buy).

### Ε4: Υπάρχει διαθέσιμη δωρεάν δοκιμή;

 A4: Ναι, μπορείτε να λάβετε δωρεάν δοκιμή από[εδώ](https://releases.aspose.com/).

### Ε5: Πώς μπορώ να αποκτήσω μια προσωρινή άδεια χρήσης για το Aspose.Page για .NET;

 A5: Μπορείτε να αποκτήσετε προσωρινή άδεια από[αυτός ο σύνδεσμος](https://purchase.aspose.com/temporary-license/).