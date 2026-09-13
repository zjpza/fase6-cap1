# 👁️ FarmTech Solutions — PBL Fase 6 | Visão Computacional com YOLO

> **Detecção de objetos personalizada com YOLOv5, comparada com YOLO padrão e CNN treinada do zero.**

---

## 👨‍🎓 Integrantes

| Nome                               | RM        | GitHub                                                           |
| ---------------------------------- | --------- | ---------------------------------------------------------------- |
| Henrique Sanches Silva             | RM 570527 | [@HenriqueSanchesSilva](https://github.com/HenriqueSanchesSilva) |
| João Pedro Zavanela Andreu         | RM 570231 | [@zjpza](https://github.com/zjpza)                               |
| Kayck Gabriel Evangelista da Silva | RM 572331 | [@Kayckxz](https://github.com/Kayckxz)                           |
| Luis Henrique Laurentino Boschi    | RM 571352 | [@lhboschi](https://github.com/lhboschi)                         |
| Patrick Borges de Melo             | RM 574030 | [@Trickmelo](https://github.com/Trickmelo)                       |

**Tutora:** Sabrina Otoni
**Coordenador:** André Godoi

> **FIAP — Inteligência Artificial | Turma: 1TIAOB-2026**

---

## 📜 Visão Geral

A FarmTech Solutions expandiu sua carteira de serviços de IA para além do agronegócio — saúde animal, segurança patrimonial, controle de acessos, análise de documentos e **visão computacional**. Neste projeto, o time demonstra a um cliente fictício como funciona um sistema de detecção de objetos na prática.

Este repositório contempla as **duas entregas obrigatórias** da Fase 6:

| Entrega       | Tema                                                                                                                       | Onde está                  |
| ------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------- |
| **Entrega 1** | Visão Computacional — dataset customizado, rotulação, treinamento/validação/teste com YOLOv5 e comparação de épocas        | [`notebooks/`](notebooks/)  |
| **Entrega 2** | Comparação de abordagens — YOLO customizada vs. YOLO tradicional vs. CNN treinada do zero                                   | [`notebooks/`](notebooks/) |

O detalhamento técnico completo (código, passo a passo, gráficos, achados e conclusões) está no **Jupyter Notebook**. Este README é apenas uma introdução que conduz o leitor até ele.

---

## 🎯 Entrega 1 — Detecção de objetos com YOLOv5

> ⚠️ Documentação em construção — acompanhe o progresso pelas [issues](../../issues).

- Dataset próprio com **2 classes** (objeto A e objeto B, bem distintos): 80 imagens no total, divididas em treino (32/classe), validação (4/classe) e teste (4/classe);
- Rotulação no [Make Sense AI](https://www.makesense.ai/) e organização no Google Drive;
- Colab conectado ao Drive executando **treino, validação e teste**, com passo a passo em markdown;
- **Duas simulações de treinamento** com quantidades diferentes de épocas, comparando acurácia, erro e desempenho;
- Prints das imagens de teste processadas pelo modelo e conclusões sobre os resultados (`yolov5/runs/detect/expX`).

### 📒 Notebook

➡️ `notebooks/JoaoPedroZavanelaAndreu_rm570231_pbl_fase6.ipynb` *(em construção)*

### 🎥 Vídeo demonstrativo

🔗 Link em breve (YouTube — não listado).

---

## 🎯 Entrega 2 — Comparação de abordagens

> ⚠️ Documentação em construção — acompanhe o progresso pelas [issues](../../issues).

A partir da mesma base da Entrega 1, comparamos criticamente três abordagens em termos de **facilidade de uso/integração, precisão, tempo de treinamento e tempo de inferência**:

1. **YOLO customizada** (Entrega 1);
2. **YOLO tradicional** (pré-treinada);
3. **CNN treinada do zero** para classificação das imagens.

---

## 🚀 Ir Além *(opcional — não vale nota)*

- **Opção 1 — ESP32-CAM:** coleta de imagens em tempo real via Wi-Fi e detecção com o `best.pt` gerado na Entrega 1;
- **Opção 2 — Transfer Learning & Fine Tuning:** rede pré-treinada na ImageNet + segmentação com máscara antes da classificação.

---

## 📁 Estrutura do repositório

```
fase6-cap1/
├── notebooks/   # Notebooks Jupyter das entregas
├── data/        # Bases e artefatos de dados
├── assets/      # Imagens, gráficos e figuras do README
├── docs/        # Documentação complementar
└── README.md
```