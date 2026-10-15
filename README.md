# Dá pra morar em Lucas? Preço dos imóveis x renda — a conta da acessibilidade

Análise de dados que cruza o preço dos imóveis de Lucas do Rio Verde (MT) com a renda local para medir a acessibilidade: quanto um imóvel custa em anos de renda, e que renda familiar é preciso ter para financiá-lo.

> **Pergunta de negócio:** Com a renda praticada na região, quem consegue comprar um imóvel em Lucas do Rio Verde hoje — e de quanto precisa ser a renda familiar para isso?

---

## Esta é a 4ª camada de uma análise sobre habitação em Lucas do Rio Verde

- **[Camada 1 — Projeção populacional e demanda](https://github.com/thamires-siriustech/previsao-populacional-lucas-do-rio-verde)** — a *demanda* futura por moradia.
- **[Camada 2 — Oferta habitacional](https://github.com/thamires-siriustech/habitacao-social-lucas-do-rio-verde)** — a *oferta* real de habitação de interesse social.
- **[Camada 3 — Preços do mercado](https://github.com/thamires-siriustech/precos-imoveis-lucas-do-rio-verde)** — o *preço* do m² e por bairro.
- **Camada 4 (este repositório)** — a *acessibilidade*: o preço frente à renda.

## Principais resultados

- O imóvel típico (R$ 540 mil) exige, para ser financiado, uma renda familiar de cerca de **R$ 13 mil/mês — perto de 8 salários mínimos** — além de R$ 108 mil de entrada (20%, 30 anos, ~11% a.a.).
- Em anos de renda integral, ele custa de **3,5 anos** (família de 8 SM) a quase **14 anos** (família de 2 SM) — acima da linha de 5 anos que marca, internacionalmente, um mercado severamente inacessível (índice Demographia).
- Mercado segmentado por renda: **4 salários mínimos alcançam ~2% dos imóveis; 8 SM chegam a 50%; só 10 SM alcançam a maioria (74%).**
- Frente ao rendimento médio individual de Mato Grosso (R$ 3.402, PNAD/IBGE), o imóvel típico equivale a cerca de 13 anos de renda.
- Fecha a trilogia: a cidade cresceu, construiu menos do que precisava, os preços subiram a patamar de capital — e morar nela ficou caro demais para a renda local típica.

## Metodologia

1. **Base de preços** — dataset da Camada 3 (236 anúncios de 13 imobiliárias, out/2026).
2. **Âncoras de renda** — salário mínimo 2026 (R$ 1.621) e rendimento médio mensal de Mato Grosso (R$ 3.402/pessoa, PNAD Contínua/IBGE 2024). Como o IBGE não publica uma renda familiar fechada para Lucas, a acessibilidade é calculada **em função da renda**, por faixa, em vez de cravar um único número local.
3. **Indicadores** — anos de renda para comprar o imóvel típico; simulação de financiamento (parcela e renda necessária); teto de imóvel financiável por faixa de renda e fatia do mercado alcançada.

## Stack técnico

- **Python** — pandas, numpy
- **Visualização** — matplotlib
- **Ambiente** — Jupyter Notebook

## Como executar

```bash
git clone https://github.com/thamires-siriustech/acessibilidade-imovel-lucas-do-rio-verde.git
cd acessibilidade-imovel-lucas-do-rio-verde
pip install -r requirements.txt
jupyter notebook analise_acessibilidade_lucas.ipynb
```

Mantenha o notebook e o CSV na mesma pasta. No Jupyter, use **Kernel → Restart & Run All**.

## Estrutura do repositório

```
acessibilidade-imovel-lucas-do-rio-verde/
├── analise_acessibilidade_lucas.ipynb   # análise completa
├── precos_imoveis_lucas.csv             # base de preços (da Camada 3)
├── requirements.txt
└── README.md
```

## Limitações

- **Preço de anúncio, não de venda** — valor pedido, geralmente acima do fechamento.
- **Sem renda familiar municipal fechada** — por isso a análise é feita por faixa de renda, ancorada no salário mínimo e no rendimento médio de MT; é um retrato da relação preço/renda, não da renda exata da cidade.
- **Parâmetros de financiamento assumidos** (entrada 20%, 30 anos, 10–12% a.a., Price, parcela em 30% da renda) — premissas padrão de mercado; condições reais variam por banco e programa (ex.: Minha Casa Minha Vida).
- **Renda familiar, não individual** — os cenários supõem a renda somada da família.

## Fontes dos dados

Dataset de preços da Camada 3 (anúncios de imobiliárias de Lucas do Rio Verde). Salário mínimo 2026. Rendimento médio de Mato Grosso — PNAD Contínua/IBGE (2024).

---

**Autora:** Thamires Martins da Silva
Projeto de portfólio em análise de dados — Camada 4 de 4.
