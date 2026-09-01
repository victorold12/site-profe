# Os 2 painéis AcessoPro — prontos para a Vercel

Estrutura preparada para deploy. Cada pasta é um site independente, em HTML puro,
sem framework, sem build e sem configuração especial.

```
painel-1/          Painel administrativo  (vendas, cupons, parceiros, repasses, checkout)
  index.html
  vercel.json
  README.md
painel-2/          Portal do parceiro     (login, cupom, comissões, repasses, perfil)
  index.html
  vercel.json
  README.md
```

Os arquivos já foram renomeados para `index.html`, que é o nome que a Vercel procura.

---

## Caminho A — dois repositórios separados (o que você pediu)

Dá dois links completamente independentes. É preciso criar os repositórios manualmente,
porque a integração do Claude com o GitHub tem permissão para escrever em repositórios
existentes, mas **não** para criar repositórios novos.

### 1. Criar os repositórios no GitHub (pelo iPhone)

1. Abra [github.com/new](https://github.com/new).
2. Em **Repository name**, digite `painel-1`.
3. Deixe **Public** marcado e **não** marque "Add a README file".
4. Toque em **Create repository**.
5. Repita tudo para `painel-2`.

### 2. Enviar os arquivos

Duas opções:

**Opção rápida — me avisar.** Depois de criar os dois repositórios vazios, é só me dizer
"criei os repos" que eu envio `index.html`, `vercel.json` e `README.md` para cada um.

**Opção manual — pelo próprio GitHub.** Na tela do repositório recém-criado, toque em
**uploading an existing file** e envie o `index.html` da pasta correspondente
(`painel-1/index.html` vai para o repositório `painel-1`, e assim por diante).
Envie também o `vercel.json`, que é opcional mas melhora o cache e os headers.

### 3. Importar na Vercel

1. Acesse [vercel.com](https://vercel.com) e faça login com o GitHub.
2. Toque em **Add New → Project**.
3. Em **Import Git Repository**, escolha `painel-1`.
4. Não altere nada — Framework Preset em **Other**, Build Command e Output Directory vazios.
5. Toque em **Deploy**.
6. Repita para `painel-2`.

Resultado: dois endereços parecidos com `painel-1.vercel.app` e `painel-2.vercel.app`.
Se o nome já estiver em uso na Vercel, ela acrescenta um sufixo — dá para trocar depois em
**Settings → Domains** do projeto.

---

## Caminho B — um repositório só, dois sites (sem criar nada)

A Vercel permite importar o **mesmo** repositório várias vezes, apontando cada projeto para
uma pasta diferente. Assim os dois sites saem direto deste repositório.

1. Na Vercel, toque em **Add New → Project** e importe `site-profe`.
2. Antes de dar Deploy, abra **Root Directory**, toque em **Edit** e escolha `painel-1`.
3. Dê um nome ao projeto (por exemplo `acessopro-admin`) e toque em **Deploy**.
4. Repita o processo importando `site-profe` de novo, agora com Root Directory `painel-2`.

**Atenção:** por padrão a Vercel publica a branch de produção do repositório (normalmente
`main`). Estes arquivos estão na branch `claude/mandie-2-paineis-vercel-sr2qht`. Então
faça uma das duas coisas:

- juntar essa branch na `main` no GitHub; **ou**
- na Vercel, ir em **Settings → Git → Production Branch** e trocar para
  `claude/mandie-2-paineis-vercel-sr2qht`.

---

## O que ainda não funciona

O backend é **fictício e local**. Publicar na Vercel faz a interface funcionar por completo,
mas os dados continuam salvos no navegador de cada dispositivo (`localStorage`).

Na prática isso significa que:

- o painel administrativo e o portal do parceiro **não compartilham vendas** entre si;
- abrir o mesmo painel em outro celular mostra outros dados;
- limpar os dados do navegador apaga tudo.

Para os painéis conversarem de verdade, o próximo passo é um backend real — Supabase,
Firebase ou Vercel com banco de dados. Aí as vendas registradas no administrativo aparecem
automaticamente no portal do parceiro correspondente.
