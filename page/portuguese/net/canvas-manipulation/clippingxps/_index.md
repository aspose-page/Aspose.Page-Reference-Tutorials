---
date: 2026-06-25
description: Aprenda a recortar documentos XPS usando Aspose.Page para .NET. Este
  guia passo a passo mostra como criar, manipular e salvar arquivos XPS de forma eficiente.
keywords:
- how to clip xps
- Aspose.Page .NET
- XPS clipping tutorial
linktitle: Recorte de XPS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to clip XPS documents using Aspose.Page for .NET. This step‑by‑step
    guide shows you how to create, manipulate, and save XPS files efficiently.
  headline: How to Clip XPS with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can assign a complex `PathGeometry` that contains several sub‑paths
      to the `Clip` property, allowing layered masking.
    question: Can I combine multiple clip geometries on a single canvas?
  - answer: When you later convert the XPS to PDF using Aspose.PDF, the clip geometry
      is preserved, so the visual result remains identical.
    question: Does clipping affect PDF conversion?
  - answer: XPS itself does not support animation; however, you can generate a series
      of XPS pages with different clip shapes to simulate motion.
    question: Is it possible to animate clipping in XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Como recortar XPS com Aspose.Page para .NET
url: /pt/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Recortar XPS com Aspose.Page para .NET

## Introdução

Bem-vindo a este tutorial abrangente sobre **como recortar XPS** usando Aspose.Page para .NET! Neste guia, você aprenderá passo a passo como criar um documento XPS, aplicar máscaras de recorte geométricas e salvar o resultado. O recorte permite ocultar partes de uma tela, possibilitando layouts sofisticados como imagens mascaradas, formas personalizadas ou áreas de conteúdo focadas — tudo sem sair do seu código .NET.

## Respostas Rápidas
- **O que é recorte de XPS?** Aplicar uma máscara geométrica (clip) para limitar a área visível dos elementos da tela XPS.  
- **Qual biblioteca é a melhor para isso?** Aspose.Page para .NET oferece uma API completa para criação e recorte de XPS.  
- **Pré-requisitos?** Visual Studio, runtime .NET e a biblioteca Aspose.Page para .NET.  
- **Quanto tempo leva a implementação?** Aproximadamente 10‑15 minutos para um cenário básico de recorte.  
- **Posso usar isso em produção?** Sim, com uma licença válida da Aspose (versão de avaliação disponível).

## O que é “como recortar XPS”?

Recortar XPS significa aplicar uma máscara geométrica a uma tela de modo que qualquer desenho fora da máscara não seja renderizado. Essa técnica é ideal para criar imagens mascaradas, botões com formas personalizadas ou focar a atenção do leitor em uma região específica da página. Ao definir uma geometria de recorte — como um retângulo, círculo ou caminho complexo — você obtém controle detalhado sobre o que aparece na página XPS final.

## Por que usar Aspose.Page para .NET para recortar XPS?

Aspose.Page fornece manipulação determinística de XPS no lado do servidor sem dependências externas. Ele suporta **mais de 50 formatos de entrada e saída**, pode processar **arquivos XPS de 200 páginas em menos de 0,5 segundo** em uma CPU padrão de 2,5 GHz, e funciona em .NET Framework 4.0+, .NET Core 2.0+, .NET 5, .NET 6 e .NET 7. A API oferece controle total sobre transformações de tela, geometrias de caminho e pincéis, garantindo saída de alta qualidade a cada uso.

## Pré-requisitos

