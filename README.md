# Quando a Mata Responde

> **Coleção de Artefatos Sonoros da Biodiversidade da Mata Atlântica**  
> *Projeto Autoral da disciplina de Criatividade Computacional (CIn/UFPE)*

---

## 🌿 1. Eixo Poético e Curatorial

**Quando a Mata Responde** é uma coleção de efeitos sonoros concebida e sintetizada com ferramentas de Inteligência Artificial generativa, tendo como matéria-prima espécies emblemáticas da fauna da **Mata Atlântica**.

Cada artefato traduz uma forma particular de presença animal — vocalizações territoriais, cantos de acasalamento, trinados, esturros ou a movimentação mecânica de uma colônia — em uma cena curta de escuta atenta.

### Princípios do Eixo:
- **O animal como protagonista (*Foreground*):** O sujeito animal ocupa obrigatoriamente o primeiro plano acústico. A ambiência da floresta atua como situador espacial sutil, sem se transformar em trilha musical ou encobrir a assinatura sonora da espécie.
- **Referência bioacústica verificável:** Não entram efeitos genéricos de "som de selva" ou paisagens abstratas sem vínculo comprovado com o comportamento e a morfologia das espécies do bioma.
- **Diversidade tímbrica e espacial:** A coleção explora contrastes extremos de escala — do *close-mic* microscópico e seco (saúvas, beija-flor) à reverberação de copas montanhosas e dosséis profundos (araponga, bugio, muriqui).
- **Seleção por critérios declarados:** Cada peça finalizada é fruto de uma triagem rigorosa entre takes gerados, distinguindo claramente descarte técnico/conceitual por falha no eixo de rejeição por gosto subjetivo.

---

## 🎧 2. Catálogo da Coleção

