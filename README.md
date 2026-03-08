# DESAFIO-QA-BEEDOO-2026


## 1. Análise da aplicação

### Objetivo da aplicação
A aplicação tem como objetivo permitir o cadastro e a visualização de cursos, possibilitando que usuários registrem informações sobre cursos e consultem os cursos cadastrados em uma listagem.

### Principais fluxos identificados
Durante a exploração inicial da aplicação foram identificados os seguintes fluxos:

- Cadastro de cursos
- Listagem de cursos
- Exclusão de cursos a partir da listagem

### Pontos críticos para teste

Os principais pontos considerados críticos para teste foram:

- Validação de campos obrigatórios no cadastro de cursos
- Validação de formatos de dados (datas, número de vagas, URL de imagem)
- Comportamento do sistema ao cadastrar cursos com dados inválidos
- Comportamento da listagem após o cadastro de novos cursos
- Possível cadastro de cursos duplicados
- Validação de datas (data de início maior que data de fim)
- Funcionamento da exclusão de cursos a partir da listagem

### Tela de listagem de cursos

A tela inicial apresenta uma lista de cursos cadastrados no sistema. 
Caso não existam cursos cadastrados, a lista permanece vazia.

### Tela de cadastro de cursos

A aplicação disponibiliza um formulário para cadastro de cursos contendo os seguintes campos:

- Nome do curso
- Descrição do curso
- Instrutor
- URL da imagem de capa
- Data de início
- Data de fim
- Número de vagas
- Tipo de curso
- Endereço do curso

## Casos de teste

Os cenários e casos de teste criados para o módulo de cursos estão disponíveis na planilha abaixo:

[\[Link para a planilha de testes\]](https://docs.google.com/spreadsheets/d/1HaFjkaRQCLT1FM3S7DBxauZcsITm-9HalMvV9iro9Oc/edit?usp=sharing)

## Evidências de execução

As evidências (prints) da execução dos testes podem ser encontradas na pasta:

/evidencias

## Relatório de Bugs

Os bugs identificados durante a execução dos testes estão documentados em:

/bugs/relatorio-bugs.md
