# Publicação em andrevrc.github.io

Este guia cobre o deploy deste site Astro no GitHub Pages a partir de um **repositório privado**.

## Pré-requisitos

- Conta no GitHub
- `git` configurado localmente
- Token de acesso clássico (classic) do GitHub com escopo `repo` (para repositórios privados)

---

## Passo a passo

### 1. Ajustar configuração do Astro

O arquivo `astro.config.mjs` já está configurado para `andrevrc.dev`. Como vamos publicar em `andrevrc.github.io`, altere:

```js
// astro.config.mjs
export default defineConfig({
  site: 'https://andrevrc.github.io',
  base: '/',
  // ...
});
```

> Se quiser usar domínio próprio depois, basta voltar para `https://andrevrc.dev` e configurar o CNAME no GitHub Pages.

### 2. Criar o repositório no GitHub

Crie um repositório **privado** com o nome:

```
andrevrc.github.io
```

> O nome **precisa** ser exatamente `andrevrc.github.io` para o GitHub Pages entender que é um site de usuário.

### 3. Subir o código

```bash
git remote add origin git@github.com:andrevrc/andrevrc.github.io.git
git branch -M main
git push -u origin main
```

### 4. Ativar GitHub Pages

1. Vá em **Settings > Pages** do repositório `andrevrc/andrevrc.github.io`
2. Em **Source**, selecione **GitHub Actions**
3. (Não precisa configurar branch — o workflow já faz tudo)

### 5. Verificar o deploy

1. Vá na aba **Actions** do repositório
2. Veja se o workflow `Deploy to GitHub Pages` rodou com sucesso (deve iniciar automaticamente após o push)
3. Acesse `https://andrevrc.github.io` — o site estará no ar

### 6. Repositório privado — atenção

Repositórios privados no plano **GitHub Free** têm limite de **500 MB** de armazenamento de Actions artifacts por mês. O deploy do site gera ~1 MB por build, então dá para ~500 deploys mensais sem custo.

Se precisar de mais, o plano **GitHub Pro** (ou Teams) aumenta o limite.

### 7. Próximos deploys

Sempre que fizer `git push` para a branch `main`, o GitHub Actions executa automaticamente:

```bash
git add -A
git commit -m "descrição das alterações"
git push
```

---

## Troubleshooting

**O Action falhou?**
1. Vá em **Actions** > clique no workflow com falha
2. Veja os logs para identificar o erro
3. Problema comum: `npm ci` falha se o `package-lock.json` estiver desatualizado — rode `npm install` localmente e commite o lockfile

**O site subiu mas está em branco?**
1. Verifique se o `site` no `astro.config.mjs` está correto
2. Verifique se o `base` está como `'/'`
3. No navegador, abra o DevTools > Console para ver erros de rota

**Quer usar domínio próprio no futuro?**
1. Configure um domínio (ex: `andrevrc.dev`) no Cloudflare ou onde estiver o DNS
2. Em Settings > Pages do repositório, adicione o domínio customizado
3. Atualize `site` no `astro.config.mjs` para a URL final
