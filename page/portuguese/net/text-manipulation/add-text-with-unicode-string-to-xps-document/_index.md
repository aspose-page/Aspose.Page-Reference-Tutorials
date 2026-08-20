---
date: 2026-03-21
description: Aprenda como adicionar texto Unicode a um documento XPS usando Aspose.Page
  para .NET. Este guia mostra como criar um documento XPS em C# e adicionar texto
  com strings Unicode usando Aspose.Page.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Como adicionar texto Unicode a um documento XPS com Aspose.Page
url: /pt/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Adicionar Texto Unicode a um Documento XPS com Aspose.Page

## Introdução

Se você precisa **how to add unicode** caracteres a um arquivo XPS, chegou ao lugar certo. Neste tutorial vamos percorrer os passos exatos necessários para **create XPS document C#**‑style usando Aspose.Page para .NET e demonstrar a capacidade **aspose page add text** com uma string Unicode. Ao final, você terá um documento XPS totalmente funcional que exibe texto Unicode da direita para a esquerda (RTL) corretamente.

## Respostas Rápidas
- **O que o tutorial cobre?** Adicionar texto Unicode a um documento XPS com Aspose.Page para .NET.  
- **Qual linguagem é usada?** C# (compatível com .NET Framework e .NET Core).  
- **Preciso de uma licença?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Posso mudar a fonte ou o tamanho?** Sim – o exemplo usa Arial 20 pt, mas qualquer fonte instalada funciona.  
- **O suporte RTL está incluído?** Definir `BidiLevel = 1` habilita a renderização da direita‑para‑esquerda para strings Unicode.

## O que é “how to add unicode” em XPS?

Adicionar texto Unicode significa inserir caracteres de qualquer idioma — árabe, hebraico, chinês, etc. — em um documento XPS. A classe `XpsGlyphs` do Aspose.Page lida com o posicionamento de glifos em baixo nível, enquanto a propriedade `BidiLevel` controla a direção do texto para scripts RTL.

## Por que usar Aspose.Page para adicionar texto?

- **Integração completa com .NET** – funciona com .NET Framework, .NET Core, .NET 5/6+.  
- **Sem dependências externas** – código totalmente gerenciado, sem interop COM.  
- **Suporte avançado a tipografia** – fontes, estilos, cores e texto bidirecional.  
- **Alto desempenho** – cria e salva arquivos XPS rapidamente, ideal para geração no lado do servidor.

## Pré‑requisitos

- Conhecimento básico de C# e desenvolvimento .NET.  
- Visual Studio (qualquer versão recente).  
- Biblioteca Aspose.Page para .NET – faça o download [aqui](https://releases.aspose.com/page/net/).

## Importar Namespaces

Primeiro, importe os namespaces que dão acesso ao modelo XPS e às utilidades de desenho.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Etapa 1: Configurar o Documento – create XPS document C#

Crie um novo documento XPS que hospedará o texto Unicode.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Etapa 2: Adicionar Texto Unicode – aspose page add text

Agora adicionamos a string Unicode real. Neste exemplo usamos a fonte Arial, tamanho 20, e posicionamos o texto em (400 f, 200 f). O `BidiLevel` de 1 indica ao renderizador que a string deve ser tratada como da direita para a esquerda.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Etapa 3: Salvar o Documento

Por fim, persista o arquivo XPS no disco.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Parabéns! Você adicionou com sucesso texto **how to add unicode** a um documento XPS usando Aspose.Page para .NET.

## Problemas Comuns e Soluções

| Problema | Motivo | Correção |
|----------|--------|----------|
| Texto aparece corrompido | A fonte não suporta a faixa Unicode | Use uma fonte que contenha os glifos necessários (por exemplo, Arial Unicode MS). |
| Texto RTL ainda da esquerda para a direita | `BidiLevel` não está definido ou está definido como 0 | Certifique‑se de que `glyphs.BidiLevel = 1;` para scripts RTL. |
| Arquivo não salvo | Caminho `dataDir` inválido | Verifique se o diretório existe e se o aplicativo tem permissões de gravação. |

## Perguntas Frequentes

**Q: O Aspose.Page é compatível com os frameworks .NET mais recentes?**  
A: Sim, o Aspose.Page é atualizado regularmente para suportar .NET Framework, .NET Core e .NET 5/6+.

**Q: Posso personalizar o estilo e o tamanho da fonte ao adicionar texto?**  
A: Absolutamente! O método `AddGlyphs` permite especificar qualquer família de fonte, tamanho e `FontStyle` que você precisar.

**Q: Onde posso encontrar documentação adicional para o Aspose.Page?**  
A: Você pode consultar a documentação [aqui](https://reference.aspose.com/page/net/) para detalhes abrangentes da API.

**Q: Existem recursos gratuitos para começar com o Aspose.Page?**  
A: Sim, explore o fórum da comunidade em [Aspose.Page forum](https://forum.aspose.com/c/page/39) para dicas, exemplos e suporte da comunidade.

**Q: Existe uma versão de avaliação disponível antes de comprar?**  
A: Certamente! Baixe a versão de avaliação gratuita [aqui](https://releases.aspose.com/) para avaliar a biblioteca.

---

**Última atualização:** 2026-03-21  
**Testado com:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}