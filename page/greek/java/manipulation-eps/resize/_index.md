---
title: Αλλαγή μεγέθους αρχείων EPS σε Java με το Aspose.Page
linktitle: Αλλαγή μεγέθους αρχείου EPS σε Java
second_title: Aspose.Page Java API
description: Μάθετε πώς να αλλάζετε το μέγεθος των αρχείων EPS σε Java χωρίς κόπο με το Aspose.Page για Java. Ακολουθήστε τον αναλυτικό μας οδηγό για οδηγίες βήμα προς βήμα.
weight: 11
url: /el/java/manipulation-eps/resize/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αλλαγή μεγέθους αρχείων EPS σε Java με το Aspose.Page

## Εισαγωγή
Καλώς ήρθατε στον αναλυτικό οδηγό μας για την αλλαγή μεγέθους αρχείων EPS σε Java χρησιμοποιώντας την ισχυρή βιβλιοθήκη Aspose.Page. Εάν χρειάστηκε ποτέ να προσαρμόσετε τις διαστάσεις των εικόνων EPS σας μέσω προγραμματισμού, βρίσκεστε στο σωστό μέρος. Σε αυτό το σεμινάριο, θα εξερευνήσουμε διάφορες επιλογές αλλαγής μεγέθους, συμπεριλαμβανομένων των πόντων, των ιντσών, των χιλιοστών και των ποσοστών, παρέχοντάς σας την ευελιξία που χρειάζεστε για τις συγκεκριμένες απαιτήσεις σας.
## Προαπαιτούμενα
Πριν βουτήξουμε στο σεμινάριο, βεβαιωθείτε ότι έχετε τα εξής:
- Το Java Development Kit (JDK) είναι εγκατεστημένο στο μηχάνημά σας.
-  Aspose.Page για βιβλιοθήκη Java. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/page/java/).
- Βασική κατανόηση του προγραμματισμού Java.
## Εισαγωγή πακέτων
Στο έργο σας Java, βεβαιωθείτε ότι έχετε τις απαραίτητες εισαγωγές για να χρησιμοποιήσετε τις λειτουργίες Aspose.Page. Εδώ είναι ένα παράδειγμα:
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
Τώρα, ας αναλύσουμε το σεμινάριο σε πολλά βήματα για κάθε επιλογή αλλαγής μεγέθους:
## Αλλαγή μεγέθους EPS με χρήση Πόντων
### Βήμα 1: Ρυθμίστε τη ροή εισόδου
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### Βήμα 2: Αρχικοποιήστε το αντικείμενο PsDocument
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### Βήμα 3: Εξαγάγετε το τρέχον μέγεθος της εικόνας EPS
```java
Dimension oldSize = doc.extractEpsSize();
```
### Βήμα 4: Δημιουργήστε μια ροή εξόδου
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### Βήμα 5: Αλλαγή μεγέθους και αποθήκευση σε πόντους
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## Αλλαγή μεγέθους EPS χρησιμοποιώντας ίντσες
Ακολουθήστε παρόμοια βήματα με το Παράδειγμα 1, αντικαθιστώντας το "Points" με "Inches" και προσαρμόζοντας ανάλογα το νέο μέγεθος.
## Αλλαγή μεγέθους EPS χρησιμοποιώντας χιλιοστά
Ακολουθήστε παρόμοια βήματα με το Παράδειγμα 1, αντικαθιστώντας το "Points" με το "Millimeters" και προσαρμόζοντας ανάλογα το νέο μέγεθος.
## Αλλαγή μεγέθους EPS χρησιμοποιώντας ποσοστά
Ακολουθήστε παρόμοια βήματα με το Παράδειγμα 1, αντικαθιστώντας το "Points" με το "Percentages" και προσαρμόζοντας ανάλογα το νέο μέγεθος.
## συμπέρασμα
Συγχαρητήρια! Μάθατε με επιτυχία πώς να αλλάξετε το μέγεθος των αρχείων EPS στην Java χρησιμοποιώντας το Aspose.Page. Αυτός ο οδηγός σάς παρέχει ευέλικτες επιλογές, διασφαλίζοντας ότι μπορείτε να προσαρμόσετε τη διαδικασία αλλαγής μεγέθους για να καλύψετε τις συγκεκριμένες ανάγκες σας.

## Συχνές ερωτήσεις
### Μπορώ να χρησιμοποιήσω αυτήν τη βιβλιοθήκη για άλλες μορφές εικόνας;
Όχι, το Aspose.Page έχει σχεδιαστεί ειδικά για το χειρισμό αρχείων PostScript και EPS.
### Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Page για Java;
Ναι, μπορείτε να εξερευνήσετε τη δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).
### Πού μπορώ να βρω επιπλέον βοήθεια και συζητήσεις;
 Επισκέψου το[Aspose.Page φόρουμ](https://forum.aspose.com/c/page/39) για κοινοτική υποστήριξη.
### Πώς μπορώ να αποκτήσω προσωρινή άδεια;
 Μπορείτε να πάρετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).
### Υπάρχουν διαθέσιμα παραδείγματα έργων;
 Ναι, ελέγξτε την τεκμηρίωση[εδώ](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
