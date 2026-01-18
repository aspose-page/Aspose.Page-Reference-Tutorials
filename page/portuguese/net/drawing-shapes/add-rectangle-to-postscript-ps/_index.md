---
date: 2026-01-18
description: Aprenda como criar documentos PostScript .NET e adicionar retângulos
  usando Aspose.Page para .NET. Guia passo a passo com exemplos de código.
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: Criar documento PostScript .NET – Adicionar retângulo com Aspose.Page
url: /pt/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Retângulo ao PostScript (PS) com Aspose.Page para .NET

## Introdução

Se você está procurando **criar documento postscript .net**, Aspose.Page fornece uma solução poderosa para manipular arquivos PostScript. Neste tutorial, vamos guiá‑lo na adição de retângulos a um documento PostScript usando Aspose.Page para .NET, proporcionando uma base sólida para a geração de gráficos mais ricos.

## Respostas Rápidas
- **Qual biblioteca eu preciso?** Aspose.Page for .NET.  
- **Posso criar um documento PostScript do zero?** Sim – a API permite que você construa arquivos PS programaticamente.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Preciso de licença para desenvolvimento?** Um teste gratuito funciona para testes; uma licença é necessária para produção.  
- **Quanto tempo leva a implementação?** Normalmente menos de 10 minutos para formas básicas.

## O que é criar um documento postscript .net?
Criar um documento PostScript em .NET significa gerar programaticamente um arquivo .ps que descreve o conteúdo da página — texto, gráficos ou formas — usando a API Aspose.Page. Essa abordagem é ideal para geração de gráficos no lado do servidor, criação automatizada de relatórios ou qualquer cenário em que você precise de controle preciso sobre o formato de saída.

## Por que usar Aspose.Page para .NET?
- **Controle total sobre gráficos** – desenhe formas, defina cores e aplique traçados sem lidar com a sintaxe de baixo nível do PS.  
- **Multiplataforma** – funciona em runtimes Windows, Linux e macOS.  
- **Sem dependências externas** – a biblioteca trata de toda a geração de PS internamente.  
- **Documentação rica & exemplos** – comece a trabalhar rapidamente.

## Pré‑requisitos

- **Aspose.Page for .NET Library** – faça o download e instale a partir de [aqui](https://releases.aspose.com/page/net/).  
- **Ambiente de Desenvolvimento** – Visual Studio, VS Code ou qualquer IDE compatível com .NET.

## Importar Namespaces

Antes de começar a codificar, importe os namespaces que expõem as classes necessárias:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Agora vamos dividir o exemplo em etapas claras e numeradas.

## Etapa 1: Configurar o Diretório do Seu Documento

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Substitua `"Your Document Directory"` pela pasta onde você deseja salvar o arquivo PS resultante.

## Etapa 2: Criar Stream de Saída para o Documento PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Esse stream aponta para **AddRectangle_outPS.ps**. Sinta‑se à vontade para renomear o arquivo ou alterar o local conforme necessário.

## Etapa 3: Definir Opções de Salvamento e Criar o Documento PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Aqui informamos ao Aspose.Page para usar o tamanho de página A4 e criar um documento de uma única página.

## Etapa 4: Adicionar um Retângulo Preenchido

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Definimos um retângulo em (250, 100) com largura 150 e altura 100, definimos um pincel laranja e preenchemos a forma.

## Etapa 5: Adicionar um Retângulo Contornado

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Um segundo retângulo é criado mais abaixo na página, desta vez com um traço vermelho de 3 pontos.

## Etapa 6: Fechar a Página e Salvar o Documento

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Fechar a página finaliza o desenho, e `Save()` grava o arquivo PS no disco.

## Problemas Comuns & Dicas

- **Caminho de arquivo incorreto** – Certifique‑se de que `dataDir` termina com um separador de caminho (`\\` ou `/`) ou use `Path.Combine`.  
- **Licença ausente** – Em ambiente de produção, aplique sua licença Aspose antes de criar o documento para evitar marcas d'água de avaliação.  
- **Visibilidade da cor** – Se o retângulo aparecer em branco, verifique se as cores do pincel ou da caneta contrastam com o fundo da página.

## Perguntas Frequentes

**Q:** Posso personalizar as cores dos retângulos?  
**A:** Absolutamente. Altere os valores `Color.Orange` ou `Color.Red` nos construtores `SolidBrush` e `Pen` para qualquer `System.Drawing.Color` que preferir.

**Q:** O Aspose.Page é compatível com outros formatos de documento?  
**A:** Sim. Além de PostScript, o Aspose.Page também suporta geração de XPS e EPS.

**Q:** Como posso adicionar texto ao mesmo documento?  
**A:** Use a classe `TextFragment` para posicionar texto nas coordenadas desejadas e, em seguida, chame `document.Draw(textFragment)`.

**Q:** Onde posso encontrar exemplos adicionais e a referência completa da API?  
**A:** Explore a documentação [aqui](https://reference.aspose.com/page/net/) e participe da comunidade no [fórum Aspose.Page](https://forum.aspose.com/c/page/39).

**Q:** Posso experimentar o Aspose.Page antes de comprar?  
**A:** Sim, faça o download de um teste gratuito [aqui](https://releases.aspose.com/). Para avaliação prolongada, considere uma [licença temporária](https://purchase.aspose.com/temporary-license/).

---

**Última atualização:** 2026-01-18  
**Testado com:** Aspose.Page 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}