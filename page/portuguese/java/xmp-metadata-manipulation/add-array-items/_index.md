---
date: 2026-03-05
description: Aprenda como adicionar itens de array dc:title nos metadados XMP de arquivos
  EPS usando Aspose.Page para Java. Siga este guia passo a passo para obter resultados
  rápidos.
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Como adicionar itens de array dc:title nos metadados XMP usando Java
url: /pt/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar itens de array em metadados XMP usando Java

## Introdução
Neste tutorial você descobrirá **como adicionar dc:title** (e outros itens de array) aos metadados XMP dentro de um arquivo EPS com Aspose.Page para Java. Atualizar os metadados XMP é útil quando você precisa incorporar informações pesquisáveis — como títulos, criadores ou palavras‑chave — diretamente em seus arquivos gráficos. Vamos percorrer cada passo, explicar por que cada linha é importante e mostrar como verificar as alterações.

## Respostas rápidas
- **O que representa “dc:title”?** É a propriedade de título do Dublin Core armazenada como um array XMP.  
- **Por que modificar os metadados XMP?** Isso permite melhor gerenciamento de ativos, capacidade de pesquisa e conformidade com padrões.  
- **Preciso de um bloco XMP existente?** Não — Aspose.Page gerará um a partir dos comentários PS se estiver ausente.  
- **Qual versão da biblioteca é necessária?** Qualquer versão recente do Aspose.Page para Java (testada com a última build de 2026).  
- **Posso adicionar outras propriedades de array?** Sim — use o mesmo método `addArrayItem` para propriedades como `dc:creator`.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

- Biblioteca Aspose.Page para Java instalada (adicione o JAR ao classpath do seu projeto).  
- Experiência básica em desenvolvimento Java (JDK 8+ recomendado).  
- Um arquivo EPS que já contenha metadados XMP ou, ao menos, comentários de metadados PS (por exemplo, `%%Title`, `%%Creator`).  

## Importar pacotes
Para iniciar, importe as classes necessárias para ler, manipular e salvar arquivos EPS:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Etapa 1: Carregar o documento EPS e recuperar os metadados XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Aqui abrimos o arquivo EPS e solicitamos ao Aspose.Page seu bloco XMP. Se o arquivo não possuir XMP, a biblioteca cria automaticamente um usando os comentários PS existentes, garantindo que você sempre tenha um contêiner de metadados para trabalhar.

## Etapa 2: Adicionar um novo item de array **dc:title**  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

Esta linha demonstra **como adicionar dc:title**. Substitua `"NewTitle"` pelo título real que deseja incorporar. O método acrescenta o valor ao array de títulos existente, preservando quaisquer títulos anteriores.

## Etapa 3: Adicionar um novo item de array **dc:creator**  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

Da mesma forma, você pode enriquecer a propriedade `dc:creator`. Vários criadores podem ser armazenados; cada chamada adiciona outra entrada.

## Etapa 4: Preparar o fluxo de saída  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

Criamos um stream para o arquivo EPS modificado. Usar um nome de arquivo diferente (`xmp3_changed.eps`) mantém o arquivo original intacto.

## Etapa 5: Salvar o documento com os metadados XMP atualizados  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

A chamada `save` grava os dados EPS juntamente com o bloco XMP atualizado. O bloco `finally` garante que o manipulador de arquivo seja liberado mesmo que ocorra uma exceção.

## Por que isso importa
Incorporar valores precisos de `dc:title` e `dc:creator` melhora:

- **Capacidade de pesquisa** em sistemas de gerenciamento de ativos digitais (DAM).  
- **Conformidade** com padrões de publicação que exigem metadados.  
- **Colaboração**, pois os colegas podem identificar rapidamente o conteúdo do arquivo sem abrir o EPS.

## Armadilhas comuns e dicas
- **Armadilha:** Sobrescrever itens de array existentes inadvertidamente.  
  **Dica:** Use `xmp.getArrayItems("dc:title")` para inspecionar os valores atuais antes de adicionar novos.  
- **Armadilha:** Esquecer de fechar streams, causando bloqueios de arquivo.  
  **Dica:** Sempre envolva I/O em try‑with‑resources ou em um bloco `finally`, como mostrado.  
- **Dica:** Você pode encadear várias chamadas `addArrayItem` para adicionar vários títulos ou criadores em uma única passagem.

## Perguntas frequentes

### Posso usar Aspose.Page para Java com outros formatos de documento?
Sim, Aspose.Page suporta vários formatos de documento, incluindo EPS, PDF e XPS.

### Existe um teste gratuito disponível para Aspose.Page para Java?
Sim, você pode acessar o teste gratuito [aqui](https://releases.aspose.com/).

### Onde posso encontrar a documentação do Aspose.Page para Java?
A documentação está disponível [aqui](https://reference.aspose.com/page/java/).

### Como posso comprar Aspose.Page para Java?
Você pode adquirir o produto [aqui](https://purchase.aspose.com/buy).

### Licenças temporárias estão disponíveis para Aspose.Page para Java?
Sim, você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

---

**Última atualização:** 2026-03-05  
**Testado com:** Aspose.Page para Java (última release de 2026)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}