---
date: 2026-02-05
description: Aprenda a salvar EPS como PNG usando Aspose.Page para Java enquanto configura
  uma licença por medição. Guia passo a passo com exemplo de código completo.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Salvar EPS como PNG com Aspose.Page Java (Licença por Medição)
url: /pt/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salvar EPS como PNG com Aspose.Page Java (Licença Métrica)

## Introdução
Se você precisa **salvar EPS como PNG** em uma aplicação Java e deseja uma forma simples de gerenciar a licença, está no lugar certo. Este tutorial orienta você a configurar uma licença métrica para Aspose.Page, carregar um arquivo PostScript (EPS) e convertê‑lo em uma imagem PNG — tudo com passos claros e diretos que você pode seguir imediatamente. Ao final, você também entenderá como **renderizar EPS para PNG** de forma eficiente e **escrever PNG file Java** com código pronto para ambientes de produção.

## Respostas Rápidas
- **O que significa “salvar EPS como PNG”?** Converte um arquivo EPS vetorial em uma imagem raster PNG.  
- **Por que usar uma licença métrica?** Permite pagar apenas pelas páginas que você processa, ideal para cargas de trabalho variáveis.  
- **Preciso de conexão com a internet?** Não, as chaves métricas são validadas localmente.  
- **Qual versão do Java é necessária?** Java 8 ou superior.  
- **Quanto tempo leva a configuração?** Cerca de 10 minutos para uma implementação básica.  

## O que é “salvar EPS como PNG”?
Salvar EPS como PNG transforma um documento Encapsulated PostScript escalável em um formato bitmap amplamente suportado. PNG mantém a transparência e oferece compressão sem perdas, tornando‑o ideal para gráficos web, miniaturas e pré‑visualizações de impressão.

## Por que renderizar EPS para PNG com Aspose.Page?
- **Pure Java API** – sem dependências nativas, podendo ser executada em qualquer ambiente com JVM.  
- **Renderização de alta fidelidade** – gráficos vetoriais são rasterizados com precisão, preservando a qualidade das linhas.  
- **Licença métrica** – você paga apenas pelo que converte, mantendo os custos previsíveis.  
- **Múltiplas opções de saída** – além de PNG, também é possível gerar JPEG, TIFF e outros, oferecendo flexibilidade para diferentes projetos.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

- Conhecimento básico de programação Java.  
- Biblioteca Aspose.Page instalada – faça o download [aqui](https://releases.aspose.com/page/java/).  
- Chaves públicas e privadas métricas, que podem ser obtidas através da sua conta Aspose.

## Importar Pacotes
Primeiro, importe as classes que usaremos. Mantenha o bloco de importação exatamente como mostrado para que o código compile sem alterações.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Como salvar EPS como PNG usando Aspose.Page Java
A seguir está o guia passo a passo que combina licenciamento, carregamento, renderização e gravação do arquivo PNG final.

### Etapa 1: Inicializar Documento e Formato de Imagem
Aqui definimos as chaves métricas e especificamos o formato de saída (PNG). Esta é a base para a operação de **save EPS as PNG**.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

### Etapa 2: Inicializar Fluxo de Entrada PostScript
Abra o arquivo EPS que deseja converter. O fluxo alimenta o documento no Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Etapa 3: Verificar Licença do Documento
Sempre verifique se a licença métrica foi aplicada corretamente antes do processamento.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Etapa 4: Inicializar Opções e Dispositivo de Imagem
Crie o objeto de opções que controla as configurações de conversão e o dispositivo que receberá a imagem renderizada.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Etapa 5: Salvar Arquivo EPS como Imagem
Esta é a chamada central de **save EPS as PNG**. O documento é renderizado no dispositivo de imagem usando as opções configuradas.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Etapa 6: Obter e Salvar Bytes da Imagem
Extraia os bytes PNG do dispositivo e grave‑os em um arquivo no disco. Esta etapa demonstra como **write PNG file Java** de forma segura.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Problemas Comuns e Soluções
| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| **Licença não reconhecida** | As chaves estão incorretas ou na ordem errada. | Verifique as strings das chaves pública/privada e assegure que `setMeteredKey` seja chamado antes de qualquer processamento do documento. |
| **Arquivo de saída vazio** | `device.getImagesBytes()` retornou `null`. | Confirme que o arquivo EPS é válido e que `ImageSaveOptions` não está configurado com um canvas de tamanho zero. |
| **OutOfMemoryError em EPS grande** | Renderizar arquivos vetoriais grandes consome muita memória. | Processar as páginas uma de cada vez ou aumentar o heap da JVM (`-Xmx2g`). |

## Perguntas Frequentes

**P: Como obtenho as chaves públicas e privadas métricas?**  
R: Você pode obtê‑las através da sua conta Aspose.

**P: A biblioteca Aspose.Page é gratuita?**  
R: Aspose.Page oferece versões de avaliação gratuitas e versões pagas. Visite [aqui](https://releases.aspose.com/) para uma avaliação gratuita.

**P: Posso usar Aspose.Page em projetos comerciais?**  
R: Sim, Aspose.Page oferece licenças comerciais. Você pode adquiri‑las [aqui](https://purchase.aspose.com/buy).

**P: Onde encontro documentação adicional?**  
R: Consulte a documentação [aqui](https://reference.aspose.com/page/java/).

**P: Como obtenho licenças temporárias?**  
R: Licenças temporárias podem ser obtidas [aqui](https://purchase.aspose.com/temporary-license/).

**P: E se eu precisar converter arquivos EPS de várias páginas?**  
R: Percorra cada página usando `device.getImagesBytes()` e grave cada array de bytes em um arquivo PNG separado.

**P: Posso alterar a qualidade ou profundidade de cor do PNG?**  
R: Sim, configure `ImageSaveOptions` (por exemplo, `options.setCompressionLevel(...)`) antes de chamar `document.save(...)`.

---

**Última atualização:** 2025-12-03  
**Testado com:** Aspose.Page 24.12 for Java  
**Autor:** Aspose  

**Última atualização:** 2026-02-05  
**Testado com:** Aspose.Page 24.12 for Java (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}