A coleção reúne 12 peças sonoras finalizadas e masterizadas, disponíveis no diretório [`collection/`](file:///home/vtex-lab-ufpe/quando-a-mata-responde/collection):

| # | Faixa | Espécie (*Nome científico*) | Autor | Ferramenta | Duração |
|---|-------|-----------------------------|-------|------------|:-------:|
| **01** | [`01_mico_leao_dourado.wav`](file:///home/vtex-lab-ufpe/quando-a-mata-responde/collection/01_mico_leao_dourado.wav) | Mico-leão-dourado (*Leontopithecus rosalia*) | Alex Lacava | ElevenLabs Sound Effects | `1:18` |
| **02** | [`02_sauvas_carregadoras.wav`](file:///home/vtex-lab-ufpe/quando-a-mata-responde/collection/02_sauvas_carregadoras.wav) | Saúvas carregadeiras (*Atta* sp.) | Alex Lacava | ElevenLabs Sound Effects | `1:24` |
| **03** | [`03_araponga.wav`](file:///home/vtex-lab-ufpe/quando-a-mata-responde/collection/03_araponga.wav) | Araponga (*Procnias nudicollis*) | Guilherme Rigaud | ElevenLabs Sound Effects | `0:57` |
| **04** | [`04_sabiauna.wav`](file:///home/vtex-lab-ufpe/quando-a-mata-responde/collection/04_sabiauna.wav) | Sabiá-Una (*Turdus flavipes*) | Guilherme Rigaud | ElevenLabs Sound Effects | `0:57` |
| **05** | [`05_oncapintada.wav`](file:///home/vtex-lab-ufpe/quando-a-mata-responde/collection/05_oncapintada.wav) | Onça-pintada (*Panthera onca*) | Lucas Melo | ElevenLabs Sound Effects | `0:57` |
| **06** | [`06_bugioruivo.wav`](file:///home/vtex-lab-ufpe/quando-a-mata-responde/collection/06_bugioruivo.wav) | Bugio-ruivo (*Alouatta guariba*) | Lucas Melo | ElevenLabs Sound Effects | `0:57` |
| **07** | [`07_muriqui.wav`](file:///home/vtex-lab-ufpe/quando-a-mata-responde/collection/07_muriqui.wav) | Muriqui-do-sul (*Brachyteles arachnoides*) | João Ohashi | Adobe Firefly | `1:00` |
| **08** | [`08_mitumitu.wav`](file:///home/vtex-lab-ufpe/quando-a-mata-responde/collection/08_mitumitu.wav) | Mutum-de-Alagoas (*Mitu mitu*) | João Ohashi | Adobe Firefly | `1:21` |
| **09** | [`09_preguica.wav`](file:///home/vtex-lab-ufpe/quando-a-mata-responde/collection/09_preguica.wav) | Preguiça-de-pescoço-largo (*Bradypus torquatus*) | Levi Serrano | ElevenLabs Sound Effects | `1:11` |
| **10** | [`10_beijaflorpreto.wav`](file:///home/vtex-lab-ufpe/quando-a-mata-responde/collection/10_beijaflorpreto.wav) | Beija-flor-preto (*Florisuga fusca*) | Levi Serrano | ElevenLabs Sound Effects | `1:24` |
| **11** | [`11_anta.wav`](collection/11_anta.wav) | Anta (*Tapirus terrestris*) | Josias Netto | ElevenLabs Sound Effects | `1:26` |
| **12** | [`12_sapomartelo.wav`](collection/12_sapomartelo.wav) | Sapo-martelo (*Boana faber*) | Josias Netto | ElevenLabs Sound Effects | `1:26` |

---

## 📁 3. Organização do Repositório

```text
quando-a-mata-responde/
├── collection/               # Peças finais montadas e masterizadas (.wav)
├── generated/                # Takes brutos individuais aceitos (.wav / .mp3)
├── descartes/                # Áudios descartados, critérios e medições espectrais
│   ├── anta/                 # Takes descartados da anta
│   ├── araponga/             # Takes descartados da araponga
│   ├── beija_flor_preto/     # Takes descartados do beija-flor-preto
│   ├── preguica/             # Takes descartados da preguiça
│   ├── sabiauna/             # Takes descartados do sabiá-una
│   ├── sapo_martelo/         # Takes descartados do sapo-martelo
│   ├── descartes.md          # Registro analítico dos descartes e lições de escuta
│   └── medidas_espectrais.csv# Métricas acústicas (centróide, RMS, pico, % energia)
├── juntar_takes.sh           # Montagem: nivela takes, emenda com crossfade e masteriza
├── prompts_desc.md           # Registro detalhado de prompts, parâmetros e metadados
└── README.md                 # Documentação geral do projeto
```

### Detalhamento das Camadas:
- **[`collection/`](file:///home/vtex-lab-ufpe/quando-a-mata-responde/collection)**: Contém os 12 artefatos finais no formato `[NUMERO]_[NOME_DA_ESPECIE].wav`. Representa as obras compostas através de sobreposição, *crossfades* e montagem temporal dos takes aprovados.
- **[`generated/`](file:///home/vtex-lab-ufpe/quando-a-mata-responde/generated)**: Contém todos os takes brutos que foram aprovados nas sessões generativas para servirem de matéria-prima para a montagem final.
- **[`descartes/`](file:///home/vtex-lab-ufpe/quando-a-mata-responde/descartes)**: Centraliza os áudios rejeitados na curadoria e a documentação completa dos critérios de descarte ([`descartes/descartes.md`](file:///home/vtex-lab-ufpe/quando-a-mata-responde/descartes/descartes.md)), acompanhada por análises bioacústicas e espectrais ([`descartes/medidas_espectrais.csv`](file:///home/vtex-lab-ufpe/quando-a-mata-responde/descartes/medidas_espectrais.csv)).
- **[`prompts_desc.md`](file:///home/vtex-lab-ufpe/quando-a-mata-responde/prompts_desc.md)**: Centraliza a especificação de engenharia de prompt para cada espécie: contagem de caracteres, termos negativos (`no music, no rhythm`), modelagem espacial e notas sobre iterações.

---

## 💡 4. Processo de Ideação e Decisões de Design

O desenvolvimento conceitual e técnico do projeto seguiu as dinâmicas de ideação da disciplina:

### 🔍 Abrir o leque
- **Exploração:** Foram investigadas múltiplas abordagens no início do projeto, tais como trilhas musicais temáticas sobre preservação ambiental, paisagens sonoras imersivas de ecossistemas inteiros e sintetização de vocalizações isoladas de fauna.
- **Conclusão:** A amplitude inicial abriu caminhos diversos, mas permitiu ao grupo identificar que a maior potência expressiva residia na **escuta focada e singular da fauna**, transformando animais específicos no centro acústico de cada artefato.

### 🎯 Afiar o eixo
- **Refinamento:** Substituiu-se a noção vaga e difusa de "sons da Mata Atlântica" por uma regra curatorial estrita: **o animal no primeiro plano absoluto (*foreground*) e o ambiente como contexto espacial delimitador (*background*)**.
- **Desafio:** Calibrar a relação sinal/ruído entre a presença do sujeito e a ambiência da mata, garantindo que o som da floresta situasse a cena sem competir em intensidade ou mascarar as frequências da espécie.

### 🚫 Derrubar a ideia
- **Filtro crítico:** Foi questionado se os resultados gerados por IA correriam o risco de soar como áudios genéricos de biblioteca de foley ou representações estereotipadas sem respaldo biológico.
- **Diretriz:** Estabeleceu-se a obrigatoriedade de correspondência bioacústica verificável com a espécie alvo. Foram eliminadas texturas musicais e descartados todos os takes em que o fundo sonoro, artefatos de compressão ou melodias artificiais comprometessem o foco do artefato.

### 🤝 Escutar a reunião
- **Decisão metodológica:** Optou-se por não utilizar formalmente esta skill de recuperação de atas porque o grupo alcançou alinhamento rápido e unânime logo na primeira sessão de planejamento.
- **Aplicação de esforço:** O registro das alternativas consideradas (trilhas vs. soundscapes vs. foley animal) e os critérios de escolha foram documentados diretamente no repositório. O tempo foi canalizado para a pesquisa taxonômica, experimentação iterativa de prompts, análise espectral e curadoria de descartes.

---

## 🔬 5. Engenharia de Prompts e Síntese Acústica

Para assegurar fidelidade aos sinais bioacústicos e evitar vícios comuns de modelos generativos de áudio (como a introdução inadvertida de melodias musicais, compassos rítmicos ou vozes humanas), foram adotadas estratégias estruturantes:

1. **Termos Negativos Estruturantes:** Inclusão sistemática de diretivas de supressão (`No music, no melody, no rhythm, no voice, no instruments, no reverb`).
2. **Esvaziamento Ativo de Background:** Especificação de silêncios e fundos esparsos (`mostly empty darkness between calls`, `faint high canopy air`) para impedir o surgimento de "paredes de ruído" (*noise walls*).
3. **Modelagem Temporal e Dinâmica:** Especificação da duração dos eventos e pausas naturais (`bursts of 3-4s`, `natural pauses 4-5s`, `sparse and irregular timing`).
4. **Ancoragem Tímbrica por Analogias Físicas:** Uso de descritores materiais quando o nome taxonômico não ancora o som no modelo (ex.: `sharp metallic clang like hammer striking anvil` para Araponga; `granular scrape of thousands of small bodies` para Saúvas).

Para a documentação completa dos prompts e especificações de cada espécie, consulte [prompts_desc.md](file:///home/vtex-lab-ufpe/quando-a-mata-responde/prompts_desc.md).