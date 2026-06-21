# Smart Invest B3 — Painel de Ações

Painel web (arquivo único `index.html`) com cotações em tempo real, histórico de preços e dividendos, e indicadores fundamentalistas das ~200 maiores ações da B3 por valor de mercado. Fontes de dados: [brapi.dev](https://brapi.dev) (cotações/histórico) e [Fundamentus](https://www.fundamentus.com.br) (indicadores e proventos, via r.jina.ai).

Os fundamentais (Fundamentus) funcionam sem nenhum cadastro. Para histórico de preços e dividendos de qualquer ação além das 4 de teste do brapi.dev (PETR4, VALE3, ITUB4, MGLU3), é necessária uma chave gratuita do brapi.dev — crie a sua em [brapi.dev](https://brapi.dev) (sem cartão, 15 mil requisições/mês) e cole no ícone 🔑 no topo do painel. A chave fica salva no navegador de cada pessoa (localStorage), então cada usuário configura a própria.

## Como publicar no GitHub Pages (gratuito)

Siga estes passos (leva ~5 minutos):

1. **Crie uma conta no GitHub** (se ainda não tiver): [github.com/signup](https://github.com/signup) — gratuito.

2. **Crie um novo repositório**:
   - Acesse [github.com/new](https://github.com/new)
   - Nome do repositório: por exemplo `smart-invest-b3`
   - Marque como **Public**
   - Clique em **Create repository**

3. **Envie o arquivo**:
   - Na página do repositório recém-criado, clique em **uploading an existing file** (ou "Add file" → "Upload files")
   - Arraste o arquivo `index.html` (está nesta mesma pasta)
   - Clique em **Commit changes**

4. **Ative o GitHub Pages**:
   - Vá em **Settings** (Configurações) do repositório
   - No menu lateral, clique em **Pages**
   - Em "Build and deployment" → "Source", selecione **Deploy from a branch**
   - Em "Branch", selecione **main** (ou `master`) e pasta **/ (root)**
   - Clique em **Save**

5. **Acesse o painel online**:
   - Após 1–2 minutos, o GitHub mostrará o link no formato:
     `https://SEU-USUARIO.github.io/smart-invest-b3/`
   - Esse link pode ser compartilhado com qualquer pessoa — todos verão os mesmos dados em tempo real, sem precisar configurar nada.

## Atualizações futuras

Sempre que você editar o `index.html` (por exemplo, pedindo novas melhorias aqui), basta repetir o passo 3 (subir o arquivo atualizado, sobrescrevendo o anterior) — o GitHub Pages atualiza automaticamente.

## Observações

- A lista cobre as ~200 maiores ações da B3 por valor de mercado (apenas tickers ativos e válidos, sem BDRs ou fracionário).
- Os dados de **fundamentais** (P/L, P/VP, ROE, etc.) vêm do Fundamentus.
- Os dados de **cotação atual e variação do dia** (lista geral) vêm do brapi.dev e não exigem chave.
- Os dados de **histórico de preços** (gráfico ao clicar numa ação) e variações em outros períodos exigem uma chave gratuita do brapi.dev, exceto para PETR4, VALE3, ITUB4 e MGLU3.
- Os dados de **dividendos** vêm da página de proventos do Fundamentus e não exigem chave.
- Em caso de instabilidade de alguma fonte (não relacionada à chave), o painel exibe um modo de demonstração (rótulo "DEMO") até a fonte voltar a responder.
- No cabeçalho, o botão 🔑 abre a configuração da chave brapi.dev e o botão ⟳ atualiza manualmente os dados.
