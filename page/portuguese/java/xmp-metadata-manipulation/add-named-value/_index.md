---
date: 2026-09-19
description: Aprenda a adicionar valores nomeados XMP a arquivos EPS usando Aspose.Page
  for Java – um guia passo a passo com exemplos de código.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: Adicionar Valor Nomeado em XMP usando Java
og_description: Como adicionar valores nomeados XMP a arquivos EPS usando Aspose.Page
  for Java. Siga este guia conciso para inserir metadados personalizados em minutos.
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: Como adicionar valor nomeado XMP em arquivos EPS usando Java
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: Como adicionar valor nomeado XMP em arquivos EPS usando Java
url: /pt/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar valor nomeado nos metadados XMP usando Java

## Introdução
No desenvolvimento moderno em Java, aprender **como adicionar XMP** metadados dentro de arquivos EPS é essencial para preservar a proveniência do documento e melhorar a capacidade de busca. Com **Aspose.Page for Java**, você pode injetar facilmente valores nomeados personalizados no pacote XMP. Este tutorial orienta você passo a passo — com trechos de código completos — para que possa começar a adicionar metadados XMP aos seus documentos EPS hoje mesmo.

## Respostas rápidas
- **Qual biblioteca é necessária?** Aspose.Page for Java (Aspose)  
- **Qual tipo de arquivo é alvo?** Arquivos EPS contendo metadados XMP  
- **Caso de uso principal?** Adicionar valores nomeados personalizados (por exemplo, limites de tamanho de página) ao XMP  
- **Pré‑requisitos?** JDK 8+ e a biblioteca Aspose.Page for Java  
- **Tempo típico de implementação?** 5–10 minutos após a configuração da biblioteca  

## O que é Aspose?
Aspose é a abreviação de Aspose, uma suíte de APIs que permite aos desenvolvedores criar, editar, converter e renderizar uma ampla variedade de formatos de documentos sem a necessidade de software externo. O componente Aspose.Page for Java foca especificamente no processamento de PostScript e EPS, proporcionando acesso programático ao conteúdo da página, gráficos e metadados como XMP.

## Por que adicionar valores nomeados aos metadados XMP?
Valores nomeados permitem armazenar pares chave‑valor arbitrários diretamente dentro do pacote XMP, tornando-os instantaneamente legíveis por ferramentas subsequentes. Isso melhora a compatibilidade com mecanismos de busca, possibilita automação de fluxos de trabalho e satisfaz requisitos de conformidade ao incorporar informações regulatórias sem alterar o conteúdo visual.

## Por que isso importa
Adicionar valores nomeados ao XMP permite armazenar pares chave‑valor arbitrários que podem ser lidos sem analisar todo o arquivo EPS. Essa capacidade é especialmente valiosa em pipelines de publicação automatizadas, sistemas de gerenciamento de ativos digitais e fluxos de trabalho orientados por conformidade, onde os metadados dirigem ações subsequentes.

## Pré‑requisitos
Antes de prosseguir, certifique‑se de que você possui:

