# painel-2 — AcessoPro (Portal do Parceiro)

Portal do parceiro do AcessoPro em **HTML puro**. Sem framework, sem build, sem dependências.

## O que tem aqui

- Login do parceiro (com contas de demonstração)
- Visão geral do cupom e da performance
- Minhas vendas
- Comissões e repasses
- Meu perfil (com troca de foto)

## Contas de demonstração

Senha de todas: `demo123`

| Parceiro       | E-mail                   | Cupom      |
| -------------- | ------------------------ | ---------- |
| Lucas Andrade  | `lucas@acessopro.test`   | `LUCAS20`  |
| Bia Martins    | `bia@acessopro.test`     | `BIA25`    |
| Rafael Lima    | `rafael@acessopro.test`  | `RAFAEL10` |
| Marina Costa   | `marina@acessopro.test`  | `MARINA15` |

São credenciais fictícias de demonstração, sem valor real — a validação acontece
inteiramente no navegador.

## Arquivos

| Arquivo       | Função                                                    |
| ------------- | --------------------------------------------------------- |
| `index.html`  | O portal inteiro (HTML + CSS + JS em um arquivo só)        |
| `vercel.json` | Configuração estática da Vercel (headers e `cleanUrls`)    |

## Deploy na Vercel

1. Acesse [vercel.com](https://vercel.com) e faça login com o GitHub.
2. Toque em **Add New → Project**.
3. Em **Import Git Repository**, escolha este repositório.
4. Não mexa em nada: Framework Preset fica **Other**, Build Command e Output Directory ficam vazios.
5. Toque em **Deploy**.

## Aviso importante

O backend é **fictício e local**. Os dados ficam salvos no `localStorage` do navegador de cada
dispositivo — inclusive a foto de perfil. Este portal **não compartilha vendas** com o painel
administrativo (`painel-1`).

Para os dois painéis compartilharem dados de verdade, é preciso um backend real
(Supabase, Firebase ou Vercel + banco de dados).
