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


## Kanbanly 1.5 — Dashboard de produtividade

- Menu **Produtividade**: cartões com total, concluídas, fazendo e atrasadas.
- Gráfico de barras com conclusões dos últimos sete dias, incluindo hoje.
- Gráfico de rosca com distribuição atual entre pendentes, fazendo e concluídas.
- Lista das tarefas atrasadas com atalho para editar.
- O campo `completedAt` registra o momento da conclusão. É removido quando a tarefa sai de Concluídas e recriado na próxima conclusão.
- Tarefas antigas continuam funcionando. Como versões anteriores não guardavam a data de conclusão, elas aparecem no total concluído, mas não no histórico semanal.
- Dados continuam em `localStorage` com a mesma chave e backups JSON.

## Novidade 1.6 — Jardim Noturno 🌙

- Alternância de aparência no menu lateral: **Claro**, **Noturno** ou **Auto** (segue a preferência do dispositivo).
- Tema escuro com azul-noite, azul ardósia, verde sálvia, lavanda e dourado suave, aplicado às páginas, cartões, formulários, calendário, dashboard e lixeira.
- Preferência salva na chave `kanbanly.theme.v1` do `localStorage`; as tarefas continuam na chave original `kanbanly.tasks.v1`.
- O modo Auto responde às mudanças do sistema sem recarregar a página.
- Respeita a configuração de movimento reduzido do dispositivo.

**Atualização:** faça backup das tarefas em **Exportar** antes de substituir os arquivos do projeto. A versão 1.6 não apaga nem migra a lista existente.

## Publicação na internet

Consulte **GUIA_PUBLICACAO.md** para instruções detalhadas de Netlify, Vercel, domínio, HTTPS, backups e migração do `localStorage`.


### Ajustes 1.6.3
- Melhor contraste do seletor de status dos cartões no modo noturno.
- Títulos em verde sálvia claro e creme lunar no modo noturno.
- Remoção dos imports não utilizados `ChevronDown` e `Tag` para o build TypeScript.
