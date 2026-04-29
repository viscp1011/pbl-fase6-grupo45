# 🎬 Roteiro detalhado do vídeo de entrega — PBL Fase 6

> **Aluno:** Vitorio Stevanatto Compri Paciulo — RM 567895
> **Grupo:** 45
> **Disciplina:** Cap 1 — O Despertar da Rede Neural
> **Duração-alvo:** 4'30" a 5'00" (limite máximo da FIAP é 5 minutos)
> **Plataforma:** YouTube como "Não listado"

---

## ⚙️ Antes de começar a gravar — checklist técnico

1. **Software de gravação:** OBS Studio (gratuito) ou o gravador nativo do Windows (Win+G → Captura de tela). Se usar OBS, configure cena com:
   - Captura de tela (a tela inteira ou janela específica do navegador)
   - Captura de áudio do microfone
   - Resolução: 1080p, 30 fps
2. **Microfone:** teste o áudio antes — fale uma frase, grave 10 segundos, ouça. Garanta que não há eco ou ruído de fundo.
3. **Abas a deixar pré-abertas no navegador (na ordem de uso):**
   - **Aba 1:** Repositório no GitHub — `https://github.com/viscp1011/pbl-fase6-grupo45`
   - **Aba 2:** Notebook executado no GitHub — `https://github.com/viscp1011/pbl-fase6-grupo45/blob/main/src/VitorioStevanattoCompriPaciulo_rm567895_pbl_fase6.ipynb`
   - **Aba 3 (opcional):** Notebook no Colab — `https://colab.research.google.com/github/viscp1011/pbl-fase6-grupo45/blob/main/src/VitorioStevanattoCompriPaciulo_rm567895_pbl_fase6.ipynb`
4. **Dica:** abra o notebook no GitHub antes de gravar e dê **Ctrl+End** para garantir que o navegador já carregou todas as imagens e gráficos (eles demoram alguns segundos para renderizar).
5. **Faça uma rodada de prática lendo o roteiro em voz alta com cronômetro** — provavelmente vai precisar ajustar o ritmo na primeira tentativa.

---

## 🎬 Roteiro cena a cena

### CENA 1 — Abertura e apresentação (0:00 – 0:25)

**🖥️ Tela:** página inicial do repositório no GitHub (aba 1) — `pbl-fase6-grupo45` mostrando o cabeçalho FIAP, logo, título do projeto e a estrutura de pastas.

**🎤 Fala (sugestão — adapte com suas palavras):**

> "Olá, professor! Meu nome é **Vitorio Stevanatto Compri Paciulo**, RM **567895**, grupo **45**. Este é o entregável da Fase 6 do projeto da FIAP, **Cap 1 — O Despertar da Rede Neural**. Nos próximos minutos vou apresentar o sistema de visão computacional que desenvolvi, mostrar os resultados das três abordagens de redes neurais comparadas, e explicar as decisões metodológicas que tomei ao longo do projeto."

**🎯 Ação na tela:** ficar parado mostrando a tela do repositório por uns 5 segundos para o avaliador ler o título e seu nome no canto superior direito.

---

### CENA 2 — Tour pelo repositório e estrutura template FIAP (0:25 – 1:00)

**🖥️ Tela:** continue na página inicial do GitHub. Role devagar para mostrar:
- A lista de pastas (`assets/`, `config/`, `document/`, `scripts/`, `src/`)
- O README com logo da FIAP, integrantes e professores
- Continue rolando até a seção "Estrutura de pastas"

**🎤 Fala:**

> "O repositório foi organizado seguindo o **template oficial da FIAP**, o `agodoi/templateFiapVfinal`. Na raiz vocês veem a separação por responsabilidade: `assets` com a logo institucional, `config` documentando os hiperparâmetros do projeto, `document` com a documentação complementar — incluindo este roteiro de vídeo —, `scripts` descrevendo as rotinas auxiliares, e `src` onde está o notebook principal com todo o pipeline executado. O README cumpre o papel de guia geral, identificando aluno, professores, descrição do projeto, instruções de execução e histórico de lançamentos."

**🎯 Ação na tela:** clique uma vez na pasta `src/` para mostrar que tem o notebook lá dentro, depois volte para a raiz com o botão "voltar" do navegador.

---

### CENA 3 — Escolha das classes e decisão metodológica (1:00 – 1:30)

