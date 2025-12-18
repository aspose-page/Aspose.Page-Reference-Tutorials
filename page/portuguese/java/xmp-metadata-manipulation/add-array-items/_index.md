---
date: 2025-12-18
description: Aprenda como adicionar metadados inserindo itens de array nos metadados
  XMP de arquivos EPS usando Aspose.Page para Java. Siga nosso guia passo a passo.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Como adicionar metadados – adicionar itens de array no XMP (Java)
url: /pt/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Itens de Array em Metadados XMP usando Java

## Como Adicionar Metadados
Bem-vindo ao nosso guia passo a passo sobre **como adicionar metadados** a arquivos EPS com Aspose.Page for Java. Neste tutorial, vamos guiá‑lo na adição de itens de array aos metadados XMP — uma necessidade comum quando você precisa enriquecer informações do documento, como títulos ou criadores. Ao final, você entenderá por que o XMP é valioso, como manipulá‑lo programaticamente e como salvar o arquivo EPS atualizado.

## Respostas Rápidas
- **Qual biblioteca é usada?** Aspose.Page for Java  
- **Qual formato de arquivo é alvo?** EPS (Encapsulated PostScript)  
- **Posso adicionar vários títulos?** Sim, use `xmp.addArrayItem("dc:title", ...)` repetidamente  
- **Preciso de uma licença para produção?** Sim, é necessária uma licença válida do Aspose.Page  
- **O código é compatível com Java 8+?** Absolutamente, funciona com todas as versões modernas do Java  

## Pré‑requisitos
Antes de mergulharmos no tutorial, certifique‑se de que você tem os seguintes pré‑requisitos:
- Biblioteca Aspose.Page for Java instalada.
- Compreensão básica de programação Java.
- Um arquivo EPS válido com metadados XMP existentes ou comentários de metadados PS.

## Importar Pacotes
Para começar, você precisa importar os pacotes necessários para trabalhar com Aspose.Page. Inclua as linhas a seguir no início do seu arquivo Java:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Etapa 1: Obter Metadados XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
Nesta etapa, recuperamos os metadados XMP existentes do arquivo EPS. Se o arquivo EPS ainda não contiver metadados XMP, o Aspose.Page gera um novo e o preenche com valores dos comentários de metadados PS.

## Etapa 2: Adicionar Item de Array "dc:title"
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Agora, adicionamos um novo item de array à propriedade **dc:title** nos metadados XMP. Substitua `"NewTitle"` pelo título desejado.

## Etapa 3: Adicionar Item de Array "dc:creator"
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Da mesma forma, adicionamos um novo item de array à propriedade **dc:creator** nos metadados XMP. Substitua `"NewCreator"` pelas informações do criador desejadas.

## Etapa 4: Inicializar Fluxo de Arquivo EPS de Saída
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Prepare o fluxo de arquivo EPS de saída onde o documento modificado com os metadados XMP atualizados será salvo.

## Etapa 5: Salvar Documento com Metadados XMP Alterados
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Salve o documento com os metadados XMP atualizados no arquivo EPS de saída.

## Conclusão
Parabéns! Você aprendeu com sucesso **como adicionar metadados** inserindo itens de array nos metadados XMP usando Aspose.Page for Java. Esta poderosa biblioteca simplifica o processo de manipulação de arquivos EPS e oferece funcionalidade extensiva para o processamento de documentos.

## Perguntas Frequentes

### Posso usar Aspose.Page for Java com outros formatos de documento?
Sim, o Aspose.Page suporta vários formatos de documento, incluindo EPS, PDF e XPS.

### Existe uma versão de avaliação gratuita disponível para Aspose.Page for Java?
Sim, você pode acessar a versão de avaliação gratuita [aqui](https://releases.aspose.com/).

### Onde posso encontrar a documentação do Aspose.Page for Java?
A documentação está disponível [aqui](https://reference.aspose.com/page/java/).

### Como posso comprar o Aspose.Page for Java?
Você pode comprar o produto [aqui](https://purchase.aspose.com/buy).

### Licenças temporárias estão disponíveis para Aspose.Page for Java?
Sim, você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

## Perguntas Frequentes Adicionais

**Q: Posso adicionar mais de um item de array à mesma propriedade?**  
A: Absolutamente. Chame `xmp.addArrayItem` várias vezes para a mesma propriedade para construir uma lista de valores.

**Q: Essa abordagem funciona com esquemas XMP existentes diferentes do Dublin Core?**  
A: Sim, você pode adicionar itens de array a qualquer propriedade XMP, desde que o namespace seja referenciado corretamente.

**Q: Como posso verificar se os metadados foram adicionados corretamente?**  
A: Abra o arquivo EPS resultante em um visualizador que suporte XMP (por exemplo, Adobe Bridge) ou extraia os metadados programaticamente usando os métodos `XmpMetadata`.

---

**Última atualização:** 2025-12-18  
**Testado com:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}