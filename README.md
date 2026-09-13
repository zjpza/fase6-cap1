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

## 🗺️ Roadmap de execução

Ordem de execução das [issues](../../issues), com dependências (as prioridades também estão como labels: `P1` → `P5`):

| Ordem | Issue                                                                        | Depende de      | Paralelizável?                             |
| ----- | ---------------------------------------------------------------------------- | --------------- | ------------------------------------------ |
| 1º    | [#1 Dataset — objetos A e B](../../issues/1)                                 | —               | Primeiro passo, desbloqueia tudo           |
| 2º    | [#2 Rotulação no Make Sense IA](../../issues/2)                               | #1              | Junto com #6 e #7                           |
| 3º    | [#3 Colab YOLOv5 — treino/val/teste](../../issues/3)                          | #2              | Caminho principal da Entrega 1             |
| 4º    | [#4 Simulações 30 vs 60 épocas](../../issues/4)                              | #3              | Caminho principal da Entrega 1             |
| 5º    | [#5 Resultados — prints e conclusões](../../issues/5)                        | #4              | Caminho principal da Entrega 1             |
| 6º    | [#6 YOLO tradicional](../../issues/6)                                        | #1              | Pode rodar paralelo a #2–#5                |
| 7º    | [#7 CNN treinada do zero](../../issues/7)                                     | #1              | Pode rodar paralelo a #2–#6                |
| 8º    | [#8 Comparação crítica das 3 abordagens](../../issues/8)                      | #3–#7           | Consolida a Entrega 2                       |
| 9º    | [#9 README, notebook e vídeo final](../../issues/9)                          | #1–#8           | Última antes do freeze da entrega          |
| Opc.  | [#10 Ir Além — ESP32-CAM](../../issues/10)                                    | #3 (`best.pt`)  | Paralelo, após entregas obrigatórias       |
| Opc.  | [#11 Ir Além — Transfer Learning](../../issues/11)                            | #7              | Paralelo, após entregas obrigatórias       |

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