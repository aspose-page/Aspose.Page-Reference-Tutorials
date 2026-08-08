---
date: 2026-05-25
description: Μάθετε πώς να διαβάζετε xmp χρησιμοποιώντας aspose.page με Java. Αυτός
  ο οδηγός βήμα‑βήμα δείχνει την εξαγωγή XMP metadata, πληροφορίες δημιουργού, χρονικές
  σημάνσεις, μικρογραφίες και άλλα.
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: Πώς να διαβάσετε XMP Metadata με Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: Ανάγνωση XMP με Aspose.Page – Οδηγός Java
url: /el/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αποκτήστε Μεταδεδομένα από XMP χρησιμοποιώντας Java

## Πώς να διαβάσετε XMP χρησιμοποιώντας Aspose.Page (Java)?

Φορτώστε το αρχείο EPS με `new Document("file.eps")` — η κλάση `Document` αντιπροσωπεύει ένα φορτωμένο αρχείο. Καλέστε `getXmpMetadata()`, η οποία εξάγει το πακέτο XMP, και στη συνέχεια ερωτήστε το επιστρεφόμενο αντικείμενο `XmpMetadata` — μια διεπαφή τύπου χάρτη για τις ιδιότητες XMP — ώστε να ανακτήσετε τα κλειδιά που χρειάζεστε. Αυτό είναι ό,τι απαιτείται για την ανάγνωση XMP χρησιμοποιώντας Aspose.Page. Το API αφαιρεί την χαμηλού επιπέδου ανάλυση, έτσι λαμβάνετε έναν έτοιμο προς χρήση χάρτη ιδιοτήτων σε μόλις δύο γραμμές κώδικα.

