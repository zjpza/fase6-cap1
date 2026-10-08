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

| Entrega       | Tema                                                                                        | Onde está                                                                               |
| ------------- | ------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| **Entrega 1** | Visão Computacional — dataset customizado, rotulação, treinamento/validação/teste com YOLOv5 | seções 2 a 7 do [notebook](notebooks/JoaoPedroZavanelaAndreu_rm570231_pbl_fase6.ipynb)  |
| **Entrega 2** | Comparação de abordagens — YOLO customizada vs. YOLO tradicional vs. CNN treinada do zero     | seções 7, 9 e 10 do mesmo notebook (issues [#7](issues/7) e [#8](issues/8)) |

O detalhamento técnico completo — código executado, saídas, gráficos, achados, limitações e conclusões — está no **notebook**. Este README é a porta de entrada.

---

## 📒 Notebook e como executar

- **Arquivo:** [`notebooks/JoaoPedroZavanelaAndreu_rm570231_pbl_fase6.ipynb`](notebooks/JoaoPedroZavanelaAndreu_rm570231_pbl_fase6.ipynb)
- **Abrir no Colab:** [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/zjpza/fase6-cap1/blob/main/notebooks/JoaoPedroZavanelaAndreu_rm570231_pbl_fase6.ipynb)

Passo a passo para reproduzir:

1. Abra o notebook no Colab pelo badge acima (o repositório é público).
2. _Ambiente de execução → Alterar tipo de ambiente_ → **T4 GPU**.
3. _Ambiente de execução → Reiniciar e executar tudo_. O notebook clona o YOLOv5, obtém o dataset e roda treino, validação, teste e inferência de ponta a ponta — cerca de 6 minutos na T4.
4. Na primeira execução o Colab pede autorização de leitura do Drive. O dataset está numa **pasta pública** do Drive do grupo (164 arquivos, entre imagens, rotulações e metadados); o `gdown` não dá conta porque o Google limita a 50 arquivos por pasta, então o notebook baixa pela API do Drive.

Sem GPU o treino de 100 épocas não é viável.

---

## 🎯 Entrega 1 — Detecção de objetos com YOLOv5

| Meta do enunciado                                                                       | Status                                                                                                          |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| 40 imagens do objeto A + 40 do objeto B (80 no total)                                   | ✅ `vaca` (A) e `caminhao` (B), 40 de cada                                                                       |
| 32 treino / 4 validação / 4 teste **por classe**                                        | ✅ 64 / 8 / 8 no total                                                                                           |
| Imagens organizadas no Google Drive, separadas em treino/validação/teste                | ✅ pasta pública do grupo                                                                                        |
| Rotulação das imagens (Make Sense IA) salva no Drive                                    | ✅ formato YOLO `.txt`; a procedência de cada imagem está em `origem_vaca.csv` / `origem_caminhao.csv`           |
| Colab conectado ao Drive com **treino, validação e teste** e passo a passo em markdown  | ✅ seções 2 a 6 do notebook                                                                                      |
| Prints das imagens de teste processadas + conclusões sobre validação e testes           | ✅ seção 7 (métricas por classe, gráficos, matriz de confusão e prints das detecções)                            |
| **Duas simulações** de treino com nº de épocas bem diferentes (ex.: 30 e 60)            | ✅ seção 8 — 30 e 60 épocas, com tabela comparativa de métricas, perdas e tempo |

Números desta execução (T4, 100 épocas): no **teste**, mAP@0.5 **0,864** e recall **0,894**; no dataset, **129 caixas de vaca e 44 de caminhão** em 80 imagens. Com 30 épocas o melhor mAP@0.5 na validação foi 0,836, com 60 foi 0,945 e com 100 foi 0,995.

---

## 🎯 Entrega 2 — Comparação de abordagens

Critérios do enunciado: **facilidade de uso/integração, precisão do modelo, tempo de treinamento/customização e tempo de inferência**.

| Abordagem                                     | Status                                                                                        |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| **YOLO customizada** (Entrega 1)              | ✅ treinada e avaliada (seção 7)                                                               |
| **YOLO tradicional** (COCO, sem treinar)      | ✅ baseline rodado nas mesmas imagens de teste, com comparação qualitativa na seção 7          |
| **CNN treinada do zero** (classificação A/B)  | ✅ seção 9 — acurácia 1,000 no teste (8/8) e 0,875 na validação                |
| Tabela consolidada dos 4 critérios            | ✅ seção 10 — facilidade, precisão, tempo de treino e tempo de inferência       |

---

## 🗺️ Roadmap de execução

Ordem de execução das [issues](issues), com dependências (as prioridades também estão como labels: `P1` → `P5`):

| Ordem | Issue                                                          | Depende de     | Status                                    |
| ----- | -------------------------------------------------------------- | -------------- | ----------------------------------------- |
| 1º    | [#1 Dataset — objetos A e B](issues/1)                    | —              | ✅ concluída                               |
| 2º    | [#2 Rotulação no Make Sense IA](issues/2)                 | #1             | ✅ concluída                               |
| 3º    | [#3 Colab YOLOv5 — treino/val/teste](issues/3)            | #2             | ✅ executada (notebook acima)              |
| 4º    | [#4 Simulações 30 vs 60 épocas](issues/4)                 | #3             | ✅ executada (seção 8)                     |
| 5º    | [#5 Resultados — prints e conclusões](issues/5)           | #4             | ✅ seção 7 do notebook                     |
| 6º    | [#6 YOLO tradicional](issues/6)                           | #1             | ✅ baseline, contagens e tempos (seções 7 e 10) |
| 7º    | [#7 CNN treinada do zero](issues/7)                       | #1             | ✅ executada (seção 9)                     |
| 8º    | [#8 Comparação crítica das 3 abordagens](issues/8)        | #3–#7          | ✅ seção 10                                |
| 9º    | [#9 README, notebook e vídeo final](issues/9)             | #1–#8          | 🔸 documentação pronta; falta publicar o vídeo |
| Opc.  | [#10 Ir Além — ESP32-CAM](issues/10)                      | #3 (`best.pt`) | ➖ não iniciada                            |
| Opc.  | [#11 Ir Além — Transfer Learning](issues/11)              | #7             | ✅ executada no notebook opcional          |

---

## 🚀 Ir Além _(opcional — não vale nota)_

**Opção 2 — Transfer Learning, Fine Tuning e segmentação** (a opção escolhida pelo grupo):

- **Notebook:** [`notebooks/IrAlem_TransferLearning.ipynb`](notebooks/IrAlem_TransferLearning.ipynb) — [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/zjpza/fase6-cap1/blob/main/notebooks/IrAlem_TransferLearning.ipynb)
- **O que ele testa:** (1) uma rede grande pré-treinada na ImageNet (*MobileNetV2*, com fine tuning das últimas 30 camadas) contra a CNN treinada do zero da Entrega 2; (2) se **pré-segmentar** o objeto — recortando o fundo com uma máscara — facilita a classificação.
- **Como as máscaras são geradas:** segmentação automática com um YOLO pré-treinado no COCO (`cow` = 19 e `truck` = 7), sem nenhum treino nosso; a imagem recortada mantém só o objeto, com fundo preto.
- **Evidências no notebook:** figura original/máscara/recortada, curvas de treino, matrizes de confusão, tabela comparativa dos 4 treinos e a figura de arquitetura da solução.
- **Resultados:** a MobileNetV2 pré-treinada acertou **8/8 no teste** nas duas versões da base, contra **7/8** da CNN do zero — com **2,3 M de parâmetros contra 11,2 M**. Recortar o fundo não mudou a acurácia nesta base, mas cortou o tempo de treino da CNN do zero pela metade (1,06 → 0,56 min). A segmentação automática achou máscara em **todas as 80 imagens** (cobertura média de 24,7%).
- 🎥 **Vídeo demonstrativo:** pendente de gravação e publicação no YouTube como **não listado**. O roteiro de gravação está em [`docs/VIDEO_ROTEIRO.md`](docs/VIDEO_ROTEIRO.md).

A **Opção 1** (ESP32-CAM/webcam com detecção em tempo real) ficou de fora nesta fase.

---

## 📁 Estrutura do repositório

```
fase6-cap1/
├── notebooks/   # Notebook das entregas (executado, com saídas salvas)
├── data/        # Artefatos de dados
├── assets/      # Imagens, gráficos e figuras do README
├── docs/        # Documentação complementar
└── README.md
```

O dataset não é versionado (`dataset/` está no `.gitignore`): as 80 imagens e as rotulações ficam na pasta pública do Drive do grupo e são baixadas pelo próprio notebook, o que mantém o repositório leve e sem imagens de terceiros.

---

## 🎥 Vídeo demonstrativo

O único item de implementação ainda pendente é gravar e publicar o vídeo de até 5 minutos. Para não registrar um link fictício, o README será atualizado com a URL do YouTube após o upload. Use o roteiro em [`docs/VIDEO_ROTEIRO.md`](docs/VIDEO_ROTEIRO.md), publique como **não listado** e substitua este bloco pelo link final.
