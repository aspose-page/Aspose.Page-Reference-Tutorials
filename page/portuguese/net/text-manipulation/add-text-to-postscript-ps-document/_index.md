---
date: 2026-03-21
description: Aprenda como preencher texto e adicionar texto a documentos PS usando
  Aspose.Page para .NET. Guia passo a passo com exemplos de código.
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Como Preencher Texto em Documentos PostScript (PS) com Aspose.Page
url: /pt/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Preencher Texto em Documentos PostScript (PS) com Aspose.Page

## Introdução

Se você precisa **how to fill text** dentro de um arquivo PostScript (PS), o Aspose.Page para .NET torna isso simples. Seja gerando relatórios, faturas ou gráficos personalizados, adicionar e estilizar texto é um requisito fundamental. Neste tutorial, percorreremos todo o processo — desde a configuração do ambiente até a gravação do documento PS final — para que você possa adicionar texto a arquivos PS em suas aplicações .NET com confiança.

## Respostas Rápidas
- **What does “fill text” mean?** Ele renderiza caracteres usando um pincel sólido, pintando os glifos diretamente na página.  
- **Can I use custom fonts?** Sim—Aspose.Page suporta fontes personalizadas via o recurso `add custom font ps`.  
- **How do I save the PS document?** Chame `document.Save()` após fechar a página; isso grava o arquivo no disco (`save ps document`).  
- **Is “fill and stroke text” supported?** Absolutamente; use `FillAndStrokeText` para aplicar preenchimento e contorno.  
- **What .NET versions are required?** Qualquer .NET Framework 4.5+ ou runtime .NET Core/5/6+.

## O que é “how to fill text” em um documento PS?

Preencher texto significa pintar os caracteres com uma cor sólida (ou pincel) sem contorno. No PostScript, isso é análogo ao operador `fill`. Aspose.Page abstrai isso em métodos fáceis de usar como `FillText` e `FillAndStrokeText`.

## Por que usar Aspose.Page para adicionar custom font ps?

- **Full font support** – fontes do sistema e fontes TrueType/OpenType externas funcionam imediatamente.  
- **Precise positioning** – você controla as coordenadas X/Y, tamanho e estilo.  
- **Rich styling** – combine preenchimentos, contornos e canetas para efeitos como “fill and stroke text”.  
- **Cross‑platform** – funciona no Windows, Linux e macOS com a mesma API.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

- **Aspose.Page for .NET** – baixe a biblioteca na [Aspose.Page .NET documentation](https://reference.aspose.com/page/net/).  
- **Document Directory** – uma pasta na sua máquina onde os arquivos PS de origem e saída ficarão (referida como *Your Document Directory* no código).  
- **Fonts Folder** – uma subpasta que contém quaisquer fontes personalizadas que você pretende usar.

## Importar Namespaces

Primeiro, importe os namespaces necessários para que o compilador saiba onde encontrar as classes que usaremos:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Guia Passo a Passo

### Passo 1: Criar Fluxo de Saída para o Documento PS  

Abrimos um `FileStream` que armazenará o arquivo PS gerado, configuramos `PsSaveOptions` para apontar para nossa pasta de fontes personalizadas e instanciamos um `PsDocument`.

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **Pro tip:** Mantenha o bloco `using` para garantir que o fluxo seja fechado automaticamente, o que também finaliza o arquivo PS (`save ps document`).

### Passo 2: Preencher Texto com uma Fonte do Sistema  

Aqui demonstramos a operação básica de **how to fill text** usando a fonte incorporada *Times New Roman*.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### Passo 3: Preencher Texto com uma Fonte Personalizada  

Se precisar de um visual específico, carregue uma fonte personalizada da pasta de fontes usando `ExternalFontCache.FetchDrFont`. Isso atende ao requisito **add custom font ps**.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### Passo 4: Contornar (Stroke) Texto com uma Fonte do Sistema  

O contorno desenha o contorno do glifo. Combine‑o com um preenchimento para um efeito “fill and stroke”.

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **Why this matters:** A chamada `FillAndStrokeText` demonstra como **fill and stroke text** em um único passo, proporcionando controle tipográfico mais rico.

### Passo 5: Contornar Texto com uma Fonte Personalizada  

A mesma técnica de contorno funciona com qualquer fonte personalizada que você tenha carregado.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### Passo 6: Fechar a Página e Salvar o Documento  

Finalizar é simples: feche a página atual e invoque `Save()` para gravar o arquivo PS no disco.

```csharp
document.ClosePage();
document.Save();
}
```

> **Result:** Você encontrará `AddText_outPS.ps` em *Your Document Directory*, contendo texto preenchido e contornado renderizado com fontes do sistema e personalizadas.

## Problemas Comuns e Soluções

| Problema | Solução |
|----------|---------|
| **Fonte personalizada não encontrada** | Verifique se o arquivo de fonte (.ttf/.otf) existe na pasta referenciada por `AdditionalFontsFolders`. |
| **Texto aparece na posição errada** | Ajuste as coordenadas X/Y passadas para `FillText`/`OutlineText`. Lembre‑se de que o PostScript usa pontos (1/72 polegada). |
| **Cores parecem diferentes** | Certifique‑se de que está usando `SolidBrush` ou `Pen` com os valores corretos de `Color`. |
| **Documento não está sendo salvo** | Confirme que o bloco `using` termina sem exceções e que a aplicação tem permissão de escrita na pasta de destino. |

## Perguntas Frequentes

**Q: Posso usar Aspose.Page com outras bibliotecas .NET?**  
A: Sim, Aspose.Page integra‑se perfeitamente com outros componentes .NET, permitindo combinar bibliotecas de PDF, imagem ou gráficos na mesma solução.

**Q: As fontes personalizadas são essenciais para este processo?**  
A: Embora as fontes do sistema funcionem bem, fontes personalizadas dão total liberdade de design e são úteis quando a tipografia específica da marca é necessária.

**Q: O Aspose.Page é adequado para processamento de documentos em larga escala?**  
A: Absolutamente. A biblioteca é otimizada para cenários de alto volume e pode lidar eficientemente com milhares de arquivos PS.

**Q: Posso modificar a posição do texto no documento PS?**  
A: Certamente — basta alterar os valores numéricos X/Y nas chamadas `FillText` ou `OutlineText`.

**Q: Onde posso buscar assistência para dúvidas relacionadas ao Aspose.Page?**  
A: Visite o [Aspose.Page Forum](https://forum.aspose.com/c/page/39) para conectar‑se com a comunidade e obter ajuda de especialistas.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2026-03-21  
**Testado com:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose