# Projeto IA — Simulação de Opinião Pública sobre Desigualdade

Trabalho da disciplina de Inteligência Artificial.

O objetivo é usar um modelo de linguagem (LLM) para simular como brasileiros respondem perguntas sobre desigualdade social, comparando as respostas geradas com os dados reais de uma pesquisa do CESOP/UNICAMP.

## Sobre o projeto

A ideia central é: dado o perfil de uma pessoa (sexo, idade, escolaridade, renda, região, raça/cor, religião...), conseguimos prever como ela responderia uma pesquisa de opinião?

Usamos dados da **Pesquisa 04839 do CESOP/UNICAMP** — "Percepção dos Brasileiros sobre Temas Relacionados à Desigualdade" — com 2000 respondentes, e simulamos respostas para duas perguntas:

- **P01**: Em qual local existe mais diferença no tratamento entre pessoas negras e brancas?
- **P06 (A–E)**: Concordância com afirmações sobre desigualdade estrutural (escala Likert 1–5)

As respostas simuladas são comparadas com as reais usando Jensen-Shannon Distance, KL divergence e F1-macro. O projeto também compara o LLM com um Random Forest e aplica SHAP para identificar quais variáveis demográficas mais influenciam as respostas.

## Estrutura

```
ProjetoIADesigualdade/
├── notebooks/
│   └── simulacao_opiniao_publica.ipynb
├── artigo/
│   ├── artigo_sbc.tex
│   ├── referencias.bib
│   └── entropy-27-00923.pdf
├── data/
│   └── raw/04839/
├── results/
└── requirements.txt
```

## Arquivos

- [Notebook principal](notebooks/simulacao_opiniao_publica.ipynb)
- [Artigo SBC (LaTeX)](artigo/artigo_sbc.tex)
- [Artigo de referência](artigo/entropy-27-00923.pdf)
- [Questionário CESOP](data/raw/04839/quest_04839.pdf)
- [Tabela de frequências](data/raw/04839/TF_04839.pdf)

## Como rodar

Desenvolvido para rodar no **Google Colab** sem GPU local ou API keys pagas.

1. Abra `notebooks/simulacao_opiniao_publica.ipynb` no Colab
2. Faça upload do `04839.sav` quando solicitado (disponível no CESOP/UNICAMP)
3. Execute as células em ordem

Para rodar localmente:
```bash
pip install -r requirements.txt
jupyter notebook notebooks/simulacao_opiniao_publica.ipynb
```

## Dados

Pesquisa **04839** do [CESOP/UNICAMP](https://www.cesop.unicamp.br/).

## Autores

- André Moreira Guimarães — 10416590
- Bernardo Souza Oliveira — 10312871
- Henrique Yuji Isogai Yoneoka — 10418153
- João Victor Martins — 10417928
- Leonardo Patriani Cardoso — 10417188

## Referência principal

Miranda, F.; Balbi, P.P. *Simulating Public Opinion: Comparing Distributional and Individual-Level Predictions from LLMs and Random Forests*. Entropy, 27(9), 923, 2025. https://doi.org/10.3390/e27090923
