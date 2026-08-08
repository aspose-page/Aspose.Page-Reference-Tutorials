---
date: 2026-05-20
description: Aprenda como adicionar texto Unicode em Java PostScript usando Aspose.Page
  – um guia passo a passo sobre como inserir strings Unicode sem esforço.
keywords:
- how to add unicode
- java add arabic text
- java add chinese text
linktitle: Adicionar texto usando string Unicode em Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add Unicode text in Java PostScript using Aspose.Page
    – a step‑by‑step guide on how to add unicode strings effortlessly.
  headline: How to Add Unicode Text in Java PostScript with Aspose.Page
  type: TechArticle
- description: Learn how to add Unicode text in Java PostScript using Aspose.Page
    – a step‑by‑step guide on how to add unicode strings effortlessly.
  name: How to Add Unicode Text in Java PostScript with Aspose.Page
  steps:
  - name: '**Java Development Kit (JDK)** – Any recent version (8 or newer).'
    text: '**Java Development Kit (JDK)** – Any recent version (8 or newer).'
  - name: '**Aspose.Page for Java** – Download and install the library from the [download
      link](https://releases.aspose.com/page/java/). You can also browse all releases
      [here](https://releases.aspose.com/).'
    text: '**Aspose.Page for Java** – Download and install the library from the [download
      link](https://releases.aspose.com/page/java/). You can also browse all releases
      [here](https://releases.aspose.com/).'
  - name: '**IDE of your choice** – IntelliJ IDEA, Eclipse, or any other Java IDE
      you prefer.'
    text: '**IDE of your choice** – IntelliJ IDEA, Eclipse, or any other Java IDE
      you prefer.'
  type: HowTo
- questions:
  - answer: Aspose.Page is built specifically for Java, but Aspose offers equivalent
      libraries for .NET, C++, and Python if you need cross‑language support.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.Page [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      help, samples, and troubleshooting tips.
    question: Where can I find support and community discussions?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for testing?
  - answer: The API supports Regular, Bold, Italic, and BoldItalic styles for any
      TrueType or OpenType font you load.
    question: What font styles does Aspose.Page support?
  type: FAQPage
second_title: Aspose.Page Java API
title: Como adicionar texto Unicode em Java PostScript com Aspose.Page
url: /pt/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Adicionar Texto Unicode em Java PostScript com Aspose.Page

## Introdução
Se você está se perguntando **como adicionar Unicode** a um fluxo de trabalho PostScript (ou XPS) baseado em Java, chegou ao lugar certo. Neste tutorial vamos percorrer passo a passo as etapas necessárias para incorporar strings Unicode usando a biblioteca Aspose.Page para Java. Ao final do guia você será capaz de inserir texto em qualquer idioma — árabe, chinês, emojis, o que quiser — diretamente na sua saída PostScript.

## Respostas Rápidas
- **Qual biblioteca é necessária?** Aspose.Page para Java  
- **Posso adicionar scripts da direita para a esquerda?** Sim, defina o nível Bidi conforme mostrado no código  
- **Preciso de licença para desenvolvimento?** Uma avaliação gratuita funciona para testes; uma licença comercial é necessária para produção  
- **Qual IDE funciona melhor?** Qualquer IDE Java (IntelliJ IDEA, Eclipse, NetBeans)  
- **O código é multiplataforma?** Absolutamente — execute-o no Windows, macOS ou Linux  

## O que significa “como adicionar Unicode” no contexto do PostScript?
Adicionar texto Unicode significa incorporar caracteres cujos pontos de código estão fora do intervalo ASCII básico — como árabe, chinês ou emoji — em um documento PostScript (ou XPS) usando Aspose.Page. A biblioteca mapeia automaticamente esses pontos de código para os glifos apropriados na fonte selecionada, lidando com modelagem complexa, ligaduras e ordenação da direita para a esquerda sem necessidade de codificação manual.

## Por que usar Aspose.Page para texto Unicode?
Aspose.Page oferece uma solução confiável, 100 % pura‑Java que suporta **mais de 50 formatos de entrada e saída** e pode renderizar texto multilíngue em documentos de até 1.000 páginas sem carregar o arquivo inteiro na memória. Ela elimina a necessidade de utilitários externos de manipulação de fontes, reduz o tempo de desenvolvimento em 70 % e garante saída visual consistente em ambientes Windows, macOS e Linux.

## Pré‑requisitos
Antes de começarmos, certifique‑se de que você tem os seguintes itens prontos:

1. **Java Development Kit (JDK)** – Qualquer versão recente (8 ou superior).  
2. **Aspose.Page para Java** – Baixe e instale a biblioteca a partir do [link de download](https://releases.aspose.com/page/java/). Você também pode navegar por todas as versões [aqui](https://releases.aspose.com/).  
3. **IDE de sua escolha** – IntelliJ IDEA, Eclipse ou qualquer outra IDE Java que preferir.

## Importar Pacotes
Adicione as classes necessárias do Aspose.Page ao seu arquivo fonte Java:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Etapa 1: Configurar Seu Projeto
Crie um novo projeto Java, adicione o JAR do Aspose.Page ao caminho de compilação do projeto e crie uma pasta onde o arquivo XPS gerado será salvo. Essa pasta será referenciada mais adiante como `dataDir`.

## Etapa 2: Inicializar Documento XPS
A classe `XpsDocument` representa um arquivo XPS na memória e fornece a tela para todas as operações de desenho.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Etapa 3: Adicionar Texto Unicode
Agora vamos realmente adicionar a string Unicode. O exemplo abaixo grava a frase invertida “AVAJ rof SPX.esopsA”, que contém apenas caracteres ASCII, mas você pode substituí‑la por qualquer texto Unicode (por exemplo, árabe “مرحبا” ou chinês “你好”). É assim que você **java add arabic text** ou **java add chinese text** ao seu documento.

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **Dica profissional:** Para renderizar idiomas da direita para a esquerda corretamente, defina `glyphs.setBidiLevel(1);`. Para scripts da esquerda para a direita você pode omitir esta linha.

## Etapa 4: Salvar o Documento
Persista o arquivo XPS no disco:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

Após executar o programa, abra o `AddEncodingText_out.xps` gerado com qualquer visualizador XPS para ver o texto Unicode renderizado nas coordenadas especificadas.

## Problemas Comuns e Soluções
| Problema | Motivo | Solução |
|----------|--------|---------|
| O texto aparece como quadrados | Fonte não encontrada ou não suporta os caracteres | Use uma fonte que inclua os glifos necessários (por exemplo, “Arial Unicode MS”) |
| Texto da direita‑para‑esquerda é exibido da esquerda‑para‑direita | Nível Bidi não definido | Chame `glyphs.setBidiLevel(1);` |
| Arquivo não salvo | Caminho `dataDir` inválido ou sem permissões de gravação | Certifique‑se de que o diretório exista e que a aplicação tenha acesso de escrita |

## Perguntas Frequentes
**P: Posso usar Aspose.Page para Java com outras linguagens de programação?**  
R: Aspose.Page foi desenvolvido especificamente para Java, mas a Aspose oferece bibliotecas equivalentes para .NET, C++ e Python caso você precise de suporte multiplataforma.

**P: Existe uma avaliação gratuita disponível?**  
R: Sim, você pode acessar uma avaliação gratuita do Aspose.Page [aqui](https://releases.aspose.com/).

**P: Onde posso encontrar suporte e discussões da comunidade?**  
R: Visite o [fórum Aspose.Page](https://forum.aspose.com/c/page/39) para ajuda, exemplos e dicas de solução de problemas.

**P: Como obtenho uma licença temporária para testes?**  
R: Você pode adquirir uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

**P: Quais estilos de fonte o Aspose.Page suporta?**  
R: A API suporta estilos Regular, Bold, Italic e BoldItalic para qualquer fonte TrueType ou OpenType que você carregar.

## Conclusão
Agora você domina **como adicionar texto Unicode** a um documento Java PostScript (XPS) usando Aspose.Page. Essa capacidade abre portas para relatórios multilíngues, faturas internacionalizadas e qualquer cenário onde caracteres não‑ASCII sejam necessários. Sinta‑se à vontade para explorar recursos adicionais como rotação de texto, caminhos de recorte ou incorporação de fontes personalizadas — detalhes estão disponíveis na documentação oficial [aqui](https://reference.aspose.com/page/java/).

---

**Última atualização:** 2026-05-20  
**Testado com:** Aspose.Page para Java 23.12 (mais recente na data de escrita)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [How to Add Text in PostScript with Aspose.Page for Java](/page/java/postscript-text-manipulation/)
- [Set Text Color Java with Aspose.Page – Text Manipulation Guide](/page/java/postscript-text-manipulation/add-text/)
- [Add Pages PostScript Java – A Seamless Guide with Aspose.Page](/page/java/postscript-page-manipulation/add-pages1/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}