# Projeto IA — Simulação de Opinião Pública sobre Desigualdade

Trabalho da disciplina de Inteligência Artificial — Curso de Ciência da Computação, Universidade Presbiteriana Mackenzie.

O objetivo é usar um modelo de linguagem (LLM) para simular como brasileiros respondem perguntas sobre desigualdade social, comparando as respostas geradas com os dados reais de uma pesquisa do CESOP/UNICAMP.

## Sobre o projeto

A ideia central é: dado o perfil de uma pessoa (sexo, idade, escolaridade, renda, região, raça/cor, religião...), conseguimos prever como ela responderia uma pesquisa de opinião?

Usamos dados da **Pesquisa 04839 do CESOP/UNICAMP** — "Percepção dos Brasileiros sobre Temas Relacionados à Desigualdade" — com 2000 respondentes, e simulamos respostas para seis questões:

- **P01**: Em qual local existe mais diferença no tratamento entre pessoas negras e brancas?
- **P06 (A–E)**: Concordância com afirmações sobre desigualdade estrutural (escala Likert 1–5)

As respostas simuladas são comparadas com as reais usando Jensen-Shannon Distance, KL Divergence e F1-macro. O projeto também compara o LLM com um Random Forest (validação cruzada 5-fold) e aplica SHAP para identificar quais variáveis demográficas mais influenciam as respostas.

## Resultados principais

| Métrica | LLM (flan-t5-xl) | Random Forest |
|---|---|---|
| Acurácia média | 19,3% | 41,2% |
| F1-macro médio | 16,3% | 18,5% |
| JSD médio | 0,293 | — |

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
│   ├── figures/resultados_figures/
│   └── metrics/resultados_metrics/
└── requirements.txt
```

## Vídeo de apresentação

[![Assistir no YouTube](https://img.shields.io/badge/YouTube-Assistir-red?logo=youtube)](https://www.youtube.com/watch?v=fe0G1uh6r5E)

## Arquivos

- [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/stermiix/ProjetoIADesigualdade/blob/main/notebooks/simulacao_opiniao_publica.ipynb) — Notebook principal
- [Artigo SBC (LaTeX)](artigo/artigo_sbc.tex)
- [Artigo de referência](artigo/entropy-27-00923.pdf)
- [Questionário CESOP](data/raw/04839/quest_04839.pdf)
- [Tabela de frequências](data/raw/04839/TF_04839.pdf)

## Como rodar

Desenvolvido para rodar no **Google Colab** sem GPU local ou API keys pagas. O arquivo de dados já está incluso no repositório.

1. Clique no badge "Abrir no Colab" acima
2. Vá em **Ambiente de execução → Alterar tipo → GPU T4**
3. Execute as células em ordem

Para rodar localmente:
```bash
pip install -r requirements.txt
jupyter notebook notebooks/simulacao_opiniao_publica.ipynb
```

## Autores

- André Moreira Guimarães — 10416590
- Bernardo Souza Oliveira — 10312871
- Henrique Yuji Isogai Yoneoka — 10418153
- João Victor Martins — 10417928
- Leonardo Patriani Cardoso — 10417188

## Referências

- Miranda, F.; Balbi, P.P. *Simulating Public Opinion: Comparing Distributional and Individual-Level Predictions from LLMs and Random Forests*. Entropy, 27(9), 923, 2025. https://doi.org/10.3390/e27090923
- Argyle, L.P. et al. *Out of One, Many: Using Language Models to Simulate Human Samples*. Political Analysis, 31(3), 2023. https://doi.org/10.1017/pan.2023.2
- Park, J.S. et al. *Generative Agents: Interactive Simulacra of Human Behavior*. UIST, 2023. https://doi.org/10.1145/3586183.3606763
- Bail, C.A. *Can Generative AI Improve Social Science?* PNAS, 121(21), 2024. https://doi.org/10.1073/pnas.2314021121
- Törnberg, P. et al. *Simulating Social Media Using Large Language Models*. arXiv:2310.05984, 2023.
- Breiman, L. *Random Forests*. Machine Learning, 45(1), 2001. https://doi.org/10.1023/A:1010933404324
- Lundberg, S.M.; Lee, S. *A Unified Approach to Interpreting Model Predictions*. NeurIPS, 2017.
- Souza, F. et al. *BERTimbau: Pretrained BERT Models for Brazilian Portuguese*. BRACIS, 2020. https://doi.org/10.1007/978-3-030-61377-8_28
- IBGE. *Síntese de Indicadores Sociais 2023*. https://www.ibge.gov.br/
- CESOP/UNICAMP. *Pesquisa 04839 — Percepção dos Brasileiros sobre Desigualdade*, 2023. https://www.cesop.unicamp.br/
