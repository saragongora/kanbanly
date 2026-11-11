# Publicar Kanbanly na Vercel

## 1. Teste local
Abra a pasta que contém `package.json` e execute:

```powershell
npm.cmd install
npm.cmd run build
npm.cmd run dev
```

Confirme que a barra lateral rola independentemente e que Exportar/Importar estão acessíveis, tanto no computador quanto no celular.

## 2. Publicação via GitHub (recomendada)
1. Crie um repositório no GitHub e envie **o conteúdo da pasta `kanbanly`** (não `node_modules` nem `dist`).
2. Em https://vercel.com/new, escolha **Import Git Repository** e selecione o repositório.
3. Configure **Framework Preset: Vite**; **Root Directory:** pasta onde está `package.json`; **Build Command:** `npm run build`; **Output Directory:** `dist`; **Install Command:** `npm install`.
4. Clique **Deploy**. A Vercel fornecerá um endereço HTTPS.
5. Novos commits na branch de produção criarão novas publicações automaticamente.

## 3. Publicação sem GitHub (CLI)
Na pasta `kanbanly`, execute:

```powershell
npm.cmd install
npm.cmd run build
npx.cmd vercel login
npx.cmd vercel --prod
```

Siga as perguntas do terminal e confirme o diretório do projeto. O arquivo `vercel.json` já está incluído.

## 4. Dados e notificações
- O `localStorage` é separado por domínio, navegador e dispositivo. Antes de mudar de endereço, use **Exportar** no site antigo e **Importar** no site publicado.
- O modo escuro e as tarefas são mantidos localmente por navegador.
- Notificações precisam de permissão e dependem da página aberta; publicar não as transforma em notificações em segundo plano.
- HTTPS é oferecido pela Vercel para o domínio publicado.
