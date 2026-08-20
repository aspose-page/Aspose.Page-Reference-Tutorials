---
date: 2026-03-13
description: Tanulja meg, hogyan adhat hozzá színátmenetet XPS dokumentumokhoz Java-ban
  az Aspose.Page használatával, és hogyan testreszabhatja a színátmenet állomásait
  lenyűgöző vízszintes hatások érdekében.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Hogyan adjunk hozzá színátmenetet – vízszintes színátmenet Java XPS-ben
url: /hu/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan adjunk hozzá színátmenetet – Vízszintes színátmenet Java XPS-ben

## Bevezetés
Üdvözöljük ebben a lépésről‑lépésre útmutatóban, amely bemutatja, hogyan **adhatunk hozzá színátmenetet** egy XPS dokumentumhoz Java használatával. Ebben az oktatóanyagban megtanulja, hogyan adjon hozzá vízszintes színátmenetet, miért fontos a vizuális kifinomultság szempontjából, és hogyan **testreszabhatja a színátmenet állomásait** a pontos színvezérlés érdekében. Az Aspose.Page for Java egyszerűvé teszi az XPS (XML Paper Specification) dokumentumokkal való munkát, lehetővé téve, hogy a tervezésre koncentráljon a fájl alacsony szintű kezelésének helyett.

## Gyors válaszok
- **Melyik könyvtár szükséges?** Aspose.Page for Java  
- **Melyik Java verzió működik?** Bármely Java 8+ futtatókörnyezet  
- **Szükségem van licencre?** A ingyenes próba verzió fejlesztéshez megfelelő; a termeléshez kereskedelmi licenc szükséges  
- **Módosíthatom a színátmenet irányát?** Igen – egyszerűen módosítsa a lineáris ecset kezdő‑ és végpontjait  
- **Lehetséges több színátmenetet hozzáadni?** Teljesen – ismételje meg az útvonal létrehozási lépéseket különböző ecsetekkel  

## Mi az a vízszintes színátmenet az XPS-ben?
A vízszintes színátmenet a színek balról jobbra történő sima átmenete egy alakzatban. Az XPS-ben egy lineáris színátmenet ecsettel van ábrázolva, amely interpolál a meghatározott **gradient stops** között. Ez a vizuális hatás gyakran használatos bannerek, gombok és háttérkitöltések esetén.

## Miért használjuk az Aspose.Page for Java-t?
- **Teljes XPS támogatás** – létrehozhat, szerkeszthet és renderelhet harmadik fél eszközei nélkül.  
- **Egyszerű API** – magas szintű objektumok, mint a `XpsDocument`, `XpsPath` és `XpsGradientBrush` elrejtik az XML bonyolultságát.  
- **Teljesítmény** – nagy dokumentumokhoz és kötegelt feldolgozáshoz optimalizált.  