Καλώς ήρθατε στο βήμα‑βήμα tutorial μας που δείχνει **πώς να διαβάσετε XMP** μεταδεδομένα με Java και τη βιβλιοθήκη Aspose.Page. Το XMP (Extensible Metadata Platform) είναι ένα ευρέως υιοθετημένο πρότυπο για την ενσωμάτωση πλούσιων μεταδεδομένων μέσα σε έγγραφα. Στο τέλος αυτού του οδηγού θα μπορείτε να διαβάζετε το XMP μορφής εγγράφου, να εξάγετε πληροφορίες δημιουργού, χρονικές σφραγίδες, μικρογραφίες και άλλα — δίνοντάς σας τη δυνατότητα να δημιουργήσετε πιο έξυπνες λύσεις ανάλυσης εγγράφων.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “read XMP”;** Σημαίνει την προγραμματιστική εξαγωγή του πακέτου XMP που αποθηκεύει μεταδεδομένα μέσα σε ένα αρχείο.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page for Java (κατεβάστε από την επίσημη σελίδα [here](https://releases.aspose.com/page/java/)).  
- **Χρειάζομαι άδεια;** Απαιτείται προσωρινή ή πλήρης άδεια για παραγωγή· μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση.  
- **Ποια έκδοση Java υποστηρίζεται;** Java 8 ή νεότερη.  
- **Μπορώ να διαβάσω XMP από άλλες μορφές;** Ναι – το Aspose.Page εξάγει XMP από EPS, PDF, JPEG, PNG και πάνω από 20 άλλες μορφές.

## Προαπαιτούμενα
Πριν βυθιστείτε στον κώδικα, βεβαιωθείτε ότι έχετε:

- **Java Development Kit (JDK)** – Java 8+ εγκατεστημένο και ρυθμισμένο στο μηχάνημά σας.  
- **Aspose.Page for Java** – Κατεβάστε τη βιβλιοθήκη από την επίσημη ιστοσελίδα [here](https://releases.aspose.com/page/java/).  
- Ένα αρχείο EPS που περιέχει μεταδεδομένα XMP (π.χ., `xmp1.eps`).  

## Εισαγωγή Πακέτων
Η κλάση `XmpMetadata` βρίσκεται στο namespace `com.aspose.page.xmp`, ενώ η κλάση `Document` είναι στο `com.aspose.page`. Εισάγετε και τις δύο ώστε να μπορείτε να εργαστείτε με το αρχείο EPS και τα μεταδεδομένα του.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Βήμα 1: Αρχικοποίηση Ροής Εισόδου Αρχείου EPS
Ξεκινήστε ορίζοντας τη διαδρομή προς τον φάκελο εγγράφων σας και αρχικοποιώντας τη ροή εισόδου του αρχείου EPS.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Βήμα 2: Λήψη Μεταδεδομένων XMP
`XmpMetadata` είναι το αντικείμενο του Aspose.Page που κρατά το πακέτο XMP που εξάγεται από ένα έγγραφο. Ανακτήστε το με `document.getXmpMetadata()`. Εάν το αρχείο δεν περιέχει XMP, το API συνθέτει ένα ελάχιστο πακέτο από υπάρχοντα σχόλια PostScript.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Βήμα 3: Εξαγωγή Πληροφοριών CreatorTool
Το κλειδί `CreatorTool` βρίσκεται στο namespace `xmp` και καταγράφει την εφαρμογή που δημιούργησε το αρχείο. Ελέγξτε την παρουσία του και εκτυπώστε την τιμή.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Βήμα 4: Εξαγωγή Πληροφοριών CreateDate
`CreateDate` αποθηκεύει τη χρονική σήμανση όταν το έγγραφο δημιουργήθηκε αρχικά. Χρησιμοποιήστε το ίδιο μοτίβο `containsKey`/`get` για να το διαβάσετε.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Βήμα 5: Ανάκτηση Πλάτους Μικρογραφίας
Εάν υπάρχουν μικρογραφίες, ο πίνακας `xmp:Thumbnails` περιέχει μία ή περισσότερες καταχωρήσεις. Κάθε καταχώρηση περιέχει `width`, `height` και δυαδικά δεδομένα. Το παράδειγμα εξάγει το πλάτος της πρώτης μικρογραφίας.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Βήμα 6: Εξαγωγή Πληροφοριών Format
Το κλειδί `format` σας λέει τη αρχική μορφή αρχείου (π.χ., “application/postscript”). Αυτό είναι χρήσιμο όταν χρειάζεται να καταγράψετε ή να επικυρώσετε τύπους πηγής.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Βήμα 7: Λήψη DocumentID
`DocumentID` είναι ένας μοναδικός ταυτοποιητής που εκχωρεί η εφαρμογή δημιουργού. Μπορεί να χρησιμοποιηθεί για απομάκρυνση διπλοτύπων σε μεγάλες βιβλιοθήκες περιουσιακών στοιχείων.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Γιατί Αυτό Είναι Σημαντικό
Το Aspose.Page μπορεί να διαβάσει XMP από **20+** μορφές αρχείων και επεξεργάζεται έγγραφα μέχρι **500 MB** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, παρέχοντάς σας γρήγορη, χαμηλού κόστους πρόσβαση σε βασικά μεταδεδομένα. Αυτή η δυνατότητα είναι κρίσιμη για αγωγούς επεξεργασίας παρτίδων, συστήματα διαχείρισης ψηφιακών περιουσιακών στοιχείων και οποιαδήποτε λύση που βασίζεται σε αναζητήσιμα, μηχανικά αναγνώσιμα χαρακτηριστικά εγγράφων.

## Συχνά Πόνοι & Συμβουλές
- **Missing XMP:** Κάποια αρχεία EPS μπορεί να μην περιέχουν XMP. Η κλήση `getXmpMetadata()` θα συνθέσει ένα ελάχιστο σύνολο βασισμένο σε υπάρχοντα σχόλια PS, αλλά δεν θα λάβετε πλήρη μεταδεδομένα εκτός εάν είναι ενσωματωμένα.  
- **Thumbnail Arrays:** Το κλειδί `xmp:Thumbnails` μπορεί να περιέχει πολλαπλές καταχωρήσεις. Το παράδειγμα εξάγει μόνο την πρώτη· επαναλάβετε τον πίνακα αν χρειάζεστε όλες τις μικρογραφίες.  
- **Namespace Awareness:** Τα κλειδιά XMP χρησιμοποιούν namespaces (π.χ., `xmp:`, `dc:`). Βεβαιωθείτε ότι αναφέρετε το ακριβές όνομα κλειδιού· διαφορετικά το `containsKey` θα επιστρέψει false.  

## Συχνές Ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Page για Java με άλλες γλώσσες προγραμματισμού;
Ναι, το Aspose.Page υποστηρίζει Java, .NET και αρκετές άλλες γλώσσες. Δείτε τη πλήρη λίστα στην [documentation](https://reference.aspose.com/page/java/).

### Διατίθεται δωρεάν δοκιμή για το Aspose.Page για Java;
Ναι, μπορείτε να αποκτήσετε τη δωρεάν δοκιμή [here](https://releases.aspose.com/).

### Πού μπορώ να βρω υποστήριξη για το Aspose.Page για Java;
Επισκεφθείτε το [Aspose.Page forum](https://forum.aspose.com/c/page/39) για βοήθεια από την κοινότητα και επίσημη υποστήριξη.

### Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page για Java;
Μπορείτε να αποκτήσετε προσωρινή άδεια [here](https://purchase.aspose.com/temporary-license/).

### Υπάρχουν πρόσθετοι πόροι για το Aspose.Page για Java;
Εξερευνήστε την πλήρη [documentation](https://reference.aspose.com/page/java/) και κατεβάστε τη βιβλιοθήκη [here](https://releases.aspose.com/page/java/).

## Πρόσθετες Συχνές Ερωτήσεις
**Q: Λειτουργεί αυτή η προσέγγιση με αρχεία PDF που περιέχουν XMP;**  
A: Ναι, το Aspose.Page μπορεί να διαβάσει XMP από PDF, EPS και αρκετές μορφές εικόνας.

**Q: Μπορώ να τροποποιήσω τα μεταδεδομένα XMP μετά την ανάγνωσή τους;**  
A: Απόλυτα. Το αντικείμενο `XmpMetadata` είναι μεταβλητό· μπορείτε να προσθέσετε, ενημερώσετε ή αφαιρέσετε κλειδιά και στη συνέχεια να αποθηκεύσετε το έγγραφο.

**Q: Υπάρχει τρόπος να εξάγω όλες τις εικόνες μικρογραφιών, όχι μόνο τις διαστάσεις;**  
A: Μπορείτε να ανακτήσετε τα δυαδικά δεδομένα από την ιδιότητα `xmpGImg:data` κάθε καταχώρησης μικρογραφίας και να τα γράψετε σε αρχείο.

## Συμπέρασμα
Τώρα έχετε κατακτήσει **πώς να διαβάσετε XMP** μεταδεδομένα χρησιμοποιώντας Java και Aspose.Page. Ακολουθώντας αυτά τα βήματα μπορείτε να εξάγετε εργαλεία δημιουργού, χρονικές σφραγίδες, μικρογραφίες, πληροφορίες μορφής και τα Document IDs—σας παρέχοντας πλήρη εικόνα των ενσωματωμένων μεταδεδομένων των αρχείων EPS σας. Μη διστάσετε να πειραματιστείτε με πρόσθετα namespaces XMP για να εξάγετε ακόμη πιο πλούσια δεδομένα για τις εφαρμογές σας.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose

## Σχετικά Μαθήματα

- [Aspose Page Java Tutorial – Προσθήκη XMP Metadata σε Αρχεία EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page xmp tutorial – Προσθήκη Namespace στο XMP χρησιμοποιώντας Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [aspose page xmp tutorial – Αλλαγή Named Value στο XMP χρησιμοποιώντας Java](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}