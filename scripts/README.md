# scripts

Scripts auxiliares para tarefas específicas do projeto.

Para a Fase 6, os principais "scripts" estão **encapsulados como células do notebook** em `src/VitorioStevanattoCompriPaciulo_rm567895_pbl_fase6.ipynb`. As principais rotinas auxiliares são:

- **Download e organização do dataset** — coleta de imagens de gatos e cachorros e divisão em `train/val/test` (32/4/4 por classe).
- **Auto-rotulação por pseudo-labeling** — uso da YOLOv8 pré-treinada na COCO para gerar bounding boxes e converter as classes `cat` (15) e `dog` (16) para os IDs do projeto (`gato=0`, `cachorro=1`).
- **Geração do `data.yaml`** da YOLO.
- **Treino e avaliação** das duas configurações da YOLO customizada (20 e 50 épocas).
- **Inferência da YOLO tradicional COCO** sobre o conjunto de teste.
- **Treino e avaliação** da CNN do zero em PyTorch.
- **Geração da tabela comparativa** das três abordagens.

Esta pasta foi mantida vazia (com este README explicativo) para preservar a aderência ao template oficial `agodoi/templateFiapVfinal`. Caso, em fases futuras, seja necessário extrair rotinas específicas como scripts `.py` independentes, eles serão adicionados aqui.
