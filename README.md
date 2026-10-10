# Radar de vendas da hamburgueria

Dashboard didático para a atividade de Fundamentos de IA e Análise de Dados. A base inicial (`public/dados-exemplo.csv`) é fictícia, tem 200 vendas distribuídas em 12 meses e aparece imediatamente na tela. O arquivo original `vendas_hamburgueria.csv` foi preservado na raiz; ele pode ser importado pelo seletor caso deseje analisá-lo.

O dashboard agora possui uma tela de login demonstrativa. Use `aluno@demo.com` com a senha `hamburguer`. Como é um site estático, essa autenticação acontece apenas no navegador e serve para apresentação/protótipo; não substitui um sistema de segurança com servidor. A imagem da tela de entrada é carregada do Unsplash, portanto precisa de internet para aparecer.

## Como executar

Abra `public/index.html` diretamente no navegador. Para os gráficos e a importação CSV, é necessário acesso à internet, pois Chart.js 4.4.4 e Papa Parse 5.4.3 são carregados por CDN. A amostra inicial está incorporada no JavaScript, portanto o dashboard continua funcionando quando aberto por duplo clique.

Use **Importar CSV** para selecionar uma base própria. Ela deve conter `id_venda`, `data` (AAAA-MM-DD), `produto`, `categoria`, `regiao`, `quantidade` e `preco_unitario`. Linhas com campos obrigatórios ausentes, datas inválidas ou números negativos/não numéricos são descartadas e contabilizadas na mensagem de validação. IDs repetidos são mantidos como linhas de venda e a quantidade de vendas usa IDs únicos.

## Indicadores e análise

- Faturamento da linha = `quantidade × preco_unitario`.
- Faturamento total = soma do faturamento das linhas filtradas.
- Quantidade de vendas = número de `id_venda` únicos.
- Unidades vendidas = soma de `quantidade`.
- Ticket médio = faturamento total ÷ quantidade de vendas (R$ 0,00 quando não há vendas).

Filtros, pesquisa e ordenação atualizam simultaneamente cartões, gráficos e tabela. O botão de exportação baixa somente os registros filtrados em CSV.

## Publicação no Render

1. Envie o projeto para um repositório no GitHub.
2. No Render, crie um novo **Static Site** e escolha o repositório.
3. Selecione a branch que contém o projeto.
4. Deixe **Root Directory** vazio.
5. Informe `echo "Site pronto"` em **Build Command**.
6. Informe `public` em **Publish Directory** e publique.

Não há backend, banco de dados ou etapa de compilação.
