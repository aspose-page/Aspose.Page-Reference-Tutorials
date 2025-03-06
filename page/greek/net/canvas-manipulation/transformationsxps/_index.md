---
title: Μετασχηματισμοί XPS με Aspose.Page για .NET
linktitle: Μετασχηματισμοί XPS
second_title: Aspose.Page .NET API
description: Μεταμορφώστε έγγραφα XPS χωρίς κόπο με το Aspose.Page για .NET. Ακολουθήστε τον βήμα προς βήμα οδηγό μας για απρόσκοπτες μεταμορφώσεις.
weight: 13
url: /el/net/canvas-manipulation/transformationsxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Μετασχηματισμοί XPS με Aspose.Page για .NET

## Εισαγωγή

Καλώς ήλθατε στον κόσμο του Aspose.Page για .NET, μιας ισχυρής βιβλιοθήκης που σας δίνει τη δυνατότητα να πραγματοποιείτε διάφορους μετασχηματισμούς σε έγγραφα XPS χωρίς κόπο. Σε αυτό το σεμινάριο, θα βουτήξουμε στη διαδικασία μετατροπής εγγράφων XPS χρησιμοποιώντας το Aspose.Page για .NET. Είτε είστε έμπειρος προγραμματιστής είτε μόλις ξεκινάτε, αυτός ο οδηγός θα σας καθοδηγήσει σε κάθε βήμα, διασφαλίζοντας ότι κατανοείτε εύκολα τις έννοιες.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:

