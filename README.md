# RAG-Onto

RAG-Onto é uma Ontologia de Referência desenvolvida para mapear a proveniência, rastreabilidade e auditoria em pipelines de Retrieval-Augmented Generation (RAG).

Este projeto foi desenvolvido como trabalho prático para a disciplina de Ontologias e Grafos de Conhecimento do Mestrado em Informática da Universidade Federal do Espírito Santo (UFES).

## Objetivo

Sistemas RAG frequentemente operam como "caixas pretas", dificultando a auditoria de evidências e o rastreamento das configurações utilizadas para gerar uma resposta. A RAG-Onto resolve esse problema atuando como um metamodelo focado em eventos (execuções) e configurações, permitindo responder a Questões de Competência (CQs) sobre:

- A origem e o chunking de documentos fontes (Index-time).

- Os parâmetros de vetorização e os modelos de embedding utilizados.

- As estratégias de recuperação e reranking aplicadas (Query-time).

- A rastreabilidade de citações e auditoria de facticidade (ex: detecção de unsupported claims / alucinações).

## Estrutura do Repositório

O projeto adota uma abordagem de ciclo misto (Metodologia SABiO), indo do modelo conceitual (OntoUML) até a operacionalização (OWL/gUFO).

```text
 RAG-Onto
┣  OntoUML
┃ ┣  RAG.vpp                 # Arquivo do Visual Paradigm contendo a modelagem conceitual
┃ ┗  figs                    # Imagens PNG dos diagramas exportados para o relatório
┣  OWL
┃ ┣  RAG_TBOX.ttl            # T-Box gerada automaticamente via plugin gUFO
┃ ┗  RAG_ABOX.ttl            # A-Box sintético (gerado via script Python para testes em escala)
┣  SPARQL
┃ ┣  CQ1.sparql              # Consultas SPARQL para validação das Questões de Competência
┃ ┣  CQ2.sparql
┃ ┣  ...
┃ ┗  Resultados              # Capturas de tela (PNG) das queries rodando no Protégé
┣  .gitignore                # Arquivos ignorados pelo git
┣  LICENSE                   # Licença Attribution 4.0 International
┗  README.md                 # Este arquivo
```

## Como reproduzir (Guia Rápido)

Para visualizar e testar as consultas SPARQL deste projeto, recomendamos o uso da ferramenta Protégé.

Clone este repositório:

```bash
git clone https://github.com/MrRobson9/rag-ontology
```

1. Abra a Ontologia no Protégé:

2. Abra o Protégé.

- Vá em File > Open... e selecione o arquivo OWL/RAG_TBOX.ttl.

- Opcional/Recomendado: Dependendo de como a sua importação está configurada, você pode mesclar o A-BOX abrindo também o OWL/RAG_ABOX.ttl ou garantindo que o TBOX importe os indivíduos.

3. Execute as Consultas SPARQL:

- No Protégé, vá até a aba Window > Tabs > SPARQL Tab (para habilitar a aba de consultas).

- Abra os arquivos da pasta /SPARQL/ usando um editor de texto.

- Copie o código da consulta desejada (ex: CQ10.sparql).

- Cole na janela SPARQL do Protégé e clique em Execute.

- Você pode comparar os resultados obtidos com os prints disponíveis na pasta /SPARQL/Resultados/.

## Tecnologias e Ferramentas Utilizadas

- Metodologia: SABiO (Systematic Approach for Building Ontologies)

- Modelagem Conceitual: OntoUML (Visual Paradigm)

- Ontologia de Fundamentação: gUFO (Unified Foundational Ontology)

- Operacionalização: OWL (Turtle .ttl)

- Linguagem de Consulta: SPARQL

- Ambiente de Validação: Protégé 5.6+

## Autores

- Dylan Faria Robson & Lucas Ribeiro Arêas - Mestrado em Informática - Universidade Federal do Espírito Santo (UFES)

## Licença

Este projeto está sob a licença Creative Commons Attribution 4.0 International (CC BY 4.0). Você é livre para compartilhar e adaptar o material, desde que atribua o crédito apropriado.
