---
title: Αλλάξτε την ονομαστική τιμή με το Aspose.Page για .NET
linktitle: Αλλαγή ονομαστικής τιμής
second_title: Aspose.Page .NET API
description: Μάθετε πώς να αλλάζετε ονομαστικές τιμές σε αρχεία EPS χρησιμοποιώντας το Aspose.Page για .NET. Προσαρμόστε τα μεταδεδομένα XMP χωρίς κόπο για προσαρμοσμένη επεξεργασία εγγράφων.
weight: 16
url: /el/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αλλάξτε την ονομαστική τιμή με το Aspose.Page για .NET

## Εισαγωγή

Στον κόσμο της επεξεργασίας εγγράφων, το Aspose.Page για .NET ξεχωρίζει ως ένα ισχυρό εργαλείο για τον χειρισμό αρχείων EPS. Μία από τις βασικές λειτουργίες που προσφέρει είναι η δυνατότητα αλλαγής ονομαστικών τιμών στα μεταδεδομένα XMP. Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία αλλαγής μιας ονομασμένης τιμής χρησιμοποιώντας το Aspose.Page για .NET, δίνοντάς σας τη δυνατότητα να προσαρμόσετε τα αρχεία EPS σας σύμφωνα με τις συγκεκριμένες ανάγκες σας.

## Προαπαιτούμενα

Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

-  Aspose.Page για .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Page για .NET. Εάν όχι, μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/page/net/).

- Κατάλογος εγγράφων: Έχετε έναν καθορισμένο κατάλογο για τα αρχεία EPS όπου μπορείτε να πραγματοποιήσετε τις αλλαγές της ονομαστικής τιμής.

## Εισαγωγή χώρων ονομάτων

Στο έργο σας .NET, πρέπει να εισαγάγετε τους απαραίτητους χώρους ονομάτων για πρόσβαση στη λειτουργικότητα που παρέχεται από το Aspose.Page. Προσθέστε τους παρακάτω χώρους ονομάτων στον κώδικά σας:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Τώρα, ας αναλύσουμε τον κώδικα σε πολλά βήματα για μια ολοκληρωμένη κατανόηση:

## Βήμα 1: Αρχικοποιήστε τη ροή εισόδου αρχείου EPS

```csharp
// ExStart: 1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd: 1
```

Σε αυτό το βήμα, ρυθμίσαμε τη ροή εισόδου για το αρχείο EPS που θέλετε να τροποποιήσετε. Βεβαιωθείτε ότι έχετε αντικαταστήσει τον "Κατάλογο εγγράφων σας" με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

## Βήμα 2: Λήψη μεταδεδομένων XMP

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Ανακτήστε τα υπάρχοντα μεταδεδομένα XMP από το αρχείο EPS. Εάν το αρχείο EPS δεν περιέχει μεταδεδομένα XMP, θα δημιουργηθεί ένα νέο με τιμές από σχόλια μεταδεδομένων PS.

## Βήμα 3: Αλλάξτε τις τιμές μεταδεδομένων XMP

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Εδώ, δείχνουμε την αλλαγή δύο ονομαστικών τιμών στη δομή "xmpTPg:MaxPageSize". Μπορείτε να το προσαρμόσετε σύμφωνα με τις συγκεκριμένες απαιτήσεις σας.

## Βήμα 4: Αποθήκευση αρχείου EPS με Αλλαγμένα μεταδεδομένα XMP

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Αποθηκεύστε το τροποποιημένο αρχείο EPS στη ροή εξόδου. Το αρχείο θα αντικατοπτρίζει τώρα τις αλλαγές που έγιναν στα μεταδεδομένα XMP.

## συμπέρασμα

Με αυτό το σεμινάριο, μάθατε πώς να αξιοποιείτε το Aspose.Page για .NET για να αλλάζετε ονομαστικές τιμές στα μεταδεδομένα XMP σε αρχεία EPS. Αυτή η λειτουργία ανοίγει έναν κόσμο δυνατοτήτων για την προσαρμογή και την προσαρμογή των εγγράφων σας ώστε να ανταποκρίνονται σε συγκεκριμένες απαιτήσεις.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να χρησιμοποιήσω το Aspose.Page για .NET με άλλες μορφές εγγράφων;

A1: Ναι, το Aspose.Page υποστηρίζει διάφορες μορφές εγγράφων, συμπεριλαμβανομένων των EPS, XPS και PDF.

### Ε2: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Page για .NET;

 A2: Ναι, μπορείτε να έχετε πρόσβαση σε μια δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).

### Ε3: Πού μπορώ να βρω περισσότερη τεκμηρίωση στο Aspose.Page για .NET;

 A3: Ανατρέξτε στην τεκμηρίωση[εδώ](https://reference.aspose.com/page/net/).

### Ε4: Πώς μπορώ να αποκτήσω μια προσωρινή άδεια χρήσης για το Aspose.Page για .NET;

 A4: Μπορείτε να πάρετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).

### Ε5: Ποιες επιλογές υποστήριξης είναι διαθέσιμες για το Aspose.Page για χρήστες .NET;

 A5: Επισκεφθείτε το φόρουμ της κοινότητας[εδώ](https://forum.aspose.com/c/page/39) για υποστήριξη και συζητήσεις.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
