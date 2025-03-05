---
title: Προσθήκη Circle Ellipse στο έγγραφο XPS με το Aspose.Page για .NET
linktitle: Προσθήκη Circle Ellipse στο έγγραφο XPS
second_title: Aspose.Page .NET API
description: Βελτιώστε τα έγγραφα XPS με ζωντανές ακτινικές διαβαθμίσεις χρησιμοποιώντας το Aspose.Page για .NET. Ακολουθήστε τον βήμα προς βήμα οδηγό μας για εντυπωσιακά οπτικά εφέ.
type: docs
weight: 11
url: /el/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---
## Εισαγωγή

Η δημιουργία οπτικά ελκυστικών εγγράφων XPS είναι μια κοινή απαίτηση σε διάφορες εφαρμογές. Το Aspose.Page για .NET παρέχει ένα ισχυρό σύνολο δυνατοτήτων για τον αποτελεσματικό χειρισμό εγγράφων XPS. Σε αυτό το σεμινάριο, θα επικεντρωθούμε στην προσθήκη μιας έλλειψης κύκλου σε ένα έγγραφο XPS χρησιμοποιώντας το Aspose.Page για .NET. Ακολουθήστε τα παρακάτω βήματα για να βελτιώσετε τα έγγραφά σας XPS με ζωντανές ακτινικές διαβαθμίσεις.

## Προαπαιτούμενα

Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

-  Εγκατεστημένο το Aspose.Page για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/page/net/).
- Ένα περιβάλλον ανάπτυξης, κατά προτίμηση Visual Studio ή οποιοδήποτε άλλο εργαλείο ανάπτυξης .NET.
- Βασικές γνώσεις προγραμματισμού C#.

## Εισαγωγή χώρων ονομάτων

Για να ξεκινήσετε, συμπεριλάβετε τους απαραίτητους χώρους ονομάτων στον κώδικα C#:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Τώρα, ας αναλύσουμε το παράδειγμα σε πολλά βήματα:

## Βήμα 1: Ρυθμίστε το έγγραφο

```csharp
// ExStart: 1
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "Your Document Directory";
// Δημιουργία νέου εγγράφου XPS
XpsDocument doc = new XpsDocument();
```

Εδώ, αρχικοποιούμε ένα νέο έγγραφο XPS χρησιμοποιώντας το Aspose.Page για .NET.

## Βήμα 2: Ορίστε την έλλειψη ακτινικής κλίσης

```csharp
// Ακτινωτή διαβάθμιση γραμμωμένη έλλειψη κάτω αριστερά
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

Αυτό το βήμα περιλαμβάνει τον καθορισμό μιας ακτινικής διαβάθμισης έλλειψης με διάφορες χρωματικές στάσεις.

## Βήμα 3: Ρυθμίστε το Radial Gradient Brush

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

Εδώ, ρυθμίσαμε την διαδρομή της έλλειψης σε μια ακτινωτή ντεγκραντέ βούρτσα, παρέχοντάς της τις απαραίτητες παραμέτρους.

## Βήμα 4: Προσαρμόστε το πάχος του Stroke

```csharp
path.StrokeThickness = 12f;
```

Αυτό το βήμα περιλαμβάνει προσαρμογή του πάχους της διαδρομής για καλύτερη οπτικοποίηση.

## Βήμα 5: Αποθηκεύστε το προκύπτον έγγραφο XPS

```csharp
// Αποθηκεύστε το προκύπτον έγγραφο XPS
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// ExEnd: 1
```

Τέλος, αποθηκεύστε το τροποποιημένο έγγραφο XPS στην επιθυμητή θέση.

## συμπέρασμα

Συγχαρητήρια! Προσθέσατε με επιτυχία μια κυκλική έλλειψη με ακτινικές διαβαθμίσεις στο έγγραφό σας XPS χρησιμοποιώντας το Aspose.Page για .NET. Πειραματιστείτε με διαφορετικές παραμέτρους και χρώματα για να επιτύχετε τα επιθυμητά οπτικά εφέ στα έγγραφά σας.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να χρησιμοποιήσω το Aspose.Page για .NET με άλλες μορφές εγγράφων;

A1: Το Aspose.Page για .NET ασχολείται συγκεκριμένα με τη διαχείριση εγγράφων XPS. Για άλλες μορφές, εξετάστε το ενδεχόμενο να χρησιμοποιήσετε σχετικές βιβλιοθήκες Aspose.

### Ε2: Είναι διαθέσιμη μια προσωρινή άδεια για σκοπούς δοκιμής;

 A2: Ναι, μπορείτε να αποκτήσετε μια προσωρινή άδεια για δοκιμές επισκεπτόμενοι[αυτός ο σύνδεσμος](https://purchase.aspose.com/temporary-license/).

### Ε3: Πού μπορώ να βρω πρόσθετη βοήθεια και συζητήσεις;

 A3: Επισκεφθείτε το[Aspose.Page φόρουμ](https://forum.aspose.com/c/page/39) για κοινοτική υποστήριξη και συζητήσεις.

### Ε4: Υπάρχουν διαθέσιμα δείγματα εγγράφων για αναφορά;

 A4: Εξερευνήστε το[τεκμηρίωση](https://reference.aspose.com/page/net/) για ολοκληρωμένα παραδείγματα και οδηγίες.

### Ε5: Μπορώ να αγοράσω το Aspose.Page για .NET;

 A5: Ναι, μπορείτε να αγοράσετε τη βιβλιοθήκη[εδώ](https://purchase.aspose.com/buy).