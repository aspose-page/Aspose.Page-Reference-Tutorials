---
date: 2026-05-25
description: Aprenda a modificar xmp em documentos EPS usando Java com Aspose.Page.
  Atualize metadata rapidamente e de forma confiável.
keywords:
- how to modify xmp
- Aspose.Page Java
- XMP metadata EPS
linktitle: Alterar valores em XMP usando Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to modify xmp in EPS documents using Java with Aspose.Page.
    Update metadata quickly and reliably.
  headline: how to modify xmp with Aspose.Page – Change Values in XMP using Java
  type: TechArticle
- questions:
  - answer: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` to ensure consistency
      in time zone settings.
    question: How can I handle time zone considerations when modifying XMP values?
  - answer: Yes, by using the `put` method for each desired value, you can modify
      multiple XMP values concurrently.
    question: Can I change multiple XMP values in a single operation?
  - answer: Explore the comprehensive documentation [here](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation for Aspose.Page for Java?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: como modificar xmp com Aspose.Page – Alterar valores em XMP usando Java
url: /pt/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Alterar Valores em XMP usando Java

## Introdução
Se você está procurando **como modificar xmp** dentro de um arquivo EPS com Java, chegou ao lugar certo. Este tutorial guia você por cada passo — lendo o bloco XMP existente, atualizando campos como criador, título e data de modificação, e finalmente persistindo as alterações de volta ao documento EPS. Ao final, você terá um trecho reutilizável que se encaixa em qualquer fluxo de trabalho automatizado, garantindo que seus arquivos contenham os metadados corretos para branding, conformidade ou indexação por motores de busca.

## Respostas Rápidas
- **O que faz “aspose.page modify xmp”?** Permite ler e escrever metadados XMP em arquivos EPS via a API Aspose.Page Java.  
- **Qual versão da biblioteca é necessária?** Qualquer versão recente do Aspose.Page para Java (a API é estável entre versões).  
- **Preciso de licença para executar o exemplo?** Um teste gratuito funciona para avaliação; uma licença comercial é necessária para produção.  
- **Posso alterar vários campos XMP de uma vez?** Sim — chame `put` para cada campo antes de salvar o documento.  
- **É necessário tratar fusos horários?** Definir o fuso horário padrão (por exemplo, UTC) garante valores de data consistentes.

## O que é XMP e Por Que Modificá‑lo?
XMP (Extensible Metadata Platform) é um formato padronizado, baseado em XML, para incorporar metadados ricos diretamente dentro de arquivos como EPS, PDF e imagens. Atualizar o XMP permite controlar como os documentos são indexados, exibidos e pesquisados — crítico para consistência de marca, conformidade regulatória e pipelines de conteúdo automatizados.

## Por Que Usar Aspose.Page para Java?
Aspose.Page fornece uma **API completa, pura‑Java** que elimina a necessidade de ferramentas externas ou bibliotecas nativas. Suporta **mais de 50 formatos de entrada e saída** e pode processar arquivos EPS de até **500 MB** sem carregar o documento inteiro na memória, oferecendo manipulação rápida e de baixa memória de metadados em qualquer SO que execute Java.

## Pré‑requisitos
Antes de começarmos este tutorial, certifique‑se de que você tem os seguintes pré‑requisitos em vigor:
1. **Ambiente de Desenvolvimento Java** – Um JDK (8 ou superior) e uma IDE ou ferramenta de build de sua escolha.  
2. **Biblioteca Aspose.Page para Java** – Baixe e instale a biblioteca Aspose.Page para Java. Você pode encontrar o pacote necessário [aqui](https://releases.aspose.com/page/java/).

## Importar Pacotes
Comece importando os pacotes necessários para o seu projeto Java. Esses pacotes são essenciais para interagir e manipular documentos EPS.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Como modificar XMP em EPS usando Java?
`Document` é a classe Aspose.Page que representa um arquivo EPS e fornece acesso ao seu conteúdo e metadados. `XmpMetadata` representa o bloco XMP anexado ao documento e permite ler e escrever campos de metadados. `put` adiciona ou atualiza uma entrada de metadado no objeto XmpMetadata. `save` grava o documento modificado, incluindo quaisquer metadados XMP atualizados, em um arquivo.

Carregue o arquivo EPS com `new Document("input.eps")`, recupere seu objeto `XmpMetadata`, atualize as chaves desejadas usando `put` e, finalmente, chame `save` para gravar as alterações em um novo arquivo. Esse fluxo conciso lida automaticamente com blocos XMP ausentes, cria um a partir de comentários PostScript quando necessário e garante datas consistentes com o fuso horário.

## Etapa 1: Obter Metadados XMP
A classe `XmpMetadata` representa o bloco XMP anexado a um documento EPS. Quando você chama `document.getXmpMetadata()`, a API retorna o bloco existente ou cria um novo a partir de comentários PS como `%%Creator`, `%%CreateDate` e `%%Title`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Etapa 2: Alterar o Valor "ModifyDate"
Atualize a entrada "ModifyDate" para refletir o novo carimbo de data/hora de modificação. Use `java.util.Date` combinado com `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` para garantir que o valor armazenado seja independente de fuso horário.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Etapa 3: Alterar o Valor "Creator"
A chave "Creator" armazena o nome da aplicação ou pessoa que gerou o arquivo EPS. Chame `xmp.put("dc:creator", "Your Company Name")` para substituir o valor existente por um identificador personalizado.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Etapa 4: Alterar o Valor "Title"
O campo "Title" é exibido por muitos sistemas de gerenciamento de ativos. Defini‑lo via `xmp.put("dc:title", "New Document Title")` garante que o documento apareça corretamente em catálogos e resultados de busca.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Etapa 5: Salvar Documento com Metadados XMP Alterados
Após todas as modificações, invoque `document.save("output.eps")`. A biblioteca grava o bloco XMP atualizado de volta no fluxo EPS enquanto preserva o conteúdo gráfico original inalterado.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Problemas Comuns e Soluções
- **Bloco XMP ausente** – A API cria automaticamente um a partir de comentários PS, mas você também pode instanciar manualmente `XmpMetadata` se necessário.  
- **Descompasso de fuso horário** – Sempre defina `TimeZone.setDefault` antes de criar o objeto `Date` para evitar desvios inesperados.  
- **Erros de acesso a arquivos** – Certifique‑se de que os caminhos de entrada e saída estejam corretos e que sua aplicação tenha permissões de leitura/escrita.

## Perguntas Frequentes

**Q: Como posso lidar com considerações de fuso horário ao modificar valores XMP?**  
A: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` para garantir consistência nas configurações de fuso horário.

