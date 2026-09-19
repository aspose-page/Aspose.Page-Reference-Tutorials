---
date: 2026-09-19
description: Μάθετε πώς να προσθέσετε XMP named values σε αρχεία EPS χρησιμοποιώντας
  Aspose.Page για Java – ένας οδηγός βήμα‑βήμα με παραδείγματα κώδικα.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: Προσθήκη Named Value σε XMP χρησιμοποιώντας Java
og_description: Πώς να προσθέσετε XMP named values σε αρχεία EPS χρησιμοποιώντας Aspose.Page
  για Java. Ακολουθήστε αυτόν τον σύντομο οδηγό για να ενσωματώσετε προσαρμοσμένα
  metadata σε λίγα λεπτά.
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: Πώς να προσθέσετε XMP named value σε αρχεία EPS χρησιμοποιώντας Java
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: Πώς να προσθέσετε XMP named value σε αρχεία EPS χρησιμοποιώντας Java
url: /el/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη ονομαστικής τιμής σε μεταδεδομένα XMP χρησιμοποιώντας Java

## Εισαγωγή
Στη σύγχρονη ανάπτυξη Java, η εκμάθηση **πώς να προσθέσετε μεταδεδομένα XMP** μέσα σε αρχεία EPS είναι απαραίτητη για τη διατήρηση της προέλευσης των εγγράφων και τη βελτίωση της αναζητησιμότητας. Με το **Aspose.Page for Java**, μπορείτε εύκολα να ενσωματώσετε προσαρμοσμένες ονομαστικές τιμές στο πακέτο XMP. Αυτό το tutorial σας οδηγεί βήμα προς βήμα — με πλήρη αποσπάσματα κώδικα — ώστε να ξεκινήσετε να προσθέτετε μεταδεδομένα XMP στα έγγραφα EPS σας σήμερα.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page for Java (Aspose)  
- **Ποιος τύπος αρχείου στοχεύεται;** EPS files containing XMP metadata  
- **Κύρια περίπτωση χρήσης;** Add custom named values (e.g., page size limits) to XMP  
- **Προαπαιτούμενα;** JDK 8+ and the Aspose.Page for Java library  
- **Τυπικός χρόνος υλοποίησης;** 5–10 minutes once the library is set up  

## Τι είναι το asp;
Η Aspose είναι η συντομογραφία για την Aspose, μια σουίτα API που επιτρέπει στους προγραμματιστές να δημιουργούν, να επεξεργάζονται, να μετατρέπουν και να αποδίδουν μια ευρεία γκάμα μορφών εγγράφων χωρίς την ανάγκη εξωτερικού λογισμικού. Το στοιχείο Aspose.Page for Java εστιάζει ειδικά στην επεξεργασία PostScript και EPS, παρέχοντας προγραμματιστική πρόσβαση στο περιεχόμενο της σελίδας, τα γραφικά και τα μεταδεδομένα όπως το XMP.

## Γιατί να προσθέσετε ονομαστικές τιμές στα μεταδεδομένα XMP;
Οι ονομαστικές τιμές σας επιτρέπουν να αποθηκεύετε αυθαίρετα ζεύγη κλειδιού‑τιμής απευθείας μέσα στο πακέτο XMP, καθιστώντας τα άμεσα αναγνώσιμα από τα επόμενα εργαλεία. Αυτό βελτιώνει τη φιλικότητα προς τις μηχανές αναζήτησης, ενεργοποιεί την αυτοματοποίηση ροής εργασίας και ικανοποιεί τις απαιτήσεις συμμόρφωσης ενσωματώνοντας κανονιστικές πληροφορίες χωρίς να τροποποιεί το οπτικό περιεχόμενο.

## Γιατί είναι σημαντικό
Η προσθήκη ονομαστικών τιμών στο XMP σας επιτρέπει να αποθηκεύετε αυθαίρετα ζεύγη κλειδιού‑τιμής που μπορούν να διαβαστούν χωρίς την ανάλυση ολόκληρου του αρχείου EPS. Αυτή η δυνατότητα είναι ιδιαίτερα πολύτιμη σε αυτοματοποιημένες γραμμές παραγωγής δημοσίευσης, συστήματα διαχείρισης ψηφιακών περιουσιακών στοιχείων και ροές εργασίας που καθοδηγούνται από συμμόρφωση, όπου τα μεταδεδομένα καθορίζουν τις επόμενες ενέργειες.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα παρακάτω:

