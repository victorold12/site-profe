# painel-1 — AcessoPro (Painel Administrativo)

Painel administrativo do AcessoPro em **HTML puro**. Sem framework, sem build, sem dependências.

## O que tem aqui

- Visão geral (centro de operações)
- Vendas atribuídas
- Cupons de parceiros
- Rede de parceiros
- Repasses e comissões
- Checkout Lab
- Configurações

## Arquivos

| Arquivo       | Função                                                    |
| ------------- | --------------------------------------------------------- |
| `index.html`  | O painel inteiro (HTML + CSS + JS em um arquivo só)        |
| `vercel.json` | Configuração estática da Vercel (headers e `cleanUrls`)    |

## Deploy na Vercel

1. Acesse [vercel.com](https://vercel.com) e faça login com o GitHub.
2. Toque em **Add New → Project**.
3. Em **Import Git Repository**, escolha este repositório.
4. Não mexa em nada: Framework Preset fica **Other**, Build Command e Output Directory ficam vazios.
5. Toque em **Deploy**.

Como é HTML puro, não existe build. O deploy leva alguns segundos.

## Aviso importante

O backend é **fictício e local**. Os dados ficam salvos no `localStorage` do navegador de cada
dispositivo — ou seja, cada celular/computador que abrir o painel terá os seus próprios dados,
e este painel **não compartilha vendas** com o Portal do Parceiro (`painel-2`).

Para os dois painéis compartilharem dados de verdade, é preciso um backend real
(Supabase, Firebase ou Vercel + banco de dados).
