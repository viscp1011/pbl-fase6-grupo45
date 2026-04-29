# 🧠 PBL Fase 6 — O Despertar da Rede Neural

**Aluno:** Vitorio Stevanatto Compri Paciulo  
**RM:** 567895  
**Grupo:** 45  
**Disciplina:** Redes Neurais — FIAP  
**Tema escolhido:** Classificação e detecção de **gatos** vs. **cachorros**

---

## 📌 Sobre o projeto

Este projeto desenvolve um sistema de visão computacional para um cliente fictício do portfólio da **FarmTech Solutions**, demonstrando o potencial das redes neurais aplicadas à detecção e classificação de objetos. Foram implementadas e comparadas três abordagens distintas:

1. **YOLOv8 customizada** — treinada a partir de um dataset autoral rotulado no Make Sense IA;
2. **YOLOv8 tradicional** — modelo pré-treinado na base COCO, aplicado sem retreino;
3. **CNN do zero** — uma rede convolucional simples (mini-VGG) treinada para classificação binária.

**Classes escolhidas:** `gato` (classe A) e `cachorro` (classe B). Pares visualmente distintos garantem boa convergência mesmo com dataset reduzido (40 imagens por classe).

---

## 🗂️ Estrutura do dataset

| Split | Imagens por classe | Total |
|-------|--------------------|-------|
| Treino | 32 | 64 |
| Validação | 4 | 8 |
| Teste | 4 | 8 |

Imagens organizadas no Google Drive em `dataset/images/{train,val,test}` e rótulos em `dataset/labels/{train,val}` (formato YOLO, exportado do **Make Sense IA**).

---

## 🚀 Como executar

1. Abra o notebook no Colab pelo link abaixo;
2. Conecte seu Google Drive quando solicitado;
3. Execute as células em ordem;
4. Pause na seção 2.2 para a etapa de rotulação manual no Make Sense IA;
5. Continue a execução até o final.

---

## 🔗 Links

- 📓 **Notebook Colab/Jupyter:** [VitorioStevanattoCompriPaciulo_rm567895_pbl_fase6.ipynb](./VitorioStevanattoCompriPaciulo_rm567895_pbl_fase6.ipynb)
- 🎥 **Vídeo demonstrativo (YouTube — não listado):** _link a inserir após upload_

---

## 📊 Resultados resumidos

- A **YOLOv8 customizada** foi treinada em duas simulações (20 e 50 épocas) para analisar o impacto do número de épocas em dataset pequeno;
- A **YOLOv8 tradicional (COCO)** apresentou alta precisão imediata, pois `cat` e `dog` já fazem parte das 80 classes nativas;
- A **CNN do zero** serviu como baseline didático de classificação, evidenciando os limites do treino do zero com poucos dados.

A tabela comparativa completa (facilidade de uso, precisão, tempo de treino e tempo de inferência) está disponível no notebook.

---

## 🛠️ Stack utilizada

Python · Ultralytics YOLOv8 · PyTorch · Torchvision · Google Colab · Google Drive · Make Sense IA · icrawler · Matplotlib · Pandas

---

## 👥 Grupo

**Grupo 45** — FIAP On  
- Vitorio Stevanatto Compri Paciulo (RM 567895)
