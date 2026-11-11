# Publicando o Kanbanly 1.6

## 1. Testar no computador

Requisitos: Node.js 22.12+ (ou versão compatível com o Vite instalado).

No PowerShell do VS Code, dentro da pasta `kanbanly`:

```powershell
npm.cmd install
npm.cmd run build
npm.cmd run preview
```

Abra o endereço informado. `npm.cmd` evita o bloqueio de `npm.ps1` do PowerShell.

## 2. Publicar com Netlify (recomendado)

1. Crie uma conta em https://www.netlify.com/.
2. Coloque a pasta `kanbanly` em um repositório GitHub (sem `node_modules` e `dist`).
3. No painel da Netlify, escolha **Add new project > Import an existing project** e conecte o repositório.
4. Defina **Base directory** como a raiz do projeto (`kanbanly`, se o repositório contiver uma pasta de mesmo nome; deixe vazio se os arquivos estiverem na raiz).
5. **Build command:** `npm run build`; **Publish directory:** `dist` (ou `kanbanly/dist` se a base for a raiz do repositório).
6. Publique e abra a URL HTTPS fornecida.

O arquivo `netlify.toml` já contém a configuração de build, versão Node e fallback para SPA.

### Alternativa: Netlify Drop (sem GitHub)

1. Execute `npm.cmd install` e `npm.cmd run build` localmente.
2. Abra https://app.netlify.com/drop.
3. Arraste **somente a pasta `dist`**, não a pasta com os arquivos fonte.
4. O site estará disponível em um endereço HTTPS.

## 3. Alternativa: Vercel

1. Envie o projeto para um repositório GitHub.
2. Entre em https://vercel.com/new e importe o repositório.
3. Se necessário, configure a pasta raiz como `kanbanly`.
4. Framework: Vite; build: `npm run build`; saída: `dist`.
5. Clique em Deploy. O arquivo `vercel.json` já inclui fallback para SPA.

## 4. Domínio personalizado

No painel da hospedagem, procure **Domain management / Domains**, adicione o domínio e siga as instruções de DNS exibidas pelo provedor. Aguarde a propagação e confira HTTPS.

## 5. Armazenamento e migração de dados

O Kanbanly salva tarefas no `localStorage` por **origem** (protocolo + domínio + porta). Isso significa que dados de `localhost:5173` **não aparecem automaticamente** no endereço publicado, mesmo no mesmo computador.

Antes de migrar: no site antigo, use **Exportar JSON**. No site publicado, use **Importar JSON**. Faça cópias de segurança antes de importar e teste com cuidado para evitar sobrescrever tarefas.

Não há sincronização entre navegadores, usuários ou dispositivos. Limpar dados do navegador pode apagar tarefas.

## 6. Notificações

Notificações dependem de permissão do navegador e HTTPS. A versão 1.6 verifica os prazos **enquanto a página estiver aberta**; não envia alertas com o site fechado. Alguns navegadores móveis têm restrições adicionais.

## 7. Checklist antes de divulgar

- [ ] `npm.cmd run build` conclui sem erros.
- [ ] Quadro, calendário, produtividade, lembretes e lixeira abrem.
- [ ] Criar/editar/mover/concluir/excluir/restaurar tarefas funciona.
- [ ] Claro / Jardim Noturno / Automático funcionam.
- [ ] Recarregar a página preserva tarefas.
- [ ] Exportar e importar JSON funciona.
- [ ] Testar em celular e computador.
- [ ] Conferir HTTPS e solicitar permissão para notificações.

## 8. Atualizações futuras

Com GitHub conectado, enviar alterações para a branch de publicação pode iniciar um novo deploy automaticamente. Os dados salvos no navegador normalmente permanecem se a origem do site não mudar e o aplicativo continuar usando as mesmas chaves de armazenamento.
