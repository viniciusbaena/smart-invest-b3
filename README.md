# Smart Invest B3 — Painel de Ações

Painel web (arquivo único `index.html`) com cotações em tempo real, histórico de preços (até 10 anos) e dividendos, e indicadores fundamentalistas das ~200 maiores ações da B3 por valor de mercado. Fontes de dados: [brapi.dev](https://brapi.dev) (cotação atual, 52 semanas, market cap), [Yahoo Finance](https://finance.yahoo.com) (histórico de preços, via r.jina.ai) e [Fundamentus](https://www.fundamentus.com.br) (indicadores e proventos, via r.jina.ai).

O painel já vem com uma chave do brapi.dev embutida no código, então quem acessa não precisa configurar nada. Essa chave é usada só para cotação atual e dados de 52 semanas/market cap — o histórico de preços (gráficos e variações por período) vem do Yahoo Finance, que não exige chave nem tem limite de plano para nenhuma ação.

> **Nota de segurança:** como este é um site estático (GitHub Pages), a chave do brapi.dev embutida fica visível para qualquer pessoa que abrir o código-fonte da página ou o repositório no GitHub. Essa é uma decisão consciente para priorizar a experiência do visitante — mas significa que a chave pode ser copiada e usada por terceiros, consumindo a cota mensal gratuita (15 mil requisições/mês) do brapi.dev. Se isso acontecer, apenas os dados de 52 semanas/market cap no modal ficam indisponíveis temporariamente — cotação, histórico de preços e dividendos continuam funcionando normalmente, pois não dependem dessa chave. Para trocar a chave sem precisar editar o código manualmente, gere uma nova em [brapi.dev](https://brapi.dev) e substitua o valor de `DEFAULT_BRAPI_KEY` no `index.html`.

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
- Os dados de **cotação atual e variação do dia** (lista geral) vêm do brapi.dev (`/quote/list`, sem chave).
- Os dados de **histórico de preços** (gráfico ao clicar numa ação, e variações em todos os períodos) vêm do Yahoo Finance, para qualquer uma das 200 ações, até 10 anos.
- Os dados de **52 semanas e market cap** (modal) vêm do brapi.dev usando a chave embutida.
- Os dados de **dividendos** vêm da página de proventos do Fundamentus e não exigem chave.
- Em caso de instabilidade de alguma fonte, o painel exibe um modo de demonstração (rótulo "DEMO") até a fonte voltar a responder — nunca dados inventados silenciosamente.
- No cabeçalho, o botão ⟳ atualiza manualmente os dados.