**Q: Posso alterar vários valores XMP em uma única operação?**  
A: Sim, usando o método `put` para cada valor desejado, você pode modificar vários valores XMP simultaneamente.

**Q: Onde posso encontrar documentação adicional para Aspose.Page para Java?**  
A: Explore a documentação abrangente [aqui](https://reference.aspose.com/page/java/).

**Q: Existe um teste gratuito disponível para Aspose.Page para Java?**  
A: Sim, você pode acessar o teste gratuito [aqui](https://releases.aspose.com/).

**Q: Como posso obter uma licença temporária para Aspose.Page para Java?**  
A: Obtenha uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

**Q: A modificação do XMP afeta o conteúdo visual do EPS?**  
A: Não. As alterações de XMP são apenas de metadados e não alteram os elementos gráficos do arquivo EPS.

**Q: Posso ler programaticamente os valores atualizados para verificar a alteração?**  
A: Absolutamente — basta chamar `xmp.get("dc:creator")` (ou a chave relevante) após salvar e antes de fechar o documento.

## Conclusão
Parabéns! Você dominou **como modificar valores xmp** em documentos EPS usando Aspose.Page para Java. Ao incorporar metadados precisos de criador, título e data de modificação, você garante que seus ativos sejam pesquisáveis, estejam em conformidade e alinhados com os padrões de branding. Sinta‑se à vontade para integrar este padrão em pipelines de processamento em lote, etapas de CI/CD ou qualquer fluxo de trabalho automatizado de geração de documentos.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose

## Tutoriais Relacionados

- [Tutorial Aspose Page Java – Adicionar Metadados XMP a Arquivos EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [Como Ler Metadados XMP usando Java – Guia Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp java - Alterar Itens de Array em XMP usando Java](/page/java/xmp-metadata-manipulation/change-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}