- **Java Development Kit (JDK):** Ένα πρόσφατο JDK (8 ή νεότερο) εγκατεστημένο στο μηχάνημά σας.  
- **Aspose.Page for Java Library:** Κατεβάστε το από την επίσημη [Aspose.Page for Java download](https://releases.aspose.com/page/java/). Προσθέστε το JAR στο classpath του έργου σας.  
- **Ένα αρχείο EPS** που είτε περιέχει ήδη μεταδεδομένα XMP είτε θα δημιουργηθεί αυτόματα.

## Εισαγωγή πακέτων
Ξεκινήστε εισάγοντας τα απαραίτητα πακέτα Java. Αυτές οι εισαγωγές σας δίνουν πρόσβαση σε ροές αρχείων, το μοντέλο εγγράφου EPS και τις κλάσεις διαχείρισης XMP.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Πώς να προσθέσετε ονομαστική τιμή XMP σε αρχεία EPS χρησιμοποιώντας Java
Για να προσθέσετε μια ονομαστική τιμή, φορτώστε το αρχείο EPS με ένα `FileInputStream`, ανακτήστε ή δημιουργήστε το αντικείμενο `XmpMetadata`, εισάγετε το επιθυμητό `NamedValue` στο κατάλληλο namespace και, στη συνέχεια, γράψτε το τροποποιημένο έγγραφο πίσω χρησιμοποιώντας ένα `FileOutputStream`. Το Aspose.Page διαχειρίζεται αυτόματα τη δημιουργία του πακέτου XMP εάν λείπει, εξασφαλίζοντας ότι τα νέα μεταδεδομένα ενσωματώνονται σωστά.

### Βήμα 1: Αρχικοποίηση ροής εισόδου αρχείου EPS
**FileInputStream** είναι μια κλάση Java I/O που διαβάζει ακατέργαστα byte από ένα αρχείο. Φορτώστε το πηγαίο αρχείο EPS σε ένα `FileInputStream`. Αυτή η ροή παρέχει το έγγραφο στο API του Aspose.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Συμβουλή:** Κρατήστε τη μεταβλητή `dataDir` ρυθμιζόμενη ώστε ο ίδιος κώδικας να λειτουργεί σε διαφορετικά περιβάλλοντα.

### Βήμα 2: Απόκτηση μεταδεδομένων XMP
**XmpMetadata** αντιπροσωπεύει το πακέτο XMP που συνδέεται με ένα έγγραφο EPS. Ανακτήστε το υπάρχον πακέτο XMP· εάν το αρχείο EPS δεν διαθέτει, το Aspose δημιουργεί ένα νέο αντικείμενο XMP που γεμίζει από τα σχόλια PS.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Βήμα 3: Προσθήκη ονομαστικής τιμής
**NamedValue** είναι ένα ζεύγος κλειδιού‑τιμής που αποθηκεύεται μέσα στο namespace των μεταδεδομένων XMP. Εισάγετε μια προσαρμοσμένη ονομαστική τιμή στη δομή XMP. Σε αυτό το παράδειγμα προσθέτουμε ένα νέο κλειδί στο namespace `xmpTPg:MaxPageSize`.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Γιατί είναι σημαντικό:** Οι ονομαστικές τιμές σας επιτρέπουν να αποθηκεύετε αυθαίρετα ζεύγη κλειδιού‑τιμής που οι επόμενες εφαρμογές μπορούν να διαβάσουν χωρίς να αναλύσουν ολόκληρο το έγγραφο.

### Βήμα 4: Αρχικοποίηση ροής εξόδου αρχείου EPS
**FileOutputStream** είναι μια κλάση Java I/O που γράφει ακατέργαστα byte σε ένα αρχείο. Προετοιμάστε ένα `FileOutputStream` όπου θα αποθηκευτεί το τροποποιημένο EPS.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Βήμα 5: Αποθήκευση εγγράφου
Η μέθοδος `save` διατηρεί τις αλλαγές. Γράφει το ενημερωμένο πακέτο XMP πίσω στο αρχείο EPS, εξασφαλίζοντας ότι η νέα ονομαστική τιμή γίνεται μέρος των μεταδεδομένων του εγγράφου.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Βήμα 6: Κλείσιμο ροής εισόδου EPS
Το κλείσιμο του αρχικού χειριστηρίου αρχείου αποτρέπει διαρροές πόρων και εξασφαλίζει ότι το αρχείο δεν είναι κλειδωμένο για επόμενες λειτουργίες.

```java
psStream.close();
```

Ακολουθώντας αυτά τα έξι βήματα, έχετε προσθέσει με επιτυχία **μια ονομαστική τιμή στα μεταδεδομένα XMP** χρησιμοποιώντας **Aspose.Page for Java**.

## Συχνά προβλήματα & λύσεις
| Πρόβλημα | Αιτία | Διόρθωση |
|-------|-------|-----|
| `NullPointerException` on `xmp` | Το αρχείο EPS δεν έχει XMP και το Aspose δεν μπόρεσε να δημιουργήσει ένα | Βεβαιωθείτε ότι το EPS περιέχει τουλάχιστον ένα σχόλιο PS ή δημιουργήστε χειροκίνητα ένα νέο αντικείμενο `XmpMetadata`. |
| Output file is empty | Η ροή εξόδου δεν έχει αδειάσει/κλειστεί | Επαληθεύστε ότι καλείται `outPsStream.close()` σε ένα `finally` block (όπως φαίνεται). |
| Duplicate key error | Η ίδια ονομαστική τιμή προστέθηκε δύο φορές | Ελέγξτε αν το κλειδί υπάρχει ήδη με `xmp.containsNamedValue(...)` πριν την προσθήκη. |

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Page for Java με άλλες βιβλιοθήκες Java;**  
A: Ναι, το Aspose.Page for Java έχει σχεδιαστεί ώστε να λειτουργεί απρόσκοπτα με άλλες βιβλιοθήκες Java, παρέχοντας ευελιξία στο περιβάλλον ανάπτυξής σας.

**Q: Διατίθεται δωρεάν δοκιμή για το Aspose.Page for Java;**  
A: Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή του Aspose.Page for Java στη [Aspose releases page](https://releases.aspose.com/).

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page for Java;**  
A: Επισκεφθείτε τη [temporary license page](https://purchase.aspose.com/temporary-license/) για να αποκτήσετε προσωρινή άδεια για το Aspose.Page for Java.

**Q: Πού μπορώ να βρω περισσότερα tutorials και παραδείγματα για το Aspose.Page for Java;**  
A: Εξερευνήστε την [documentation](https://reference.aspose.com/page/java/) για ολοκληρωμένα tutorials και παραδείγματα.

**Q: Είναι το Aspose.Page for Java κατάλληλο για μεγάλης κλίμακας έργα;**  
A: Απόλυτα, το Aspose.Page for Java έχει σχεδιαστεί για να διαχειρίζεται μεγάλης κλίμακας έργα αποδοτικά, παρέχοντας ισχυρές δυνατότητες διαχείρισης εγγράφων.

## Συμπέρασμα
Σε αυτόν τον οδηγό δείξαμε πώς το **Aspose.Page for Java** καθιστά εύκολο να **προσθέσετε ονομαστικές τιμές στα μεταδεδομένα XMP** μέσα σε αρχεία EPS. Με τα παραπάνω βήματα, μπορείτε να εμπλουτίσετε τα έγγραφά σας με προσαρμοσμένα μεταδεδομένα, να βελτιώσετε την αναζητησιμότητα και να ενεργοποιήσετε πιο έξυπνη επεξεργασία downstream.

---

**Last Updated:** 2026-09-19  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Σχετικά Tutorials

- [Πώς να προσθέσετε Namespace XMP σε αρχεία EPS χρησιμοποιώντας Aspose.Page – Java Tutorial](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Προσθήκη μεταδεδομένων XMP σε αρχεία EPS χρησιμοποιώντας Java](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [Ανάγνωση XMP με το Aspose.Page – Java Guide](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}