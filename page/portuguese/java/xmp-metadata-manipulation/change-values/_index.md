---
date: 2025-12-21
description: Aprenda como o Aspose.Page modifica XMP em documentos EPS usando Java.
  Aprimore metadados rapidamente com o Aspose.Page para Java.
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page modificar xmp – Alterar valores no XMP usando Java
url: /pt/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Alterar Valores em XMP usando Java

## Introdução
Se você precisa **aspose.page modify xmp** dados dentro de um arquivo EPS, chegou ao lugar certo. Neste tutorial vamos percorrer passo a passo as etapas necessárias para ler, atualizar e salvar valores XMP (Extensible Metadata Platform) usando a biblioteca Aspose.Page para Java. Ao final, você será capaz de personalizar os metadados do documento — como criador, título e data de modificação — para atender aos requisitos do seu projeto.

## Respostas Rápidas
- **O que o “aspose.page modify xmp” faz?** Ele permite ler e gravar metadados XMP em arquivos EPS via a API Aspose.Page para Java.  
- **Qual versão da biblioteca é necessária?** Qualquer versão recente do Aspose.Page para Java (a API é estável entre versões).  
- **Preciso de licença para executar o exemplo?** Uma avaliação gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Posso alterar vários campos XMP de uma vez?** Sim — chame `put` para cada campo antes de salvar o documento.  
- **É necessário tratar fuso horário?** Definir o fuso horário padrão (ex.: UTC) garante valores de data consistentes.

## O que é XMP e Por que Modificá-lo?
XMP (Extensible Metadata Platform) é um método padronizado para incorporar metadados ricos diretamente dentro de arquivos como EPS, PDF e imagens. Atualizar XMP permite controlar como os documentos são indexados, exibidos e pesquisados — essencial para branding, conformidade e automação de fluxos de trabalho.

## Por que Usar Aspose.Page para Java?
- **API completa** – Não há necessidade de ferramentas externas; tudo é tratado no processo.  
- **Multiplataforma** – Funciona em qualquer SO que suporte Java.  
- **Sem dependências nativas** – Implementação pura em Java simplifica a implantação.  
- **Suporte robusto** – Lida tanto com blocos XMP existentes quanto cria novos a partir de comentários PS quando ausentes.

## Pré-requisitos
Antes de iniciar este tutorial, certifique‑se de que você tem os seguintes pré‑requisitos:
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

## Etapa 1:ter Metadados XMP
Recupere os metadados XMP do documento EPS. Se o arquivo EPS não contiver metadados XMP, um novo será criado com valores dos comentários de metadados PS, como %%Creator, %%CreateDate e %%Title.

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
Modifique o valor "ModifyDate" nos metadados XMP para refletir a data desejada.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Etapa 3: Alterar o Valor "Creator"
Atualize o valor "Creator" nos metadados XMP para especificar o criador do documento.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Etapa 4: Alterar o Valor "Title"
Modifique o valor "Title" nos metadados XMP para definir um título apropriado para o documento.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Etapa 5: Salvar o Documento com Metadados XMP Alterados
Salve o documento com os metadados XMP atualizados em um novo arquivo EPS.

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
- **Bloco XMP ausente** – A API cria automaticamente um a partir dos comentários PS, mas você também pode instanciar manualmente `XmpMetadata` se necessário.  
- **Incompatibilidade de fusos horários** – Sempre defina `TimeZone.setDefault` antes de criar o objeto `Date` para evitar deslocamentos inesperados.  
- **Erros de acesso a arquivos** – Verifique se os caminhos de entrada e saída estão corretos e se sua aplicação tem permissões de leitura/escrita.

## Perguntas Frequentes

**Q: Como posso lidar com considerações de fuso horário ao modificar valores XMP?**  
A: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` para garantir consistência nas configurações de fuso horário.

**Q: Posso alterar vários valores XMP em uma única operação?**  
A: Sim, usando o método `put` para cada valor desejado, você pode modificar múltiplos valores XMP simultaneamente.

**Q: Onde posso encontrar documentação adicional para Aspose.Page para Java?**  
A: Explore a documentação abrangente [aqui](https://reference.aspose.com/page/java/).

**Q: Existe uma avaliação gratuita disponível para Aspose.Page para Java?**  
A: Sim, você pode acessar a avaliação gratuita [aqui](https://releases.aspose.com/).

**Q: Como posso obter uma licença temporária para Aspose.Page para Java?**  
A: Obtenha uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

**Q: A modificação do XMP afeta o conteúdo visual do EPS?**  
A: Não. As alterações de XMP são apenas de metadados e não alteram os elementos gráficos do arquivo EPS.

**Q: Posso ler programaticamente os valores atualizados para verificar a alteração?**  
A: Absolutamente — basta chamar `xmp.get("dc:creator")` (ou a chave relevante) após salvar e antes de fechar o documento.

## Conclusão
Parabéns! Você navegou com sucesso pelo processo de **aspose.page modify xmp** em documentos EPS usando Aspose.Page para Java. Este tutorial equipou você com o conhecimento para modificar metadados, garantindo que seus documentos estejam alinhados aos requisitos específicos de forma fluida.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose