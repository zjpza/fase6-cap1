# Roteiro do vídeo demonstrativo

Duração máxima: **5 minutos**. Publicar no YouTube como **não listado**.

## Antes de gravar

- Abrir o README e o notebook principal no Colab.
- Confirmar que o notebook está com as saídas salvas; não é necessário treinar novamente durante a gravação.
- Separar as imagens de teste processadas em `runs/detect/custom_test/` e, se desejado, a figura de arquitetura do notebook opcional.
- Gravar a tela com o áudio do apresentador. Evitar exibir tokens, dados pessoais ou a pasta privada do Drive.

## Roteiro sugerido

| Tempo | Tela e fala |
| --- | --- |
| 0:00–0:20 | Apresentar a FarmTech Solutions, o objetivo e as classes `vaca` e `caminhao`. Explicar que o detector retorna classe e caixa delimitadora. |
| 0:20–0:50 | Mostrar o README, o notebook nomeado conforme o barema e o botão **Open in Colab**. Informar que a execução usa GPU e que o dataset é baixado do Drive público do grupo. |
| 0:50–1:20 | Mostrar no notebook a estrutura `images/` e `labels/`, a divisão 32/4/4 por classe e uma amostra com as caixas anotadas. |
| 1:20–2:10 | Mostrar duas imagens de teste processadas pelo YOLO customizado, uma de cada classe. Apontar as caixas, nomes e confianças exibidos. |
| 2:10–2:45 | Mostrar as curvas, a matriz de confusão e a tabela de métricas. Informar os resultados de teste: mAP@0.5 **0,864**, recall **0,894** e mAP@0.5:0.95 **0,581**. |
| 2:45–3:20 | Mostrar a comparação de 30, 60 e 100 épocas. Explicar o trade-off entre tempo de treino e melhora de validação, sem afirmar que a base pequena garante generalização. |
| 3:20–4:00 | Mostrar a YOLO tradicional COCO e a CNN do zero. Explicar a diferença: YOLO localiza objetos; CNN classifica a imagem inteira. Apresentar a tabela consolidada de facilidade, precisão, treino e inferência. |
| 4:00–4:35 | Se apresentar o item opcional, abrir `IrAlem_TransferLearning.ipynb` e mostrar a sequência original → máscara → recorte, além do resultado da MobileNetV2. Identificar explicitamente essa parte como opcional. |
| 4:35–5:00 | Concluir: a YOLO customizada é a escolha para localização/contagem; a CNN é mais simples para classificação; a YOLO COCO serve como baseline, mas não substitui a customização. Mostrar o link do GitHub na tela. |

## Checklist de publicação

- [ ] Conferir duração menor ou igual a 5 minutos.
- [ ] Publicar como **não listado**.
- [ ] Testar o link em uma janela anônima.
- [ ] Substituir os dois avisos de vídeo no `README.md` pela mesma URL do YouTube.
- [ ] Enviar o link do GitHub e o link do vídeo pelo portal da FIAP.
- [ ] Depois do prazo definido pela turma, não fazer novos commits no repositório.
