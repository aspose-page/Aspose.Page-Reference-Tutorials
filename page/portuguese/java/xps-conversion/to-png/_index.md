---
date: 2025-12-23
description: Converta **XPS para PNG** sem esforço em Java usando Aspose.Page. Este
  guia mostra como renderizar XPS em arquivos de imagem com uma solução confiável
  e amigável ao desenvolvedor.
linktitle: Convert XPS to PNG in Java
second_title: Aspose.Page Java API
title: Converter XPS para PNG em Java
url: /pt/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converter XPS para PNG em Java

## Introdução
No dinâmico mundo do desenvolvimento de software, a necessidade de **converter XPS para PNG** (XML Paper Specification para Portable Network Graphics) surge com frequência. Para realizar essa tarefa de forma fluida em Java, o Aspose.Page oferece uma solução poderosa. Neste tutorial, percorreremos o processo de conversão de XPS para PNG usando o Aspose.Page para Java.

## Respostas Rápidas
- **Qual biblioteca realiza a conversão?** Aspose.Page for Java  
- **Quais formatos estão envolvidos?** XPS (origem) → PNG (saída)  
- **Preciso de licença para produção?** Sim, é necessária uma licença comercial  
- **Posso definir a resolução da imagem?** Sim, usando `PngSaveOptions.setResolution()`  
- **É possível selecionar páginas específicas?** Absolutamente – forneça os números das páginas no objeto de opções  

## Por que Converter XPS para PNG?
Renderizar XPS para arquivos de imagem é útil quando você precisa exibir documentos na web, incorporá‑los em relatórios ou gerar miniaturas para visualização. PNG oferece compressão sem perdas e amplo suporte em navegadores, tornando‑o uma escolha ideal para representações visuais de alta qualidade do conteúdo XPS.

## Pré‑requisitos
Antes de mergulharmos no tutorial, certifique‑se de que você tem os seguintes pré‑requisitos configurados:
1. Java Development Kit (JDK): Certifique‑se de que o JDK está instalado em seu sistema.  
2. Aspose.Page for Java: Baixe e instale a biblioteca Aspose.Page. Você pode encontrar o link de download [aqui](https://releases.aspose.com/page/java/).  
3. Ambiente de Desenvolvimento Integrado (IDE): Escolha uma IDE compatível com Java, como IntelliJ IDEA ou Eclipse.  

## Como converter XPS para PNG em Java
A seguir, um guia passo a passo que explica **como converter documentos XPS** em imagens PNG, incluindo trechos de código que você pode copiar diretamente para o seu projeto.

### Importar Pacotes
No seu projeto Java, importe os pacotes necessários para utilizar as funcionalidades do Aspose.Page. Adicione as seguintes instruções de importação no início do seu arquivo Java:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

### Etapa 1: Definir Diretório do Documento
Defina a pasta que contém seu arquivo XPS de origem e onde os arquivos PNG serão salvos.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Etapa 2: Carregar Documento XPS
Crie uma instância de `XpsDocument` que carregue o arquivo XPS de origem.

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Etapa 3: Inicializar Opções
Configure as opções de saída PNG. Aqui você pode definir suavização, resolução e especificar quais páginas renderizar.

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Etapa 4: Criar Dispositivo de Renderização
Crie um `ImageDevice` que armazenará os dados da imagem renderizada.

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

### Etapa 5: Salvar e Iterar
Renderize o documento XPS e, em seguida, grave cada array de bytes PNG gerado em um arquivo no disco.

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

Seguindo estas etapas, você pode facilmente **renderizar XPS para imagens** no formato PNG usando o Aspose.Page para Java.

## Conclusão
Em conclusão, o Aspose.Page para Java simplifica o processo de conversão de XPS para PNG, oferecendo aos desenvolvedores uma ferramenta confiável e eficiente. Incorpore esta biblioteca em seus projetos Java para otimizar tarefas de manipulação de documentos.

## Perguntas Frequentes
### Posso usar Aspose.Page para Java em projetos comerciais?
Sim, o Aspose.Page é um produto comercial. Você pode encontrar informações de licenciamento [aqui](https://purchase.aspose.com/buy).

### Existe uma versão de avaliação gratuita disponível?
Sim, você pode experimentar uma avaliação gratuita [aqui](https://releases.aspose.com/).

### Onde posso encontrar a documentação do Aspose.Page para Java?
A documentação completa está disponível [aqui](https://reference.aspose.com/page/java/).

### Como obtenho uma licença temporária para fins de teste?
Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Existem fóruns da comunidade para discussões sobre Aspose.Page?
Sim, visite os fóruns da comunidade [aqui](https://forum.aspose.com/c/page/39).

## Perguntas Frequentes Adicionais

**Q: Posso converter apenas páginas selecionadas de um arquivo XPS?**  
A: Absolutamente. Use o método `setPageNumbers` em `PngSaveOptions` para especificar as páginas que deseja renderizar.

**Q: Qual resolução de imagem é recomendada para PNGs de alta qualidade?**  
A: Uma resolução de 300 dpi é um bom equilíbrio entre qualidade e tamanho do arquivo, mas você pode ajustá‑la via `options.setResolution()`.

**Q: A API suporta conversão multithread para documentos grandes?**  
A: Sim, você pode invocar a lógica de conversão em threads paralelas, cada uma manipulando uma página ou partição diferente do documento.

**Q: Como lidar com o uso de memória ao converter arquivos XPS muito grandes?**  
A: Processe as páginas sequencialmente e libere o `FileOutputStream` após cada gravação, como mostrado no código de exemplo.

**Q: Existe uma maneira de adicionar metadados personalizados aos arquivos PNG gerados?**  
A: Embora `PngSaveOptions` não exponha diretamente campos de metadados, você pode pós‑processar o PNG usando bibliotecas de imagem padrão para incorporar metadados.

---

**Última atualização:** 2025-12-23  
**Testado com:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}