**🖥️ Tela:** abra a aba 2 (notebook no GitHub) e role até a primeira célula de markdown — a introdução. Depois role até a seção **2.2 Auto-rotulação assistida (pseudo-labeling com YOLO+COCO)**.

**🎤 Fala:**

> "Para o sistema, escolhi classificar e detectar **gatos versus cachorros** — dois animais que coabitam ambientes rurais e residenciais, e cuja distinção automática tem aplicação prática em manejo, contagem populacional e monitoramento por câmeras. O dataset é autoral: **40 imagens de gatos e 40 de cachorros**, divididas em 32 de treino, 4 de validação e 4 de teste por classe, conforme o enunciado. A decisão metodológica mais importante do projeto está aqui: em vez de rotular manualmente as 64 imagens de treino e validação no Make Sense IA, optei pela técnica de **pseudo-labeling**, onde a YOLOv8 pré-treinada na base COCO atua como modelo *teacher* gerando os bounding boxes automaticamente. É uma técnica amplamente utilizada em pipelines reais quando há um modelo confiável disponível, e está documentada em detalhes no notebook."

**🎯 Ação na tela:** pause mostrando o bloco "Justificativa metodológica" do notebook por 2-3 segundos para o avaliador ler.

---

### CENA 4 — Entrega 1: dataset, auto-rotulação e YOLO customizada (1:30 – 3:00)

**🖥️ Tela:** continue no notebook, role pelas seções na ordem:
1. **2.1 — Dataset autoral** (mostre as imagens baixadas se aparecerem como output)
2. **2.2 — Auto-rotulação** (mostre alguns bounding boxes gerados, se houver visualização)
3. **2.3 — Treinamento da YOLO 20 épocas** (mostre o gráfico de loss / mAP)
4. **2.4 — Treinamento da YOLO 50 épocas** (mostre os mesmos gráficos)

**🎤 Fala:**

> "A primeira entrega é o pipeline de detecção customizada. Comecei coletando as imagens autorais e organizando a estrutura de pastas que a YOLO espera. Em seguida, executei a auto-rotulação: a YOLO COCO percorre cada imagem, identifica as instâncias de gato — classe 15 da COCO — e cachorro — classe 16 —, e converte para os IDs do meu projeto: gato é zero, cachorro é um. Os arquivos `.txt` no formato YOLO são gerados em segundos. Com o dataset rotulado, treinei a YOLOv8 em **duas configurações**. A primeira com **20 épocas** levou cerca de **64 segundos** na GPU T4 do Colab e atingiu **mAP@0.5 de 99,5%**. A segunda, com **50 épocas**, levou **116 segundos** e ficou também em **99,5%** — ou seja, o modelo já saturou a capacidade do dataset por volta da 20ª época, o que é um insight importante: mais épocas nem sempre se traduzem em ganho real, e o tempo extra de treino não compensou."

**🎯 Ação na tela:** role devagar pelas duas células de treino, mostrando claramente os gráficos de **train/box_loss**, **train/cls_loss**, **metrics/mAP50** e a **matriz de confusão** se aparecer.

---

### CENA 5 — Entrega 2: YOLO COCO, CNN do zero e tabela comparativa (3:00 – 4:15)

**🖥️ Tela:** role no notebook até **Entrega 2 — YOLO tradicional COCO**, depois **3.2 CNN do zero**, e finalmente **3.3 Tabela comparativa**.

**🎤 Fala:**

> "Na segunda entrega, comparei minha YOLO customizada com duas alternativas. Primeiro, a **YOLO tradicional**: usei os pesos da COCO sem nenhum fine-tuning, aplicados diretamente sobre o conjunto de teste. Isso serve para mensurar o ganho do treino customizado e a qualidade do *teacher* que usei na auto-rotulação. O tempo de inferência ficou em **148,6 milissegundos por imagem** na T4. Em seguida, implementei uma **CNN do zero** em PyTorch — três blocos convolucionais e um classificador denso, treinada por 30 épocas como classificador binário. O resultado foi bastante revelador: apenas **50% de accuracy**, o que evidencia uma limitação clássica do treinamento do zero com poucos dados — a rede não tem capacidade de generalização suficiente. Na **tabela comparativa final**, fica claro o trade-off: a YOLO customizada lidera em precisão e em facilidade de uso por aproveitar transfer learning, a YOLO COCO é a mais rápida de configurar mas não é especializada nas minhas classes, e a CNN do zero exigiria dezenas de vezes mais dados ou data augmentation pesado para chegar perto."

