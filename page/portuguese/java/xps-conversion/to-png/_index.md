---
title: Converter XPS em PNG em Java
linktitle: Converter XPS em PNG em Java
second_title: API Java Aspose.Page
description: Converta facilmente XPS para PNG em Java usando Aspose.Page. Simplifique as tarefas documentais com esta solução confiável e amigável ao desenvolvedor.
weight: 13
url: /pt/java/xps-conversion/to-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converter XPS em PNG em Java

## Introdução
No mundo dinâmico do desenvolvimento de software, surge frequentemente a necessidade de converter documentos XPS (XML Paper Specification) em imagens PNG (Portable Network Graphics). Para realizar essa tarefa perfeitamente em Java, Aspose.Page fornece uma solução poderosa. Neste tutorial, percorreremos o processo de conversão de XPS em PNG usando Aspose.Page para Java.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos configurados:
1. Java Development Kit (JDK): Certifique-se de ter o JDK instalado em seu sistema.
2.  Aspose.Page para Java: Baixe e instale a biblioteca Aspose.Page. Você pode encontrar o link para download[aqui](https://releases.aspose.com/page/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): Escolha um IDE compatível com Java, como IntelliJ IDEA ou Eclipse.
## Importar pacotes
Em seu projeto Java, importe os pacotes necessários para utilizar as funcionalidades do Aspose.Page. Adicione as seguintes instruções de importação no início do seu arquivo Java:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Etapa 1: definir diretório de documentos
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
```
## Etapa 2: carregar o documento XPS
```java
// Carregar documento XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Etapa 3: opções de inicialização
```java
// Inicialize o objeto de opções com os parâmetros necessários.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Etapa 4: criar dispositivo de renderização
```java
// Crie um dispositivo de renderização para formato PDF
ImageDevice device = new ImageDevice();
```
## Etapa 5: salvar e iterar
```java
// Salve o documento XPS em PNG usando opções e dispositivo
document.save(device, options);
//Iterar através de partições de documentos (documentos fixos, em termos XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterar pelas páginas de partição
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Inicializar fluxo de saída de imagem
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Escrever imagem
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Fechar o fluxo
        imageStream.close();
    }
}
```
Seguindo essas etapas, você pode converter facilmente documentos XPS em imagens PNG usando Aspose.Page for Java.
## Conclusão
Concluindo, Aspose.Page for Java simplifica o processo de conversão de XPS para PNG, fornecendo aos desenvolvedores uma ferramenta confiável e eficiente. Incorpore esta biblioteca em seus projetos Java para agilizar tarefas de manipulação de documentos.
## Perguntas frequentes
### Posso usar Aspose.Page for Java em projetos comerciais?
 Sim, Aspose.Page é um produto comercial. Você pode encontrar informações de licenciamento[aqui](https://purchase.aspose.com/buy).
### Existe um teste gratuito disponível?
 Sim, você pode explorar uma avaliação gratuita[aqui](https://releases.aspose.com/).
### Onde posso encontrar a documentação do Aspose.Page for Java?
 A documentação abrangente está disponível[aqui](https://reference.aspose.com/page/java/).
### Como obtenho uma licença temporária para fins de teste?
 Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### Existem fóruns da comunidade para discussões do Aspose.Page?
 Sim, visite os fóruns da comunidade[aqui](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