## Előfeltételek
1. **Java fejlesztői környezet** – Telepítse a legújabb JDK-t a [java.com](https://www.java.com) oldalról.  
2. **Aspose.Page for Java könyvtár** – Töltse le a JAR fájlt az [Aspose.Page for Java dokumentáció](https://reference.aspose.com/page/java/) oldalról.  

## Csomagok importálása
Kezdje a szükséges osztályok importálásával. Ezek az importok hozzáférést biztosítanak a dokumentum létrehozásához, a színátmenet kezeléséhez és az alapvető geometriai műveletekhez.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## 1. lépés: Az XPS dokumentum inicializálása
Hozzon létre egy új `XpsDocument` példányt, és adja meg azt a mappát, ahová a végeredményt menteni kívánja.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## 2. lépés: Ví­zszintes színátmenet létrehozása
Határozzon meg egy **gradient stops** listát, amely szabályozza minden átmeneti pont színét és pozícióját. Az alábbi példa egy élénk, szivárvány‑szerű színátmenetet hoz létre.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### Hogyan testreszabja a színátmenet állomásait
- **Szín** – Használja a `doc.createColor(alpha, red, green, blue)` metódust bármely ARGB érték beállításához.  
- **Pozíció** – A második argumentum (`float` 0 és 1 között) határozza meg, hogy az állomás hol jelenik meg a színátmenet vonalán. Állítsa ezeket az értékeket a színek balra vagy jobbra történő eltolásához.

## 3. lépés: Útvonal hozzáadása színátmenettel
Hozzon létre egy téglalap alakú útvonalat, szükség esetén alkalmazzon transzformációt, és töltse ki a lineáris színátmenet ecsettel. Az ecset két pontot (`(10,0)` és `(228,0)`) használ a vízszintes hatás eléréséhez. Mivel a Y‑koordináták azonosak, ez az ecset **vízszintes színátmenet ecsetként** működik.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Hasznos tipp:** Ugyanazon `stops` lista újrahasználata több útvonalhoz javíthatja a teljesítményt, de ne felejtse el `clear()`-el törölni, mielőtt új állomásokat adna hozzá.

## 4. lépés: Dokumentum mentése
Mentse az XPS fájlt a lemezre. Most már megnyithatja bármely XPS megjelenítővel, hogy lássa a vízszintes színátmenet működését.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Hogyan alkalmazzon több színátmenetet
Ha **több színátmenetet szeretne alkalmazni** egyetlen XPS dokumentumban, egyszerűen ismételje meg a „Vízszintes színátmenet létrehozása” és a „Útvonal hozzáadása színátmenettel” lépéseket minden új alakzatnál. Használjon egy új `XpsGradientStop` objektumlistát (vagy törölje a meglévőt), és rendelje hozzá egy új `LinearGradientBrush`-t a saját kezdő‑ és végpontjaival. Ez a megközelítés lehetővé teszi a színátmenetek rétegezését, összetett háttér létrehozását vagy különböző UI elemek kiemelését egyetlen oldalon.

## Miért fontos – A vízszintes színátmenet ecset előnyei
- **Vizuális mélység:** A vízszintes színátmenet ecset finom háromdimenziós hatást ad extra képek nélkül.  
- **Fájlméret hatékonyság:** A színátmenetek vektoros definícióként tárolódnak, így az XPS fájl könnyű marad.  
- **Skálázhatóság:** Mivel a színátmenet vektoros, tisztán méretezhető nagy felbontású kijelzőkön.  

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| A színátmenet egyszínűnek tűnik | Nincsenek hozzáadva színátmenet állomások vagy az ecset nincs beállítva | Győződjön meg arról, hogy a `path.setFill(...)` egy `LinearGradientBrush`-t használ, és hogy az állomásokat a `getGradientStops().addAll(stops)`-val adták hozzá. |
| A színek tompák | Helytelen alfa érték (első paraméter) | Használjon `255`-öt a teljesen átlátszatlan színekhez, hacsak nem kíván átlátszóságot. |
| Az útvonal mérete hibás | A transzformációs mátrix értékei hibásak | Állítsa be a mátrix paramétereit (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Gyakran ismételt kérdések

**Q: Alkalmazhatok több színátmenetet egyetlen XPS dokumentumban?**  
A: Igen, több útvonalat is hozzáadhat, mindegyik saját színátmenet ecsettel, így összetett rétegezett tervezéseket hozhat létre.

**Q: Az Aspose.Page kompatibilis a legújabb Java verziókkal?**  
A: Az Aspose.Page for Java rendszeresen frissül, és működik a Java 8 és újabb kiadásokkal.

**Q: Vannak más színátmenet típusok is az Aspose.Page-ben?**  
A: A lineáris színátmenetek mellett az Aspose.Page támogatja a radiális színátmeneteket is, amelyek körkörös színátmeneteket biztosítanak.

**Q: Testreszabhatom a színátmenet állomások színeit és pozícióit?**  
A: Teljes mértékben! Teljes ellenőrzés áll rendelkezésére minden állomás ARGB színe és relatív pozíciója (0‑1 tartomány) felett.

**Q: Van közösségi fórum az Aspose.Page-hez, ahol segítséget kérhetek?**  
A: Igen, felkeresheti az [Aspose.Page fórumot](https://forum.aspose.com/c/page/39), hogy csatlakozzon a közösséghez és segítséget kapjon.

**Legutóbb frissítve:** 2026-03-13  
**Tesztelve a következővel:** Aspose.Page for Java 24.11  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}