-  Aspose.Page για .NET Library: Κάντε λήψη και εγκατάσταση της βιβλιοθήκης από[Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

- Περιβάλλον ανάπτυξης: Ρυθμίστε ένα συμβατό περιβάλλον ανάπτυξης, όπως το Visual Studio ή οποιοδήποτε άλλο εργαλείο ανάπτυξης .NET.

- Ο Κατάλογος Εγγράφων σας: Αντικαταστήστε το σύμβολο κράτησης θέσης στον κώδικα με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

Τώρα, ας μεταβούμε στο σεμινάριο!

## Εισαγωγή χώρων ονομάτων

Αρχικά, βεβαιωθείτε ότι εισάγετε τους απαραίτητους χώρους ονομάτων για να κάνετε τη Aspose.Page για λειτουργίες .NET διαθέσιμη στον κώδικά σας. Προσθέστε τους ακόλουθους χώρους ονομάτων στην αρχή του σεναρίου σας:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Βήμα 1: Δημιουργήστε ένα νέο έγγραφο XPS

```csharp
// ExStart: 1
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "Your Document Directory";

// Δημιουργία νέου εγγράφου XPS
XpsDocument doc = new XpsDocument();
```

## Βήμα 2: Δημιουργήστε έναν κύριο καμβά

```csharp
// Δημιουργήστε κύριο καμβά, κοινό για όλα τα στοιχεία της σελίδας
XpsCanvas canvas1 = doc.AddCanvas();

// Κάντε αριστερά και πάνω μετατόπιση στον κύριο καμβά
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Βήμα 3: Δημιουργήστε μια Γεωμετρία Ορθογώνιας Διαδρομής

```csharp
// Δημιουργήστε γεωμετρία διαδρομής ορθογωνίου
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## Βήμα 4: Προσθέστε ένα γέμισμα για ορθογώνια

```csharp
// Δημιουργήστε ένα γέμισμα για ορθογώνια
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Βήμα 5: Προσθέστε έναν νέο καμβά χωρίς μετασχηματισμούς

```csharp
// Προσθέστε νέο καμβά χωρίς μετασχηματισμούς στον κύριο καμβά
XpsCanvas canvas2 = canvas1.AddCanvas();

// Δημιουργήστε ορθογώνιο σε αυτόν τον καμβά και γεμίστε τον
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Βήμα 6: Προσθήκη νέου καμβά με Translate Transformation

```csharp
// Προσθέστε νέο καμβά με μετατροπή μετάφρασης στον κύριο καμβά
XpsCanvas canvas3 = canvas1.AddCanvas();

// Μεταφράστε αυτόν τον καμβά για να τοποθετήσετε ένα νέο ορθογώνιο κάτω από το προηγούμενο ορθογώνιο
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Μεταφράστε αυτόν τον καμβά στη δεξιά πλευρά της σελίδας
canvas3.RenderTransform.Translate(500, 0);

// Δημιουργήστε ορθογώνιο σε αυτόν τον καμβά και γεμίστε τον
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## Βήμα 7: Προσθέστε έναν νέο καμβά με μετασχηματισμό διπλής κλίμακας

```csharp
//Προσθέστε νέο καμβά με μετασχηματισμό διπλής κλίμακας στον κύριο καμβά
XpsCanvas canvas4 = canvas1.AddCanvas();

// Μεταφράστε αυτόν τον καμβά για να τοποθετήσετε ένα νέο ορθογώνιο κάτω από το προηγούμενο ορθογώνιο
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Κλιμακώστε αυτόν τον καμβά
canvas4.RenderTransform.Scale(2, 2);

// Δημιουργήστε ορθογώνιο σε αυτόν τον καμβά και γεμίστε τον
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## Βήμα 8: Προσθέστε έναν νέο καμβά με μετασχηματισμό περιστροφής γύρω από ένα σημείο

```csharp
// Προσθέστε νέο καμβά με περιστροφή γύρω από μετασχηματισμό σημείου στον κύριο καμβά
XpsCanvas canvas5 = canvas1.AddCanvas();

// Μεταφράστε αυτόν τον καμβά για να τοποθετήσετε ένα νέο ορθογώνιο κάτω από το προηγούμενο ορθογώνιο
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Περιστρέψτε αυτόν τον καμβά γύρω από ένα σημείο σε 45 μοίρες
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Δημιουργήστε ορθογώνιο σε αυτόν τον καμβά και γεμίστε τον
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## Βήμα 9: Αποθηκεύστε το προκύπτον έγγραφο XPS

```csharp
// Αποθηκεύστε το προκύπτον έγγραφο XPS
doc.Save(dataDir + "output1.xps");
// ExEnd: 1
```

## συμπέρασμα

Συγχαρητήρια! Μεταμορφώσατε με επιτυχία ένα έγγραφο XPS χρησιμοποιώντας το Aspose.Page για .NET. Αυτός ο οδηγός κάλυψε βασικά βήματα, από τη δημιουργία προαπαιτούμενων έως την εκτέλεση διαφόρων μετασχηματισμών. Πειραματιστείτε με αυτές τις τεχνικές και ξεκλειδώστε πλήρως τις δυνατότητες του Aspose.Page για .NET στα έργα σας.

## Συχνές ερωτήσεις

### Ε1: Είναι το Aspose.Page για .NET συμβατό με όλα τα περιβάλλοντα ανάπτυξης .NET;

A1: Ναι, το Aspose.Page για .NET έχει σχεδιαστεί για να λειτουργεί απρόσκοπτα με διάφορα περιβάλλοντα ανάπτυξης .NET, συμπεριλαμβανομένου του Visual Studio.

### Ε2: Πού μπορώ να βρω επιπλέον παραδείγματα και τεκμηρίωση για το Aspose.Page για .NET;

 A2: Επισκεφθείτε το[Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/) για πλήρη τεκμηρίωση και παραδείγματα.

### Ε3: Μπορώ να δοκιμάσω το Aspose.Page για .NET πριν από την αγορά;

 A3: Ναι, μπορείτε να εξερευνήσετε μια δωρεάν δοκιμαστική έκδοση κάνοντας μια επίσκεψη[Aspose.Page Δωρεάν δοκιμή](https://releases.aspose.com/).

### Ε4: Πώς μπορώ να αποκτήσω μια προσωρινή άδεια χρήσης για το Aspose.Page για .NET;

 A4: Λάβετε μια προσωρινή άδεια με μια επίσκεψη[Προσωρινή Άδεια](https://purchase.aspose.com/temporary-license/).

### Ε5: Πού μπορώ να αγοράσω το Aspose.Page για .NET;

 A5: Αγορά Aspose.Page για .NET στο[Aspose.Page Αγορά](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
