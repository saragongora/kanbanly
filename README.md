# ✿ Kanbanly 1.1

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

## Funcionalidades

- Criar e editar tarefas com título, descrição, status e subtarefas.
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
