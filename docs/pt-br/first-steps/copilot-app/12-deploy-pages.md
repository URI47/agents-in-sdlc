---
title: "Lição 12 - Publique o site com o GitHub Pages"
description: "Use o aplicativo GitHub Copilot para configurar um fluxo de trabalho do Pages, revisar o pull request e verificar o Space Quiz publicado."
authors:
  - jamesmontemagno
lastUpdated: 2026-10-12
---

Publique o Space Quiz no GitHub Pages para que qualquer pessoa possa acessar o site. O Copilot pode preparar o fluxo de trabalho e orientar a implantação, mas você é responsável por revisar as alterações e confirmar que o site está no ar.

Nesta lição, você vai:

- pedir ao Copilot para configurar uma implantação do GitHub Pages.
- revisar o fluxo de trabalho e o pull request antes de fazer o merge.
- acompanhar a implantação e verificar o site publicado.

## Cenário

O Space Quiz já está em um repositório do GitHub, mas ainda precisa de uma forma simples para as pessoas experimentarem. Publicar o site de arquivo único com o GitHub Pages o disponibiliza em uma URL pública, sem adicionar um servidor ou uma dependência de runtime.

## Peça ao Copilot para preparar a implantação

> [!WARNING]
> Criar um pull request pode confirmar e enviar código. Revise as configurações de aprovação e o repositório de destino antes de enviar este prompt. Com **Approve all**, não espere outra solicitação de confirmação.

Na sessão do aplicativo Copilot para `space-quiz`, envie este prompt:

```plaintext
Prepare uma implantação do GitHub Pages para este repositório. Crie um fluxo de trabalho do GitHub Actions que compile o site, se necessário, e o implante no GitHub Pages depois que as alterações chegarem à ramificação padrão. Adicione um README que descreva o aplicativo e como executá-lo localmente, caso ainda não exista. Crie um pull request com essas alterações e informe o link e quaisquer configurações ou permissões necessárias do Pages. Não faça merge, não habilite o merge automático, não altere as configurações do Pages nem implante o site. Pare e aguarde minha revisão.
```

## Revise o fluxo de trabalho e o pull request

1. Confirme que o README só foi adicionado se o repositório ainda não tinha um.
2. Revise as alterações do pull request, incluindo as etapas de compilação e implantação do fluxo de trabalho, os gatilhos e as permissões.
3. Confirme que o fluxo de trabalho implanta a partir da ramificação padrão, e não de um pull request ainda não mesclado.
4. Solicite as correções necessárias e revise o diff atualizado. Aguarde a aprovação nas verificações obrigatórias do pull request antes de autorizar o merge.

## Autorize o merge e a implantação

> [!WARNING]
> O prompt a seguir autoriza o agente a fazer merge do pull request revisado, alterar as configurações do Pages do repositório e publicar o site. Envie-o somente depois de concluir a revisão e confirmar o repositório e o pull request. Dependendo das configurações de aprovação, essas ações podem ocorrer sem outra solicitação de confirmação.

Substitua `<PR_NUMBER>` pelo número do pull request revisado e envie este prompt separadamente:

```plaintext
Revisei o pull request <PR_NUMBER> neste repositório e autorizo o merge e a implantação. Habilite o GitHub Pages usando o GitHub Actions, faça merge somente desse pull request depois que as verificações obrigatórias forem aprovadas e acompanhe a implantação até que seja concluída com sucesso. Informe a URL final do site publicado. Se você não tiver permissão para habilitar o Pages ou fazer merge, diga exatamente o que preciso aprovar ou fazer; não informe que a implantação foi bem-sucedida até que o site esteja no ar.
```

![Diagrama em três etapas: um pull request do space-quiz mesclado; uma execução bem-sucedida de Deploy website no GitHub Actions com as etapas Build website, Upload artifact e Deploy to Pages; e o Space Quiz publicado em yourname.github.io/space-quiz/.](../../../_images/first-steps-app-pages-deploy.svg)

## Verifique a implantação

1. Acompanhe a execução de implantação do GitHub Actions até que ela seja concluída com sucesso.
2. Abra a URL informada e confirme que o Space Quiz carrega.

Se o agente não puder habilitar o Pages ou fazer merge do pull request, siga as instruções específicas fornecidas por ele. Não considere a tarefa concluída até que a implantação tenha sucesso e o site esteja no ar.

## Resumo e próximos passos

O Space Quiz agora está disponível como um site, e você verificou a implantação em vez de confiar apenas no relato do agente. Continue para a [Lição 13: Revisão e próximos passos][next-lesson].

[next-lesson]: ../13-review/
