---
date: 2026-02-23
description: Ismerje meg, hogyan adhat hozzá színátmenetet PostScript fájlokhoz, hogyan
  menthet PostScript fájlt A4-es oldalmérettel, és hogyan töltheti ki a téglalap színátmenetét
  az Aspose.Page for .NET használatával.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Hogyan adjunk hozzá színátmenetet – átlós színátmenet a PostScript (PS) fájlban
  az Aspose.Page .NET használatával
url: /hu/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan adjunk hozzá színátmenetet: Átlós színátmenet a PostScript (PS) fájlhoz az Aspose.Page .NET segítségével

## Bevezetés

Az átlós színátmenet hozzáadása egy PostScript (PS) dokumentumhoz jelentősen javíthatja a vizuális megjelenést, különösen akkor, amikor **how to add gradient** hatásokat kell alkalmazni technikai jelentésekben, prospektusokban vagy grafika‑intenzív alkalmazásokban. Ebben az útmutatóban pontosan megmutatjuk, hogyan adhatunk színátmenetet egy PostScript fájlhoz, állíthatunk be A4 oldalméretet, és tölthetünk ki egy téglalapot egy sima színátmenettel az Aspose.Page for .NET használatával.

## Gyors válaszok
- **Milyen könyvtár szükséges?** Aspose.Page for .NET  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **Módosíthatom a színátmenet irányát?** Igen – forgassa a brush transzformációt a kódban látható módon  
- **Hogyan menthetem az eredményt?** Használd a `PsDocument.Save()` metódust, amely egy PostScript fájlt ír a lemezre  
- **Szükséges licenc a termeléshez?** Igen, egy kereskedelmi licenc feloldja a teljes funkcionalitást  

## Mi az az átlós színátmenet a PostScript-ben?

Az átlós színátmenet egy lineáris színátmenet, amely egy szöggel (általában 45°) fut egy alakzaton keresztül. PostScript-ben ez egy `LinearGradientBrush` alkalmazásával valósítható meg, egy egyedi transzformációs mátrix segítségével, amely elforgatja, méretezzi és eltolja a színátmenetet, hogy illeszkedjen a kívánt téglalaphoz.

## Miért használjuk az Aspose.Page-et színátmenetes kitöltésekhez?

Az Aspose.Page elrejti az alacsony szintű PostScript parancsokat, lehetővé téve, hogy ismerős .NET grafikai objektumokkal dolgozz. Létrehozhatsz összetett kitöltéseket, beállíthatod az oldal méreteit, és közvetlenül exportálhatsz egy **save PostScript file** fájlba anélkül, hogy a nyers PS szintaxist kellene kezelned.

## Előfeltételek

- **Aspose.Page for .NET Library** – töltsd le [itt](https://releases.aspose.com/page/net/).  
- **Document Directory** – egy mappa, ahová a generált `*.ps` fájl kerül.

Most, hogy az alapokat lefedtük, lépésről lépésre végigvezetünk a megvalósításon.

## Névterek importálása

Először importáld a névtereket, amelyek hozzáférést biztosítanak az EPS eszközhöz, a rajzoló segédeszközökhöz és az I/O osztályokhoz.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 1. lépés: Kimeneti stream létrehozása a PostScript dokumentumhoz (PostScript dokumentum létrehozása)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## 2. lépés: A4 oldalméret beállítása (Mentési beállítások)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## 3. lépés: Új, egyoldalas PS dokumentum létrehozása

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## 4. lépés: Téglalap paramétereinek meghatározása

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## 5. lépés: Grafikai útvonal létrehozása

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## 6. lépés: Lineáris színátmenet ecset létrehozása (Téglalap kitöltése színátmenettel)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## 7. lépés: Transzformáció létrehozása az ecsethez

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## 8. lépés: Transzformációk alkalmazása az ecsetre (Forgatás, méretezés, eltolás)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## 9. lépés: Transzformáció beállítása az ecsethez

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## 10. lépés: Festék beállítása és a téglalap kitöltése

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## 11. lépés: Aktuális oldal bezárása

```csharp
	//Close current page
	document.ClosePage();
```

## 12. lépés: Dokumentum mentése (PostScript fájl mentése)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## Hogyan mentse a PostScript fájlt

A `PsDocument.Save()` hívás a teljesen elkészített PostScript tartalmat a **1. lépés**‑ben megnyitott streambe írja. A `using` blokk befejezése után a `DiagonaGradient_outPS.ps` fájl elérhető lesz a megadott könyvtárban.

## Gyakori felhasználási esetek

- **Technikai dokumentáció**, amely finom háttérárnyalatot igényel.  
- **Marketing prospektusok**, ahol az átlós színátmenet modern megjelenést kölcsönöz.  
- **Automatizált jelentésgenerátorok**, amelyek valós időben nyomtatható PS fájlokat állítanak elő.

## Hibaelhárítás és tippek

- **Helytelen színek** – ellenőrizd a `LinearGradientBrush`‑nek átadott ARGB értékeket.  
- **A színátmenet nem látszik** – győződj meg róla, hogy a transzformációs mátrix helyesen forgat és méretez; a `Rotate(-45)` hívás állítja be az átlós szöget.  
- **A fájl nem jön létre** – ellenőrizd, hogy a `dataDir` egy létező mappára mutat, és az alkalmazásnak van írási joga.

## Gyakran ismételt kérdések

**Q: Az Aspose.Page kompatibilis minden .NET keretrendszerrel?**  
A: Az Aspose.Page széles .NET verziók körét támogatja, a .NET Framework 4.5+-tól a .NET 6+-ig, biztosítva a széles körű kompatibilitást.

**Q: Testreszabhatom a színátmenet színeit az Aspose.Page-ben?**  
A: Igen, a `LinearGradientBrush` létrehozásakor megadhatsz bármilyen ARGB színt, így teljesen szabályozhatod a kezdő és végső árnyalatokat.

**Q: Elérhető próba verzió az Aspose.Page-hez?**  
A: Igen, az Aspose.Page funkcióit a próba verzió letöltésével ismerheted meg [itt](https://releases.aspose.com/).

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Page-hez?**  
A: Ideiglenes licencet az Aspose.Page-hez [itt](https://purchase.aspose.com/temporary-license/) szerezhetsz, amely további funkciók feloldását teszi lehetővé a tesztelés során.

**Q: Hol találok közösségi támogatást az Aspose.Page-hez?**  
A: Csatlakozz az Aspose.Page közösséghez a [fórumon](https://forum.aspose.com/c/page/39) segítségért és beszélgetésekért.

---

**Utoljára frissítve:** 2026-02-23  
**Tesztelve:** Aspose.Page for .NET (legújabb stabil kiadás)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}