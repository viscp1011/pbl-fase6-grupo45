# config

Arquivos de configuração do projeto.

Na Fase 6, os principais parâmetros de configuração ficam **dentro do próprio notebook** em `src/VitorioStevanattoCompriPaciulo_rm567895_pbl_fase6.ipynb`, especificamente:

- **`data.yaml`** da YOLO — gerado dinamicamente pelo notebook na seção *Setup do dataset*, contendo os caminhos para `train/`, `val/`, `test/` e os nomes das classes (`gato`, `cachorro`).
- **Hiperparâmetros de treino YOLO** — épocas (20 e 50), `imgsz=640`, `batch=16`, otimizador padrão da Ultralytics.
- **Hiperparâmetros da CNN do zero** — `lr=1e-3`, `batch=16`, 30 épocas, otimizador Adam, `CrossEntropyLoss`.
- **Mapeamento COCO → classes do projeto** — `{15: 0, 16: 1}` (cat → gato, dog → cachorro).

Caso o leitor queira reproduzir com outros valores, basta ajustá-los nas células correspondentes do notebook.
