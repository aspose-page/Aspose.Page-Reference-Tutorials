---
title: Converta XPS para JPEG em Java
linktitle: Converta XPS para JPEG em Java
second_title: API Java Aspose.Page
description: Aprenda como converter XPS para JPEG em Java usando Aspose.Page. Um guia completo com instruções passo a passo para uma integração perfeita.
type: docs
weight: 11
url: /pt/java/xps-conversion/to-jpeg/
---
## Introdução
Neste tutorial, exploraremos como converter arquivos XPS (XML Paper Specification) em imagens JPEG usando Aspose.Page para Java. Aspose.Page é uma biblioteca Java poderosa que permite aos desenvolvedores trabalhar perfeitamente com XPS e outros formatos de documentos. Este guia passo a passo ajudará você a entender o processo e implementá-lo em seus aplicativos Java.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Ambiente de desenvolvimento Java: certifique-se de ter um ambiente de desenvolvimento Java configurado em sua máquina.
-  Biblioteca Aspose.Page para Java: Baixe e instale a biblioteca Aspose.Page para Java. Você pode encontrar a biblioteca[aqui](https://releases.aspose.com/page/java/).
- Exemplo de documento XPS: tenha um exemplo de documento XPS que deseja converter para JPEG.
## Importar pacotes
Comece importando os pacotes necessários para sua classe Java:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Etapa 1: inicializar caminhos e documento XPS
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Inicializar fluxo de entrada XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Etapa 2: definir opções JpegSave
```java
// Inicialize o objeto de opções com os parâmetros necessários.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Etapa 3: criar dispositivo de renderização
```java
// Crie um dispositivo de renderização para formato PDF
ImageDevice device = new ImageDevice();
```
## Etapa 4: salve XPS como JPEG
```java
document.save(device, options);
```
## Etapa 5: iterar e salvar páginas JPEG
```java
//Iterar através de partições de documentos (documentos fixos, em termos XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterar pelas páginas de partição
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Inicializar fluxo de saída de imagem
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Escrever imagem
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //feche o fluxo
        imageStream.close();
    }
}
```
Esta série de etapas converterá efetivamente seu documento XPS em imagens JPEG, cada uma salva separadamente.
## Conclusão
Parabéns! Você aprendeu com sucesso como converter XPS para JPEG em Java usando Aspose.Page. Este processo é inestimável para desenvolvedores que trabalham com conversão de documentos em aplicativos Java.
## perguntas frequentes

### P: O Aspose.Page é adequado para projetos comerciais?
 R: Sim, Aspose.Page é um produto comercial com opções de licenciamento disponíveis. Verificar[aqui](https://purchase.aspose.com/buy) para detalhes.
### P: Posso experimentar o Aspose.Page antes de comprar?
 R: Sim, você pode obter uma avaliação gratuita[aqui](https://releases.aspose.com/).
### P: Onde posso encontrar a documentação do Aspose.Page?
 R: A documentação está disponível[aqui](https://reference.aspose.com/page/java/).
### P: Como posso obter suporte para Aspose.Page?
 R: Visite o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para apoio comunitário.
### P: Preciso de uma licença temporária para testes?
 R: Sim, você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).