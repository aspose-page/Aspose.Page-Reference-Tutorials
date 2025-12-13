---
date: 2025-12-13
description: Aprenda como adicionar texto em uma página ASP em Java, definir o estilo
  de fonte em Java e como inserir texto Unicode usando Aspose.Page. Siga nosso guia
  passo a passo.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: página asp adiciona texto – Unicode em Java PostScript
url: /pt/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page add text – Unicode em Java PostScript

## Introdução
Se você precisa **asp page add text** em um fluxo de trabalho Java PostScript preservando caracteres Unicode, chegou ao lugar certo. Neste tutorial vamos percorrer a inserção de texto Unicode, a definição do estilo da fonte e a gravação do resultado usando **Aspose.Page for Java**. Ao final, você entenderá como definir font style java e como adicionar unicode text de forma eficiente em seus projetos.

## Respostas rápidas
- **Qual biblioteca pode adicionar texto Unicode em Java PostScript?** Aspose.Page for Java.  
- **Qual método principal adiciona texto?** `doc.addGlyphs(...)` com um objeto `XpsGlyphs`.  
- **Preciso de uma fonte especial para Unicode?** Qualquer fonte TrueType/OpenType que suporte os pontos de código necessários (por exemplo, Arial).  
- **Posso alterar o estilo da fonte?** Sim, usando `XpsFontStyle` (Regular, Bold, Italic, etc.).  
- **É necessária licença para produção?** Sim, uma licença válida do Aspose.Page é necessária para uso não‑trial.

## O que é asp page add text?
`asp page add text` refere‑se ao processo de inserção de cadeias de texto em um documento PostScript ou XPS usando a API Aspose.Page. A API abstrai comandos de baixo nível do PostScript, permitindo que você trabalhe com objetos de alto nível como `XpsGlyphs`.

## Por que usar Aspose.Page para set font style java e add Unicode text?
- **Suporte total a Unicode** – Lida com scripts da direita para a esquerda e glifos complexos.  
- **API simples** – Chamadas de uma linha para adicionar texto e aplicar estilos.  
- **Multiplataforma** – Funciona em qualquer ambiente compatível com Java.  
- **Sem dependências externas** – Não é necessário nenhum motor de renderização adicional.

## Pré‑requisitos
Antes de mergulharmos no tutorial, certifique‑se de que você possui os seguintes pré‑requisitos:

1. **Java Development Kit (JDK)** – Verifique se o Java está instalado na sua máquina.  
2. **Aspose.Page for Java** – Baixe e instale a biblioteca Aspose.Page a partir do [download link](https://releases.aspose.com/page/java/).  
3. **Integrated Development Environment (IDE)** – Escolha sua IDE Java preferida, como IntelliJ IDEA ou Eclipse.

## Importar pacotes
No seu projeto Java, importe os pacotes necessários para o Aspose.Page. Adicione as linhas a seguir ao seu código:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Etapa 1: Configurar seu projeto
Crie um novo projeto Java na sua IDE e configure a estrutura do projeto. Certifique‑se de incluir a biblioteca Aspose.Page nas dependências do projeto.

## Etapa 2: Inicializar o documento XPS
Comece inicializando um novo documento XPS dentro do seu projeto:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Etapa 3: Adicionar texto Unicode
Agora, vamos adicionar texto Unicode ao seu documento XPS usando a biblioteca Aspose.Page. Use o trecho de código a seguir:

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

Este segmento de código adiciona o texto Unicode **"AVAJ rof SPX.esopsA"** ao documento XPS nas coordenadas (400, 200) com a fonte e estilo especificados. Observe como a chamada `setBidiLevel(1)` habilita a renderização da direita para a esquerda para exibição correta do Unicode.

## Etapa 4: Salvar o documento
Salve o documento XPS resultante usando o código a seguir:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

## Conclusão
Parabéns! Você adicionou com sucesso **asp page add text** e definiu o estilo da fonte em um cenário Java PostScript usando Aspose.Page. Esse método oferece controle granular sobre a renderização e o estilo Unicode, tornando‑o ideal para relatórios, faturas e gráficos internacionalizados.

Sinta‑se à vontade para explorar mais recursos e capacidades do Aspose.Page na [documentation](https://reference.aspose.com/page/java/).

## Perguntas Frequentes

**Q:** Posso usar Aspose.Page for Java com outras linguagens de programação?  
**A:** Aspose.Page foi projetado principalmente para Java, mas a Aspose fornece bibliotecas para várias linguagens de programação.

**Q:** Existe uma versão de avaliação gratuita disponível?  
**A:** Sim, você pode acessar uma avaliação gratuita do Aspose.Page [aqui](https://releases.aspose.com/).

**Q:** Onde posso encontrar suporte e discussões sobre Aspose.Page?  
**A:** Visite o [Aspose.Page forum](https://forum.aspose.com/c/page/39) para suporte e discussões.

**Q:** Como posso obter uma licença temporária para Aspose.Page?  
**A:** Você pode adquirir uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

**Q:** Quais estilos de fonte estão disponíveis no Aspose.Page?  
**A:** Aspose.Page suporta estilos de fonte como Regular, Bold, Italic e BoldItalic.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2025-12-13  
**Testado com:** Aspose.Page for Java (latest)  
**Autor:** Aspose  

---