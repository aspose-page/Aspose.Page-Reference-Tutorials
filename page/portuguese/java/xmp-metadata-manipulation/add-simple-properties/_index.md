---
date: 2025-12-20
description: Aprenda como criar metadados XMP em arquivos EPS usando Aspose.Page para
  Java. Guia passo a passo para adicionar propriedades XMP simples programaticamente.
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: Como criar EPS com metadados XMP usando Java
url: /pt/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Propriedades Simples em XMP usando Java

## Introdução
Em fluxos de trabalho modernos de documentos, ser capaz de **create XMP metadata EPS** arquivos programaticamente lhe dá controle total sobre como seus gráficos são descritos, pesquisados e arquivados. Com Aspose.Page for Java você pode ler, modificar e gravar pacotes XMP dentro de documentos EPS sem sair do ecossistema Java. Neste tutorial, vamos guiá‑lo passo a passo para adicionar propriedades simples de XMP a um arquivo EPS, para que você possa enriquecer seus gráficos com metadados personalizados de forma rápida e confiável.

## Respostas Rápidas
- **O que significa “create xmp metadata eps”?** Adicionar um pacote XMP (metadados baseados em XML) a um arquivo EPS.  
- **Qual biblioteca é necessária?** Aspose.Page for Java (disponível para download no site da Aspose).  
- **Preciso de licença para testes?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Quantas linhas de código?** Menos de 30 linhas de Java mais algumas instruções de importação.  
- **Posso adicionar outros tipos de dados?** Sim – datas, inteiros, doubles, strings e até arrays são suportados.

## O que é create xmp metadata eps?
XMP (Extensible Metadata Platform) é um padrão para incorporar metadados ricos dentro de arquivos. Quando você **create XMP metadata EPS**, você incorpora um pacote XML dentro de um documento EPS (Encapsulated PostScript), permitindo que aplicações subsequentes leiam autor, data de criação, tags personalizadas e muito mais.

## Por que adicionar metadados XMP a arquivos EPS?
- **Facilidade de busca:** Permite indexação automática por sistemas DAM.  
- **Conformidade:** Armazena informações legais ou de licenciamento diretamente no arquivo.  
- **Automação:** Permite que pipelines subsequentes tomem decisões com base nos dados incorporados.  
- **Portabilidade:** Os metadados viajam com o EPS, garantindo consistência entre plataformas.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

- Conhecimento básico de programação Java.  
- Biblioteca Aspose.Page for Java instalada. Você pode baixá‑la **[aqui](https://releases.aspose.com/page/java/)**.  
- Um arquivo EPS de exemplo contendo metadados. Se você não tiver um, sinta‑se à vontade para usar o arquivo **`xmp3.eps`** fornecido.

## Importar Pacotes
Primeiro, importe as classes que você precisará. As importações permanecem exatamente as mesmas do exemplo original:

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

## Etapa 1: Carregar o documento EPS e obter metadados XMP
Abrimos o arquivo EPS, criamos uma instância `PsDocument` e recuperamos (ou criamos) o pacote XMP.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Etapa 2: Adicionar uma propriedade de Data
Adicionar uma data é tão simples quanto criar um objeto `Date` e inseri‑lo no mapa XMP.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Etapa 3: Adicionar uma propriedade Inteira
Você pode armazenar identificadores numéricos ou números de versão usando um valor inteiro.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Etapa 4: Adicionar uma propriedade Double
Números de ponto flutuante são úteis para medições ou avaliações.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Etapa 5: Adicionar uma propriedade String
Tags textuais personalizadas (por exemplo, códigos de projeto) são armazenadas como strings.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Etapa 6: Salvar o arquivo EPS atualizado
Depois que todas as propriedades forem adicionadas, grave o documento de volta ao disco.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Etapa 7: Limpar recursos
Sempre feche o fluxo de entrada para evitar vazamentos de manipuladores de arquivo.

```java
// Close input EPS stream
psStream.close();
```

## Problemas Comuns e Soluções
| Problema | Motivo | Correção |
|----------|--------|----------|
| **Null XMP metadata** | O arquivo EPS não continha pacote XMP e a biblioteca não pôde inferir comentários PS. | Certifique‑se de que o EPS de origem contenha ao menos um comentário PS (por exemplo, `%%Creator`). A biblioteca gerará automaticamente um pacote XMP mínimo. |
| **Time zone mismatch** | As datas aparecem deslocadas ao serem abertas em outra aplicação. | Defina `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` antes de criar o objeto `Date`, como mostrado na Etapa 2. |
| **License exception** | Em tempo de execução lança `LicenseException`. | Aplique uma licença válida do Aspose.Page antes de usar a API, ou execute em modo de avaliação. |

## Conclusão
Seguindo estas etapas, você agora sabe como **create XMP metadata EPS** arquivos usando Aspose.Page for Java. Adicionar propriedades simples como datas, inteiros, doubles e strings é simples, e os arquivos EPS resultantes carregam metadados ricos e pesquisáveis que beneficiam qualquer fluxo de trabalho subsequente.

## Perguntas Frequentes
### Posso usar Aspose.Page for Java com outras linguagens de programação?
Aspose.Page suporta principalmente Java, mas há versões disponíveis para outras linguagens como .NET.

### Existe uma avaliação gratuita disponível para Aspose.Page for Java?
Sim, você pode explorar os recursos do Aspose.Page obtendo uma avaliação gratuita **[aqui](https://releases.aspose.com/)**.

### Onde posso encontrar documentação detalhada do Aspose.Page for Java?
A documentação está disponível **[aqui](https://reference.aspose.com/page/java/)**.

### Como posso obter uma licença temporária para Aspose.Page for Java?
Uma licença temporária pode ser adquirida **[aqui](https://purchase.aspose.com/temporary-license/)**.

### Onde posso comprar Aspose.Page for Java?
Você pode comprar o produto **[aqui](https://purchase.aspose.com/buy)**.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}