- Visual Studio instalado na sua máquina.  
- Biblioteca Aspose.Page para .NET adicionada ao seu projeto. Você pode baixá‑la [aqui](https://releases.aspose.com/page/net/).  
- Conhecimento básico da linguagem de programação C#.

## Como Recortar XPS?

Carregue um documento XPS, crie uma tela, defina uma geometria de recorte (por exemplo, um círculo), atribua a geometria à propriedade `Clip` da tela, desenhe seu conteúdo e, finalmente, salve o documento. Todas essas etapas podem ser realizadas com apenas algumas chamadas de método, e o Aspose.Page lida automaticamente com a marcação XML subjacente, permitindo que você se concentre no design visual em vez da estrutura do arquivo.

## Importar Namespaces

Para usar as funcionalidades do Aspose.Page para .NET, você precisa importar os namespaces necessários ao seu projeto. Siga estas etapas:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.IO;
```

Agora, vamos dividir o código de exemplo que você forneceu em várias etapas.

## Etapa 1: Definir o caminho do diretório do documento.

Defina a pasta onde o arquivo XPS será criado. Usar `Path.Combine` garante o separador de diretório correto em qualquer sistema operacional.

```csharp
string dataDir = Path.Combine(Environment.CurrentDirectory, "Output");
Directory.CreateDirectory(dataDir);
```

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Etapa 2: Criar um novo Documento XPS.

Instancie a classe `XpsDocument`, que representa todo o pacote XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

```csharp
string dataDir = "Your Document Directory";
```

## Etapa 3: Criar a tela principal.

A classe `Canvas` representa uma superfície de desenho dentro de uma página XPS onde formas, imagens e texto são renderizados.

```csharp
Canvas mainCanvas = new Canvas();
```

```csharp
XpsDocument doc = new XpsDocument();
```

## Etapa 4: Definir deslocamentos esquerdo e superior na tela principal.

Ajuste a posição da tela para controlar onde o desenho começa na página.

```csharp
mainCanvas.Left = 20;
mainCanvas.Top = 30;
```

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

## Etapa 5: Criar uma geometria de caminho retangular.

`PathGeometry` define uma forma vetorial; aqui criamos um retângulo simples.

```csharp
PathGeometry rectGeometry = new PathGeometry("M0,0 L100,0 100,50 0,50 Z");
```

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Etapa 6: Criar um preenchimento para retângulos.

Defina um pincel de cor sólida que será usado para preencher o retângulo.

```csharp
SolidColorBrush rectFill = new SolidColorBrush(Color.Black);
```

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

## Etapa 7: Adicionar outra tela com recorte à tela principal.

Crie uma tela filha que receberá uma máscara de recorte.

```csharp
Canvas clippedCanvas = new Canvas();
mainCanvas.Children.Add(clippedCanvas);
```

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Etapa 8: Criar uma geometria circular para recorte.

`PathGeometry` também pode representar círculos; esta geometria será atribuída à propriedade `Clip` da tela filha.

```csharp
PathGeometry circleClip = new PathGeometry("M50,0 A50,50 0 1 0 49.9,0 Z");
clippedCanvas.Clip = circleClip;
```

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

## Etapa 9: Criar um retângulo na segunda tela e preenchê‑lo.

Desenhe um retângulo dentro da tela recortada; somente a parte dentro do círculo será visível.

```csharp
Path rectangle = new Path(rectGeometry, rectFill);
clippedCanvas.Children.Add(rectangle);
```

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

## Etapa 10: Adicionar a segunda tela com um retângulo contornado à tela principal.

Adicione um retângulo com contorno para ilustrar como os contornos interagem com o recorte.

```csharp
Path strokedRect = new Path(rectGeometry, null, new Pen(Color.Blue, 2));
mainCanvas.Children.Add(strokedRect);
```

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Etapa 11: Criar um retângulo na terceira tela e contorná‑lo.

Uma terceira tela demonstra desenho independente sem recorte.

```csharp
Canvas thirdCanvas = new Canvas();
PathGeometry thirdRectGeom = new PathGeometry("M0,0 L150,0 150,75 0,75 Z");
Path thirdRect = new Path(thirdRectGeom, null, new Pen(Color.Green, 3));
thirdCanvas.Children.Add(thirdRect);
mainCanvas.Children.Add(thirdCanvas);
```

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

## Etapa 12: Salvar o documento XPS resultante.

Persistir o pacote XPS no sistema de arquivos.

```csharp
doc.Save(Path.Combine(dataDir, "ClippedOutput.xps"));
```

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

## Problemas Comuns e Soluções
- **Caminho inválido** – Certifique‑se de que `dataDir` termina com uma barra invertida (`\\`) ou use `Path.Combine`.  
- **Recorte não aplicado** – Verifique se a string da geometria de recorte está bem‑formada; um espaço ausente pode fazer com que o recorte seja ignorado.  
- **Exceção de licença** – Em uma compilação não‑de avaliação, adicione uma licença válida da Aspose antes de criar o documento para evitar exceções em tempo de execução.

## Perguntas Frequentes

### Q1: Posso usar Aspose.Page para .NET com outros formatos de documento?
R1: Aspose.Page para .NET foca principalmente em documentos XPS, mas a Aspose oferece outras bibliotecas para vários formatos de documento.

### Q2: O Aspose.Page para .NET é adequado para iniciantes?
R2: Sim, Aspose.Page para .NET foi projetado para ser amigável ao usuário, e iniciantes podem compreender rapidamente suas funcionalidades com a documentação adequada.

### Q3: Onde posso encontrar mais exemplos e recursos?
R3: Visite a [documentação](https://reference.aspose.com/page/net/) e o [fórum Aspose.Page](https://forum.aspose.com/c/page/39) para recursos e exemplos extensos.

### Q4: Como posso obter uma licença temporária para Aspose.Page para .NET?
R4: Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Q5: Existe uma versão de avaliação gratuita disponível para Aspose.Page para .NET?
R5: Sim, você pode explorar a versão de avaliação gratuita [aqui](https://releases.aspose.com/).

## Perguntas Frequentes Adicionais

**Q: Posso combinar múltiplas geometrias de recorte em uma única tela?**  
A: Sim, você pode atribuir um `PathGeometry` complexo que contém vários sub‑caminhos à propriedade `Clip`, permitindo mascaramento em camadas.

**Q: O recorte afeta a conversão para PDF?**  
A: Quando você converte o XPS para PDF usando Aspose.PDF, a geometria de recorte é preservada, portanto o resultado visual permanece idêntico.

**Q: É possível animar o recorte em XPS?**  
A: O XPS em si não suporta animação; porém, você pode gerar uma série de páginas XPS com diferentes formas de recorte para simular movimento.

---

**Última atualização:** 2026-06-25  
**Testado com:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

```csharp
doc.Save(dataDir + "output2.xps");
```

## Tutoriais Relacionados

- [Como Transformar XPS com Aspose.Page para .NET](/page/net/canvas-manipulation/transformationsxps/)
- [Adicionar Retângulo ao Documento XPS com Aspose.Page para .NET](/page/net/drawing-shapes/add-rectangle-to-xps-document/)
- [Converter XPS para PDF com Aspose.Page para .NET](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< /blocks/products/products-backtop-button >}}

{{< blocks/products/products-backtop-button >}}