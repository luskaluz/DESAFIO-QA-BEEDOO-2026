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
- Validação de campos obrigatórios no cadastro de cursos
- Validação de formatos de dados (datas, número de vagas, URL de imagem)
- Comportamento do sistema ao cadastrar cursos com dados inválidos
- Comportamento da listagem após o cadastro de novos cursos
- Possível cadastro de cursos duplicados
- Validação de consistência entre datas (início e fim)
- Funcionamento da exclusão de cursos a partir da listagem

---

## 2. Decisões tomadas e raciocínio durante a análise

### Por onde comecei

Como a listagem estava vazia ao abrir a aplicação, decidi começar diretamente pela tela de cadastro. O raciocínio foi simples: sem cadastrar um curso, não seria possível verificar se a listagem funcionava corretamente. O cadastro era o pré-requisito para testar qualquer outra funcionalidade.

### Decisões tomadas por intuição

Alguns cenários de teste surgiram naturalmente durante a exploração, sem estar em um roteiro planejado:

**Cadastro com campos vazios:** A primeira coisa que quis verificar foi se o sistema validava o formulário antes de permitir o cadastro. Tentei cadastrar sem preencher nenhum campo para confirmar se havia alguma proteção mínima — e o sistema não impediu.

**Datas absurdas e números de vagas extremos:** Durante os testes de validação, percebi que os campos de data e número de vagas poderiam aceitar qualquer valor sem restrição. Por isso, decidi inserir valores completamente fora do contexto real, como anos no século 10 e números excessivamente grandes, para observar o comportamento do sistema nesses limites.

Esses cenários não estavam no plano inicial, mas surgiram como consequência natural de observar como o sistema reagia a entradas inesperadas.

### Por que gravei um vídeo para a exclusão

O fluxo de exclusão teve atenção especial porque suspeitei que o problema poderia não ser imediatamente visível. Minha hipótese era que o sistema poderia exibir uma notificação de sucesso sem que a exclusão fosse de fato persistida — e que isso só ficaria evidente ao atualizar a página.

Por isso, decidi gravar o fluxo completo: clicar em excluir, visualizar a notificação e atualizar a página para verificar se o curso realmente havia sido removido. Essa decisão foi tomada para ter uma evidência clara do comportamento inconsistente entre o feedback visual e o resultado real da ação.

---

## 3. Estrutura do repositório

```
/
├── README.md
├── bugs/
│   └── relatorio-bugs.md
└── evidencias/
    ├── [prints dos testes]
    └── [vídeo da exclusão]
```

## 4. Casos de teste

Os cenários e casos de teste criados para o módulo de cursos estão documentados na planilha:
[\[Link para o Google Sheets\]](https://docs.google.com/spreadsheets/d/1HaFjkaRQCLT1FM3S7DBxauZcsITm-9HalMvV9iro9Oc/edit?usp=sharing)

## 5. Relatório de bugs

Os bugs identificados durante a execução dos testes estão documentados em:
`/bugs/relatorio-bugs.md`

## 6. Evidências de execução

As evidências (prints e vídeo) da execução dos testes estão disponíveis em:
`/evidencias`