- **Java Development Kit (JDK):** Uma JDK recente (8 ou superior) instalada na sua máquina.  
- **Aspose.Page for Java Library:** Baixe-a da página oficial de [download do Aspose.Page for Java](https://releases.aspose.com/page/java/). Adicione o JAR ao classpath do seu projeto.  
- **Um arquivo EPS** que já contenha metadados XMP ou que será gerado automaticamente.

## Importar pacotes
Comece importando os pacotes Java necessários. Essas importações dão acesso a fluxos de arquivos, ao modelo de documento EPS e às classes de manipulação de XMP.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Como adicionar valor nomeado XMP em arquivos EPS usando Java
Para adicionar um valor nomeado, carregue o arquivo EPS com um `FileInputStream`, recupere ou crie seu objeto `XmpMetadata`, insira o `NamedValue` desejado no namespace apropriado e, em seguida, grave o documento modificado usando um `FileOutputStream`. O Aspose.Page cria automaticamente o pacote XMP caso esteja ausente, garantindo que os novos metadados sejam incorporados corretamente.

### Etapa 1: Inicializar fluxo de arquivo EPS de entrada
**FileInputStream** é uma classe de I/O Java que lê bytes brutos de um arquivo. Carregue o arquivo EPS de origem em um `FileInputStream`. Esse fluxo alimenta o documento na API do Aspose.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Dica profissional:** Mantenha a variável `dataDir` configurável para que o mesmo código funcione em diferentes ambientes.

### Etapa 2: Obter metadados XMP
**XmpMetadata** representa o pacote XMP associado a um documento EPS. Recupere o pacote XMP existente; se o arquivo EPS não possuir um, o Aspose cria um novo objeto XMP preenchido a partir dos comentários PS.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Etapa 3: Adicionar valor nomeado
**NamedValue** é um par chave‑valor armazenado dentro do namespace de metadados XMP. Insira um valor nomeado personalizado na estrutura XMP. Neste exemplo, adicionamos uma nova chave sob o namespace `xmpTPg:MaxPageSize`.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Por que isso importa:** Valores nomeados permitem armazenar pares chave‑valor arbitrários que aplicações downstream podem ler sem analisar todo o documento.

### Etapa 4: Inicializar fluxo de arquivo EPS de saída
**FileOutputStream** é uma classe de I/O Java que grava bytes brutos em um arquivo. Prepare um `FileOutputStream` onde o EPS modificado será salvo.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Etapa 5: Salvar documento
O método `save` persiste as alterações. Ele grava o pacote XMP atualizado de volta no arquivo EPS, garantindo que o novo valor nomeado faça parte dos metadados do documento.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Etapa 6: Fechar fluxo de arquivo EPS de entrada
Fechar o manipulador de arquivo original evita vazamentos de recursos e assegura que o arquivo não fique bloqueado para operações subsequentes.

```java
psStream.close();
```

Seguindo estas seis etapas, você adicionou com sucesso **um valor nomeado nos metadados XMP** usando **Aspose.Page for Java**.

## Problemas comuns e soluções
| Problema | Causa | Correção |
|----------|-------|----------|
| `NullPointerException` on `xmp` | O arquivo EPS não tem XMP e o Aspose falhou ao gerar um | Certifique‑se de que o EPS contenha ao menos um comentário PS ou crie manualmente uma nova instância `XmpMetadata`. |
| Output file is empty | O fluxo de saída não foi descarregado/fechado | Verifique se `outPsStream.close()` é chamado em um bloco `finally` (conforme mostrado). |
| Duplicate key error | O mesmo valor nomeado foi adicionado duas vezes | Verifique se a chave já existe com `xmp.containsNamedValue(...)` antes de adicioná‑la. |

## Perguntas frequentes

**Q: Posso usar Aspose.Page for Java com outras bibliotecas Java?**  
A: Sim, o Aspose.Page for Java foi projetado para funcionar perfeitamente com outras bibliotecas Java, oferecendo flexibilidade no seu ambiente de desenvolvimento.

**Q: Existe uma versão de avaliação gratuita do Aspose.Page for Java?**  
A: Sim, você pode acessar uma avaliação gratuita do Aspose.Page for Java na [página de releases da Aspose](https://releases.aspose.com/).

**Q: Como posso obter uma licença temporária para Aspose.Page for Java?**  
A: Visite a [página de licença temporária](https://purchase.aspose.com/temporary-license/) para obter uma licença temporária para Aspose.Page for Java.

**Q: Onde encontro mais tutoriais e exemplos para Aspose.Page for Java?**  
A: Explore a [documentação](https://reference.aspose.com/page/java/) para tutoriais e exemplos abrangentes.

**Q: O Aspose.Page for Java é adequado para projetos de grande escala?**  
A: Absolutamente, o Aspose.Page for Java foi projetado para lidar eficientemente com projetos de grande escala, fornecendo recursos robustos de manipulação de documentos.

## Conclusão
Neste guia demonstramos como **Aspose.Page for Java** simplifica a **adição de valores nomeados aos metadados XMP** em arquivos EPS. Com as etapas acima, você pode enriquecer seus documentos com metadados personalizados, melhorar a capacidade de busca e habilitar um processamento downstream mais inteligente.

---

**Última atualização:** 2026-09-19  
**Testado com:** Aspose.Page for Java 24.12 (mais recente na época da escrita)  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como adicionar namespace XMP em arquivos EPS usando Aspose.Page – Tutorial Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Adicionar metadados XMP a arquivos EPS usando Java](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [Ler XMP usando Aspose.Page – Guia Java](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}