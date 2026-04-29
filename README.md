# FIAP - Faculdade de Informática e Administração Paulista

<p align="center">
<a href="https://www.fiap.com.br/"><img src="assets/logo-fiap.png" alt="FIAP - Faculdade de Informática e Admnistração Paulista" border="0" width=40% height=40%></a>
</p>

<br>

# Cap 1 — O Despertar da Rede Neural

## Grupo 45

## 👨‍🎓 Integrantes:
Vitorio Stevanatto Compri Paciulo — RM 567895</a>

## Link do vídeo:

## 📜 Descrição

Este projeto desenvolve um sistema de **visão computacional** para um cliente fictício do portfólio da **FarmTech Solutions**, demonstrando o uso de **Redes Neurais Convolucionais** aplicadas à detecção e classificação de objetos. O cenário escolhido foi a **distinção entre gatos e cachorros**, dois animais que coabitam em fazendas e residências rurais e cuja identificação automática tem aplicações práticas em manejo, contagem populacional, monitoramento por câmeras de segurança e bem-estar animal.

A solução é estruturada em **duas entregas** conforme o enunciado da disciplina. Na **Entrega 1**, é construído um pipeline de detecção customizada com **YOLOv8**: monta-se um dataset autoral com **40 imagens de gatos** e **40 de cachorros** (32 treino, 4 validação e 4 teste por classe), realiza-se a rotulagem por meio de **pseudo-labeling assistido pela YOLOv8 pré-treinada na base COCO** (técnica amplamente utilizada em pipelines reais de visão computacional quando há um modelo *teacher* confiável disponível) e treina-se a YOLO em duas configurações distintas (20 e 50 épocas) para comparar o impacto do tempo de treino na qualidade da detecção. A justificativa metodológica para a substituição do *Make Sense IA* pelo pseudo-labeling está documentada em detalhes no notebook.

Na **Entrega 2**, são implementadas duas abordagens adicionais para fins comparativos. A primeira utiliza a **YOLOv8 tradicional**, sem qualquer fine-tuning, aplicando os pesos da COCO diretamente sobre o conjunto de teste — útil para mensurar a qualidade do modelo *teacher* e o ganho relativo do treino customizado. A segunda implementa uma **CNN do zero** em PyTorch (3 blocos convolucionais + classificador denso), treinada por 30 épocas como classificador binário. Os resultados das três abordagens são consolidados em uma tabela comparativa que avalia **facilidade de uso, precisão, tempo de treino e tempo de inferência**, evidenciando os trade-offs práticos entre transferência de aprendizado em modelos modernos e o treinamento de redes do zero com poucos dados.

Todo o pipeline é executável de ponta a ponta no Google Colab com GPU T4 em aproximadamente 10 minutos, e os resultados (pesos treinados, gráficos, predições visuais e métricas) são persistidos no Google Drive do usuário durante a execução.

## 📁 Estrutura de pastas

Dentre os arquivos e pastas presentes na raiz do projeto, definem-se:

- <b>.github</b>: Nesta pasta ficarão os arquivos de configuração específicos do GitHub que ajudam a gerenciar e automatizar processos no repositório.

- <b>assets</b>: aqui estão os arquivos relacionados a elementos não-estruturados deste repositório, como imagens (logo da FIAP e demais figuras de apoio).

- <b>config</b>: Posicione aqui arquivos de configuração que são usados para definir parâmetros e ajustes do projeto (ex.: `data.yaml` da YOLO, hiperparâmetros).

- <b>document</b>: aqui estão todos os documentos do projeto que as atividades poderão pedir. Na subpasta "other", adicione documentos complementares e menos importantes.

- <b>scripts</b>: Posicione aqui scripts auxiliares para tarefas específicas do seu projeto (ex.: download do dataset, conversão COCO→YOLO, geração de relatórios).

- <b>src</b>: Todo o código fonte criado para o desenvolvimento do projeto. Aqui está o notebook principal **`VitorioStevanattoCompriPaciulo_rm567895_pbl_fase6.ipynb`** com o pipeline completo da Fase 6.

- <b>README.md</b>: arquivo que serve como guia e explicação geral sobre o projeto (o mesmo que você está lendo agora).

## 🔧 Como executar o código

**Pré-requisitos:** conta Google (para usar o Google Colab e o Google Drive). Não é necessária instalação local — todas as dependências (`ultralytics`, `torch`, `torchvision`, `opencv-python`, `matplotlib`, `scikit-learn`, `Pillow`) são instaladas automaticamente pelo notebook na primeira célula.

**Passo a passo:**

1. **Abrir no Colab.** Clique no badge "Open in Colab" presente na primeira célula do notebook em [`src/VitorioStevanattoCompriPaciulo_rm567895_pbl_fase6.ipynb`](src/VitorioStevanattoCompriPaciulo_rm567895_pbl_fase6.ipynb), ou acesse diretamente: [Abrir no Colab](https://colab.research.google.com/github/viscp1011/pbl-fase6-grupo45/blob/main/src/VitorioStevanattoCompriPaciulo_rm567895_pbl_fase6.ipynb).

2. **Selecionar GPU.** No menu do Colab: *Ambiente de execução → Alterar tipo de ambiente de execução → GPU T4*.

3. **Executar tudo.** *Ambiente de execução → Executar tudo* (ou Ctrl+F9). O Colab pedirá autorização para montar o Google Drive — autorize, pois os artefatos (pesos, gráficos, predições) são gravados em `/content/drive/MyDrive/pbl_fase6/`.

4. **Acompanhar a execução.** O pipeline executa em ~10 minutos na GPU T4 e segue a ordem:
   - **Entrega 1** — Setup → Download de imagens → Organização do dataset (32/4/4 por classe) → Auto-rotulação com YOLO+COCO → Treino YOLO 20 épocas → Treino YOLO 50 épocas → Análise crítica.
   - **Entrega 2** — YOLO tradicional COCO sobre o conjunto de teste → CNN do zero (3 blocos conv + denso, 30 épocas) → Tabela comparativa final.

5. **Ver os resultados.** Os outputs ficam visíveis nas células do próprio notebook (gráficos de loss/mAP, matriz de confusão, predições com bounding boxes) e também no Drive em `MyDrive/pbl_fase6/`.

## 🗃 Histórico de lançamentos

* 1.0.0 - 29/04/2026 — versão final entregue na FIAP, com pipeline completo, notebook executado no Colab T4 e estrutura adequada ao template oficial `agodoi/templateFiapVfinal`.
* 0.2.0 - 29/04/2026 — adoção do *caminho C* (pseudo-labeling YOLO+COCO em substituição ao *Make Sense IA*) e execução completa no Colab.
* 0.1.0 - 29/04/2026 — criação do repositório, README inicial e estrutura do notebook.

## 📋 Licença

<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"><p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/agodoi/template">MODELO GIT FIAP</a> por <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://fiap.com.br">Fiap</a> está licenciado sobre <a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Attribution 4.0 International</a>.</p>