**🎯 Ação na tela:** pause na tabela comparativa por uns 3-4 segundos para o avaliador ler. Se possível, dê zoom no navegador (`Ctrl + +`) para a tabela ficar legível.

---

### CENA 6 — Análise crítica e encerramento (4:15 – 4:55)

**🖥️ Tela:** role até a seção **2.5 Análise crítica** ou **Conclusões** no notebook. Volte ao README do GitHub para encerrar.

**🎤 Fala:**

> "Para fechar, a análise crítica das três abordagens. Em **facilidade de uso**, a YOLO COCO ganha por ser plug-and-play, mas a YOLO customizada empata pela maturidade da biblioteca *Ultralytics*. Em **precisão**, a YOLO customizada lidera com folga. Em **tempo de treino**, a YOLO customizada de 20 épocas é o melhor custo-benefício. Em **tempo de inferência**, todas as YOLOs são equivalentes. A grande lição do projeto foi confirmar, na prática, o valor do **transfer learning** quando se trabalha com datasets pequenos e domínios específicos. Era isso, professor, obrigado pela atenção! Todo o código, gráficos e o histórico de commits estão no repositório, e os links do GitHub e deste vídeo estão na entrega da FIAP. Até a próxima fase!"

**🎯 Ação na tela:** termine mostrando o repositório no GitHub com a URL visível na barra de endereço.

---

## ⏱️ Cronograma resumido

| Cena | Início – fim | Duração | Tela principal |
|------|-------------|---------|----------------|
| 1. Abertura | 0:00 – 0:25 | 25" | Repo GitHub (home) |
| 2. Tour pelo repo | 0:25 – 1:00 | 35" | Repo GitHub (estrutura) |
| 3. Decisão metodológica | 1:00 – 1:30 | 30" | Notebook (justificativa) |
| 4. Entrega 1 (YOLO custom) | 1:30 – 3:00 | 1'30" | Notebook (treinos YOLO) |
| 5. Entrega 2 (COCO + CNN + tabela) | 3:00 – 4:15 | 1'15" | Notebook (comparativos) |
| 6. Análise crítica e fim | 4:15 – 4:55 | 40" | Notebook + Repo GitHub |
| **Total** | | **~4'55"** | |

---

## ✅ Checklist final antes de subir no YouTube

- [ ] Áudio audível e sem ruído pesado
- [ ] Tela legível (zoom de 110-125% no navegador ajuda na leitura)
- [ ] Apresentei nome, RM e grupo na abertura
- [ ] Mostrei a estrutura template FIAP do repo
- [ ] Justifiquei a substituição do Make Sense IA pelo pseudo-labeling
- [ ] Mostrei os resultados da YOLO 20 e 50 épocas (mAP=0,995)
- [ ] Mostrei a YOLO COCO e a CNN do zero (50% acc)
- [ ] Mostrei a tabela comparativa
- [ ] Encerrei com agradecimento
- [ ] Vídeo tem **menos de 5 minutos**

## 📤 Como subir no YouTube como "Não listado"

1. Acesse `https://studio.youtube.com`
2. Clique no botão **"Criar"** no canto superior direito → **"Enviar vídeos"**
3. Arraste o arquivo do vídeo
4. **Título:** `PBL Fase 6 - Cap 1 O Despertar da Rede Neural - Vitorio Stevanatto Compri Paciulo RM 567895 - Grupo 45`
5. **Descrição (opcional):** copie o link do GitHub
6. Em **"Visibilidade"**, escolha **"Não listado"** (não é "Privado" — privado o professor não consegue assistir)
7. Clique em **"Salvar"**
8. Copie o link compartilhável e cole na entrega da FIAP, junto com o link do repositório

---

## 💡 Como exportar este roteiro em PDF

Você pode:
1. **Pelo GitHub:** abra este arquivo no navegador, use `Ctrl+P` → "Salvar como PDF" no destino da impressora.
2. **Pelo VS Code:** clone o repo, instale a extensão "Markdown PDF" e clique com o botão direito → "Markdown PDF: Export".
3. **Online:** copie o conteúdo, cole em `https://www.markdowntopdf.com/` e baixe.
