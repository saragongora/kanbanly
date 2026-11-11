# ✿ Kanbanly 1.3

Gerenciador de tarefas pessoal com quadro Kanban, visual delicado e armazenamento local.

## Como executar

1. Instale o [Node.js](https://nodejs.org/) versão 20.19+ ou 22.12+.
2. Abra um terminal dentro da pasta `kanbanly`.
3. Execute:

```bash
npm install
npm run dev
```

4. Abra o endereço mostrado no terminal (normalmente http://localhost:5173).

Para gerar uma versão de produção:

```bash
npm run build
npm run preview
```

## Notificações de prazos (1.3)

Na seção **Lembretes**, ative as notificações e permita que o navegador mostre avisos. Escolha antecedência de 0, 1, 2, 3 ou 7 dias. O Kanbanly avisa sobre tarefas pendentes ou em andamento, incluindo atrasadas, no máximo uma vez por dia para cada tarefa, prazo e antecedência. Concluídas e tarefas na lixeira não notificam. Configurações e histórico de avisos ficam no localStorage.

**Limitação importante:** os avisos funcionam enquanto a página estiver aberta e em contexto seguro (`localhost` ou HTTPS). Não há push remoto ou execução em segundo plano com a página fechada. Alguns navegadores limitam notificações em dispositivos móveis.

## Funcionalidades

- Criar e editar tarefas com título, descrição, status, subtarefas e data de vencimento opcional.
- Calendário mensal navegável, seleção de dias, tarefas por dia e criação de tarefa na data selecionada.
- Indicadores de prazo atrasado, vencendo hoje, futuro e concluído; painel de próximos prazos.
- Marcar subtarefas e acompanhar progresso por tarefa.
- Arrastar tarefas entre Pendentes, Fazendo e Concluídas, ou usar o seletor de status.
- Pesquisar tarefas.
- Excluir para a lixeira, restaurar e excluir permanentemente (com confirmação).
- Esvaziar lixeira com confirmação.
- Layout responsivo com menu lateral e navegação móvel.
- Persistência automática no `localStorage`.
- Exportar e importar backup JSON no menu lateral.

## Observações

- Os cartões de exemplo aparecem apenas no primeiro acesso; você pode excluí-los ou editá-los.
- Os dados ficam armazenados **somente no navegador e dispositivo atual**. Para transferir dados, use Exportar/Importar.
- Limpar os dados do navegador pode apagar as tarefas. Faça backups periodicamente.
- Não é necessário criar conta nem configurar banco de dados.
- A imagem `reference-palette.jpeg` é apenas a referência visual enviada e não é exibida no site.

## Tecnologias

React, TypeScript, Vite, Tailwind CSS, Lucide React e dnd-kit.

## Novidades visuais da versão 1.1

Cartões com efeitos de elevação, texturas sutis, flores decorativas, animações leves e respeito à preferência por movimento reduzido. Todas as funções da versão 1.0 foram preservadas.

## Atualização da versão 1.1

Os dados existentes permanecem na chave `kanbanly.tasks.v1` do localStorage, para preservar tarefas antigas. Datas são opcionais. Faça um backup JSON antes de atualizar. O armazenamento é específico da origem (endereço e porta) do navegador.


## Kanbanly 1.4 — Prioridades, etiquetas e filtros

- Cada tarefa pode ter prioridade baixa, média ou alta. Tarefas antigas recebem prioridade média por padrão.
- Crie até oito etiquetas coloridas por tarefa, escolhendo verde, amarelo, azul, rosa ou lilás.
- Filtre o quadro por prioridade, etiqueta e prazo; a busca também encontra nomes das etiquetas.
- Ordene as tarefas por prioridade ou data de vencimento. Use “Ordem manual” para recuperar a ordem normal do quadro.
- Etiquetas e prioridades são salvas no mesmo localStorage e incluídas nos backups JSON.
- Para atualizar, faça antes um backup usando o botão Exportar.
