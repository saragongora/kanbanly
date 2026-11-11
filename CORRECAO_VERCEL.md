# Correção do deploy Vercel — Kanbanly 1.6.2

O erro `node_modules/.bin/tsc: Permission denied` (código 126) ocorre quando o sistema não pode executar o shim `tsc`.

O script `build` foi alterado para executar TypeScript e Vite pelo Node diretamente:

```json
"build": "node ./node_modules/typescript/bin/tsc -b && node ./node_modules/vite/bin/vite.js build"
```

## Publicação

1. Substitua os arquivos no repositório GitHub pelos deste ZIP e faça commit.
2. Na Vercel, confira Root Directory (pasta que contém `package.json`), Framework Vite, Build Command `npm run build` e Output Directory `dist`.
3. Faça um novo deploy com **Use existing Build Cache** desativado, se disponível.
4. Se ainda houver problemas, confira se o repositório contém `node_modules` (não deve conter) e se há `.npmrc` com configurações antigas.

O aviso de `esbuild` é distinto da falha do `tsc`. Se a instalação de esbuild for bloqueada pelo gerenciador npm, será necessário aprovar seus scripts conforme as políticas do ambiente.

Antes de trocar o domínio, exporte um backup JSON das tarefas.
