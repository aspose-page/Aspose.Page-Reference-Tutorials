---
date: 2026-02-23
description: Aprenda como adicionar gradiente a arquivos PostScript, salvar o arquivo
  PostScript com tamanho de página A4 e preencher o gradiente de retângulo usando
  Aspose.Page para .NET.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Como adicionar gradiente – Gradiente diagonal em PostScript (PS) com Aspose.Page
  .NET
url: /pt/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Adicionar Gradiente: Gradiente Diagonal ao PostScript (PS) com Aspose.Page .NET

## Introdução

Adicionar um gradiente diagonal a um documento PostScript (PS) pode melhorar drasticamente o apelo visual, especialmente quando você precisa de efeitos **como adicionar gradiente** em relatórios técnicos, brochuras ou aplicações intensivas em gráficos. Neste tutorial você verá exatamente como adicionar gradiente a um arquivo PostScript, definir o tamanho de página A4 e preencher um retângulo com uma transição de cores suave usando Aspose.Page para .NET.

## Respostas Rápidas
- **Qual biblioteca é necessária?** Aspose.Page for .NET  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **Posso mudar a direção do gradiente?** Sim – rotacione a transformação do brush conforme mostrado no código  
- **Como salvo o resultado?** Use `PsDocument.Save()` que grava um arquivo PostScript no disco  
- **É necessária uma licença para produção?** Sim, uma licença comercial desbloqueia toda a funcionalidade  

## O que é um gradiente diagonal no PostScript?

Um gradiente diagonal é uma transição de cor linear que se estende em um ângulo (tipicamente 45°) através de uma forma. No PostScript, isso é conseguido aplicando um `LinearGradientBrush` com uma matriz de transformação personalizada que rotaciona, escala e traduz o gradiente para corresponder ao retângulo desejado.

## Por que usar Aspose.Page para preenchimentos com gradiente?

Aspose.Page abstrai os comandos de baixo nível do PostScript, permitindo que você trabalhe com objetos gráficos familiares do .NET. Você pode criar preenchimentos complexos, definir dimensões de página e exportar diretamente para um **arquivo PostScript salvo** sem lidar com a sintaxe bruta do PS.

## Pré-requisitos

- **Aspose.Page for .NET Library** – faça o download [aqui](https://releases.aspose.com/page/net/).  
- **Document Directory** – uma pasta onde o arquivo `*.ps` gerado será gravado.

Agora que cobrimos o básico, vamos percorrer a implementação passo a passo.

## Importar Namespaces

Primeiro, importe os namespaces que dão acesso ao dispositivo EPS, utilitários de desenho e classes de I/O.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Etapa 1: Criar Fluxo de Saída para o Documento PostScript (Criar Documento PostScript)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Etapa 2: Definir Tamanho da Página A4 (Opções de Salvamento)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## Etapa 3: Criar um Novo Documento PS de 1 Página

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Etapa 4: Definir Parâmetros do Retângulo

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Etapa 5: Criar Caminho Gráfico

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Etapa 6: Criar Brush de Gradiente Linear (Preencher Gradiente do Retângulo)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Etapa 7: Criar Transformação para o Brush

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Etapa 8: Aplicar Transformações ao Brush (Rotacionar, Escalar, Traduzir)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Etapa 9: Definir Transformação no Brush

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## Etapa 10: Definir Pintura e Preencher o Retângulo

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## Etapa 11: Fechar a Página Atual

```csharp
	//Close current page
	document.ClosePage();
```

## Etapa 12: Salvar o Documento (Salvar Arquivo PostScript)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## Como Salvar o Arquivo PostScript

A chamada `PsDocument.Save()` grava o conteúdo PostScript totalmente formado no fluxo que você abriu na **Etapa 1**. Após a conclusão do bloco `using`, o arquivo `DiagonaGradient_outPS.ps` estará disponível no diretório que você especificou.

## Casos de Uso Comuns

- **Documentação técnica** que precisa de uma sombra de fundo sutil.  
- **Brochuras de marketing** onde um gradiente diagonal adiciona um visual moderno.  
- **Geradores automáticos de relatórios** que produzem arquivos PS imprimíveis em tempo real.

## Solução de Problemas & Dicas

- **Cores incorretas** – verifique novamente os valores ARGB passados para `LinearGradientBrush`.  
- **Gradiente não visível** – garanta que a matriz de transformação rotacione e escale corretamente; a chamada `Rotate(-45)` define o ângulo diagonal.  
- **Arquivo não criado** – verifique se `dataDir` aponta para uma pasta existente e se a aplicação tem permissões de escrita.

## Perguntas Frequentes

**Q: O Aspose.Page é compatível com todos os frameworks .NET?**  
A: Aspose.Page suporta uma ampla gama de versões do .NET, desde .NET Framework 4.5+ até .NET 6+, garantindo ampla compatibilidade.

**Q: Posso personalizar as cores do gradiente no Aspose.Page?**  
A: Sim, você pode especificar quaisquer cores ARGB ao construir `LinearGradientBrush`, dando controle total sobre as tonalidades inicial e final.

**Q: Existe uma versão de avaliação disponível para o Aspose.Page?**  
A: Sim, você pode explorar os recursos do Aspose.Page baixando a versão de avaliação [aqui](https://releases.aspose.com/).

**Q: Como posso obter uma licença temporária para o Aspose.Page?**  
A: Obtenha uma licença temporária para o Aspose.Page [aqui](https://purchase.aspose.com/temporary-license/) para desbloquear recursos adicionais durante a avaliação.

**Q: Onde posso encontrar suporte da comunidade para o Aspose.Page?**  
A: Interaja com a comunidade Aspose.Page no [fórum](https://forum.aspose.com/c/page/39) para obter assistência e discussões.

---

**Última atualização:** 2026-02-23  
**Testado com:** Aspose.Page for .NET (última versão estável)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}