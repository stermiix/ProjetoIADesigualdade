# Percepção dos Brasileiros sobre Desigualdade — Simulação com LLM

Projeto desenvolvido para a disciplina de Inteligência Artificial.  
Simula respostas de questionários do CESOP (Centro de Estudos de Opinião Pública / UNICAMP) usando modelos de linguagem abertos (LLMs), comparando as distribuições simuladas com as respostas reais da pesquisa.

---

## Tema

**Percepção dos Brasileiros sobre Temas Relacionados à Desigualdade**

Baseado no artigo:
> *Simulating Public Opinion: Comparing Distributional and Individual-Level Predictions from LLMs and Random Forests*

---

## Estrutura do Repositório

```
percepcao-desigualdade-brasil/
├── data/
│   ├── raw/             # Dados brutos CESOP (adicionar manualmente)
│   └── processed/       # Dados pré-processados
├── notebooks/
│   └── simulacao_opiniao_publica.ipynb   # Notebook principal (Colab)
├── src/
│   ├── preprocessing.py   # Pré-processamento dos dados
│   ├── llm_simulator.py   # Simulação via LLM
│   └── evaluation.py      # Métricas e explicabilidade
├── results/
│   ├── figures/           # Gráficos gerados
│   └── metrics/           # Métricas salvas (JSON/CSV)
├── artigo/
│   └── artigo_sbc.tex     # Artigo em formato SBC (LaTeX)
├── requirements.txt
└── README.md
```

---

## Metodologia

1. **Dados**: Questionário CESOP sobre percepção de desigualdade
2. **LLM**: Modelos abertos via HuggingFace (sem API key privada) — Mistral, Flan-T5, LLaMA
3. **Simulação**: Mínimo 200 respondentes simulados (≥10% dos dados), 3–5 repetições com validação cruzada
4. **Avaliação**:
   - Acurácia individual (resposta por resposta)
   - Distribuições das respostas (KL divergence, Earth Mover's Distance)
   - Explicabilidade (SHAP, importância de variáveis)
5. **Comparação Extra**: Random Forest vs LLM (conforme artigo de referência)

---

## Como Executar

### Colab (recomendado)

[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SEU_USUARIO/percepcao-desigualdade-brasil/blob/main/notebooks/simulacao_opiniao_publica.ipynb)

### Local

```bash
pip install -r requirements.txt
jupyter notebook notebooks/simulacao_opiniao_publica.ipynb
```

---

## Dados CESOP

Os dados utilizados são provenientes do **CESOP/UNICAMP** — Centro de Estudos de Opinião Pública.  
Por restrições de redistribuição, os dados brutos devem ser obtidos diretamente em: https://www.cesop.unicamp.br/

Coloque os arquivos na pasta `data/raw/`.

---

## Tecnologias

| Ferramenta | Uso |
|---|---|
| `transformers` (HuggingFace) | LLM para simulação de respostas |
| `pandas` / `numpy` | Manipulação de dados |
| `scikit-learn` | Random Forest, métricas, CV |
| `shap` | Explicabilidade |
| `matplotlib` / `seaborn` / `plotly` | Visualizações |
| `scipy` | KL divergence, Earth Mover's Distance |

---

## Autores

- [Bernardo S. Oliveira](mailto:bernar.s.oli@gmail.com)

---

## Referências

- Artigo base: *Simulating Public Opinion: Comparing Distributional and Individual-Level Predictions from LLMs and Random Forests*
- CESOP/UNICAMP: https://www.cesop.unicamp.br/
- Normas SBC: https://www.sbc.org.br/documentos-da-sbc/summary/169-templates-para-artigos-e-capitulos-de-livros/878-modelosparapublicaodeartigos

---

## Vídeo de Apresentação

> Link a ser adicionado após gravação.
