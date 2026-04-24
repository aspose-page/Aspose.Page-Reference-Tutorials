---
date: 2026-01-05
description: Aprenda a recortar documentos XPS usando o Aspose.Page para .NET. Este
  guia passo a passo mostra como criar, manipular e salvar arquivos XPS de forma eficiente.
linktitle: Clipping XPS
second_title: Aspose.Page .NET API
title: Como recortar XPS com Aspose.Page para .NET
url: /pt/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como recortar XPS com Aspose.Page para .NET

## Introdução

Bem‑vindo a este tutorial abrangente sobre **como recortar XPS** usando Aspose.Page para .NET! Neste guia, vamos conduzi‑lo pelo processo de criação, manipulação e salvamento de documentos XPS com a biblioteca. XPS, ou XML Paper Specification, é um formato de documento padronizado e aberto, e Aspose.Page para .NET fornece ferramentas poderosas para trabalhar com documentos XPS em suas aplicações .NET.

## Respostas rápidas
- **O que é recortar XPS?** Aplicar uma máscara geométrica (clip) para limitar a área visível dos elementos de canvas XPS.  
- **Qual biblioteca é a melhor para isso?** Aspose.Page para .NET oferece uma API completa para criação e recorte de XPS.  
- **Pré‑requisitos?** Visual Studio, runtime .NET e a biblioteca Aspose.Page para .NET.  
- **Quanto tempo leva a implementação?** Aproximadamente 10‑15 minutos para um cenário básico de recorte.  
- **Posso usar isso em produção?** Sim, com uma licença válida da Aspose (versão de avaliação disponível).

## O que é “como recortar XPS”?
O recorte em XPS funciona definindo uma **geometria de clip** (por exemplo, um círculo ou retângulo) e atribuindo‑a a um canvas. Qualquer coisa desenhada fora dessa geometria não é renderizada, permitindo criar layouts de página sofisticados, como imagens mascaradas, formas personalizadas ou áreas de conteúdo focadas.

## Por que usar Aspose.Page para .NET para recortar XPS?
- **Controle total** sobre transformações de canvas, geometria de caminhos e pincéis.  
- **Sem dependências externas** – tudo roda dentro da sua aplicação .NET.  
- **Suporte multiplataforma** para .NET Framework, .NET Core e .NET 5/6+.  
- **Alto desempenho** com uma API leve que gera arquivos XPS válidos.

## Pré‑requisitos

Antes de começarmos, certifique‑se de que você tem o seguinte:

- Visual Studio instalado na sua máquina.  
- Biblioteca Aspose.Page para .NET adicionada ao seu projeto. Você pode baixá‑la [aqui](https://releases.aspose.com/page/net/).  
- Conhecimento básico da linguagem de programação C#.

## Importar Namespaces

Para usar as funcionalidades do Aspose.Page para .NET, você precisa importar os namespaces necessários ao seu projeto. Siga estas etapas:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Agora, vamos dividir o código de exemplo que você forneceu em várias etapas.

## Etapa 1: Definir o caminho do diretório do documento.

```csharp
string dataDir = "Your Document Directory";
```

Certifique‑se de substituir “Your Document Directory” pelo caminho real do seu diretório de documentos.

## Etapa 2: Criar um novo documento XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

Isso cria um novo documento XPS com o qual você trabalhará.

## Etapa 3: Criar o canvas principal.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

Esta etapa cria o canvas principal, que é comum a todos os elementos da página.

## Etapa 4: Definir deslocamentos esquerdo e superior no canvas principal.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Ajuste os deslocamentos esquerdo e superior conforme suas necessidades.

## Etapa 5: Criar uma geometria de caminho retangular.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

Isso cria uma geometria de caminho para um retângulo.

## Etapa 6: Criar um preenchimento para os retângulos.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Defina a cor de preenchimento para os retângulos.

## Etapa 7: Adicionar outro canvas com clip ao canvas principal.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

Esta etapa adiciona outro canvas ao canvas principal.

## Etapa 8: Criar uma geometria circular para o clip.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Isso cria uma geometria de clip circular e a aplica ao segundo canvas.

## Etapa 9: Criar um retângulo no segundo canvas e preenchê‑lo.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Esta etapa cria um retângulo no segundo canvas e o preenche.

## Etapa 10: Adicionar o segundo canvas com um retângulo contornado ao canvas principal.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

Isso adiciona outro canvas ao canvas principal.

## Etapa 11: Criar um retângulo no terceiro canvas e contorná‑lo.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

Isso cria um retângulo no terceiro canvas e aplica um contorno a ele.

## Etapa 12: Salvar o documento XPS resultante.

```csharp
doc.Save(dataDir + "output2.xps");
```

Isso salva o documento XPS no diretório especificado.

## Problemas comuns e soluções
- **Caminho inválido** – Certifique‑se de que `dataDir` termina com uma barra invertida (`\\`) ou use `Path.Combine`.  
- **Clip não aplicado** – Verifique se a string da geometria de clip está bem‑formada; um espaço ausente pode fazer com que o clip seja ignorado.  
- **Exceção de licença** – Em uma compilação não‑de avaliação, adicione uma licença válida da Aspose antes de criar o documento para evitar exceções em tempo de execução.

## Perguntas Frequentes

### Q1: Posso usar Aspose.Page para .NET com outros formatos de documento?

A1: Aspose.Page para .NET foca principalmente em documentos XPS, mas a Aspose oferece outras bibliotecas para diversos formatos de documento.

### Q2: Aspose.Page para .NET é adequado para iniciantes?

A2: Sim, Aspose.Page para .NET foi projetado para ser amigável, e iniciantes podem compreender rapidamente suas funcionalidades com a documentação adequada.

### Q3: Onde posso encontrar mais exemplos e recursos?

A3: Visite a [documentação](https://reference.aspose.com/page/net/) e o [fórum Aspose.Page](https://forum.aspose.com/c/page/39) para recursos extensos e exemplos.

### Q4: Como posso obter uma licença temporária para Aspose.Page para .NET?

A4: Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Q5: Existe uma versão de avaliação gratuita para Aspose.Page para .NET?

A5: Sim, você pode explorar a avaliação gratuita [aqui](https://releases.aspose.com/).

## Perguntas Frequentes Adicionais

**Q: Posso combinar múltiplas geometrias de clip em um único canvas?**  
A: Sim, você pode atribuir um `PathGeometry` complexo que contém várias sub‑paths à propriedade `Clip`, permitindo mascaramento em camadas.

**Q: O recorte afeta a conversão para PDF?**  
A: Quando você converte o XPS para PDF usando Aspose.PDF, a geometria de clip é preservada, de modo que o resultado visual permanece idêntico.

**Q: É possível animar o recorte em XPS?**  
A: O XPS em si não suporta animação; porém, você pode gerar uma série de páginas XPS com diferentes formas de clip para simular movimento.

---

**Última atualização:** 2026-01-05  
**Testado com:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}