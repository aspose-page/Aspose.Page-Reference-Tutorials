---
title: Αλλαγή τιμών με το Aspose.Page για .NET
linktitle: Αλλάζω αξίες
second_title: Aspose.Page .NET API
description: Κύριος χειρισμός αρχείων EPS με το Aspose.Page για .NET. Αλλάξτε τις τιμές μεταδεδομένων XMP χωρίς κόπο.
weight: 17
url: /el/net/eps-metadata-management/modify-eps-metadata-change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αλλαγή τιμών με το Aspose.Page για .NET

## Εισαγωγή

Στον δυναμικό κόσμο της επεξεργασίας εγγράφων, το Aspose.Page για .NET ξεχωρίζει ως ένα ισχυρό εργαλείο, που προσφέρει στους προγραμματιστές τη δυνατότητα να χειρίζονται αρχεία EPS χωρίς κόπο. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στη διαδικασία αλλαγής τιμών στα αρχεία EPS χρησιμοποιώντας το Aspose.Page για .NET. Είτε είστε έμπειρος προγραμματιστής είτε είστε περίεργοι αρχάριοι, αυτός ο οδηγός βήμα προς βήμα θα σας εξοπλίσει με τις δεξιότητες που απαιτούνται για την αποτελεσματική τροποποίηση των μεταδεδομένων XMP στα αρχεία EPS σας.

## Προαπαιτούμενα

Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

### 1. Aspose.Page για .NET Library

Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Page για .NET στο περιβάλλον ανάπτυξης σας. Εάν όχι, μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/page/net/).

### 2. Κατάλογος Εγγράφων

Ρυθμίστε έναν κατάλογο για τα έγγραφά σας. Αυτή θα είναι η τοποθεσία όπου αποθηκεύονται τα αρχεία EPS σας.

Τώρα που έχουμε τακτοποιήσει τις προϋποθέσεις μας, ας περάσουμε στα επόμενα κρίσιμα βήματα.

## Εισαγωγή χώρων ονομάτων

Σε οποιοδήποτε έργο .NET, είναι απαραίτητο να εισάγετε τους απαραίτητους χώρους ονομάτων για να χρησιμοποιήσετε τις λειτουργίες του Aspose.Page. Δείτε πώς μπορείτε να το κάνετε:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Βήμα 1: Αρχικοποίηση ροής εισόδου αρχείου EPS

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "Your Document Directory";
// Αρχικοποίηση ροής εισόδου αρχείου EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## Βήμα 2: Δημιουργία παρουσίας PsDocument από τη ροή

```csharp
//Δημιουργία παρουσίας PsDocument από τη ροή
PsDocument document = new PsDocument(psStream);
```

Τώρα που έχουμε ορίσει το στάδιο, ας προχωρήσουμε στον πυρήνα του σεμιναρίου μας - αλλάζοντας τις τιμές μεταδεδομένων XMP μέσα στο αρχείο EPS.

## Βήμα 3: Λήψη μεταδεδομένων XMP

```csharp
// Λάβετε μεταδεδομένα XMP. Εάν το αρχείο EPS δεν περιέχει μεταδεδομένα XMP, λαμβάνουμε ένα νέο γεμάτο με τιμές από σχόλια μεταδεδομένων PS (%%Creator, %%CreateDate, %%Title, κ.λπ.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Βήμα 4: Τροποποιήστε τις τιμές μεταδεδομένων XMP

Τώρα, ας αλλάξουμε μερικές βασικές τιμές στα μεταδεδομένα XMP:

### Βήμα 4.1: Αλλάξτε την τιμή ModifyDate

```csharp
// Αλλάξτε την τιμή ModifyDate
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### Βήμα 4.2: Αλλάξτε την τιμή του Δημιουργού

```csharp
// Αλλαγή τιμής Δημιουργού
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Βήμα 4.3: Αλλάξτε την τιμή τίτλου

```csharp
// Αλλαγή τιμής τίτλου
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

Με αυτές τις αλλαγές που έγιναν, ας προχωρήσουμε στο τελικό βήμα - αποθήκευση του τροποποιημένου αρχείου EPS.

## Βήμα 5: Αποθηκεύστε το αρχείο EPS με αλλαγμένα μεταδεδομένα XMP

### Βήμα 5.1: Δημιουργία ροής εξόδου

```csharp
// Δημιουργία ροής εξόδου
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### Βήμα 5.2: Αποθήκευση αρχείου EPS

```csharp
// Αποθήκευση αρχείου EPS
document.Save(outPsStream);
```

Τέλος, κλείστε τη ροή εισόδου:

```csharp
finally
{
    psStream.Close();
}
```

Συγχαρητήρια! Τροποποιήσατε με επιτυχία τις τιμές μεταδεδομένων XMP σε ένα αρχείο EPS χρησιμοποιώντας το Aspose.Page για .NET.

## συμπέρασμα

Σε αυτό το σεμινάριο, εξερευνήσαμε την απρόσκοπτη διαδικασία αλλαγής τιμών σε αρχεία EPS χρησιμοποιώντας το Aspose.Page για .NET. Ως προγραμματιστής, έχετε τώρα ένα ισχυρό εργαλείο στη διάθεσή σας για αποτελεσματικό χειρισμό εγγράφων.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να χρησιμοποιήσω το Aspose.Page για .NET με άλλες μορφές αρχείων;

A1: Το Aspose.Page εστιάζει κυρίως στον χειρισμό αρχείων EPS. Για άλλες μορφές, εξερευνήστε τη μεγάλη γκάμα προϊόντων της Aspose.

### Ε2: Υπάρχει διαθέσιμη δοκιμαστική έκδοση;

 A2: Ναι, μπορείτε να δοκιμάσετε το Aspose.Page για .NET με τη δωρεάν δοκιμή διαθέσιμη[εδώ](https://releases.aspose.com/).

### Ε3: Πού μπορώ να βρω λεπτομερή τεκμηρίωση;

 A3: Μπορείτε να βρείτε την πλήρη τεκμηρίωση[εδώ](https://reference.aspose.com/page/net/).

### Ε4: Πώς μπορώ να αποκτήσω προσωρινή άδεια;

 A4: Μπορείτε να πάρετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).

### Ε5: Μπορώ να αγοράσω το Aspose.Page για .NET;

 Α5: Απολύτως! Επισκεφθείτε τη σελίδα αγοράς[εδώ](https://purchase.aspose.com/buy) για επιλογές αδειοδότησης.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
