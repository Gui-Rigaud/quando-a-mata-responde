# Registro de Prompts de Efeitos Sonoros

Documentação dos prompts utilizados na geração de efeitos sonoros para o projeto *Quando a Mata Responde*.

---

### 1. Araponga (*Procnias nudicollis*)

- **Nome Popular:** Araponga
- **Nome Científico:** *Procnias nudicollis*
- **Objetivo do Áudio:** Simular o chamado característico e estridente da araponga macho ao amanhecer em gravação de campo naturalista na Mata Atlântica.
- **Prompt:**
```text
Naturalistic field recording, dense Atlantic Forest at dawn, documentary style. Foreground: male Araponga bellbird call, sharp metallic clang like hammer striking anvil, piercing and loud, isolated strikes every 5-8 seconds, irregular timing. Background: distant wind through canopy, faint insects, soft leaf rustle. No music, no melody, no rhythm, no voice, no loop point.
```
- **Observações:**
  - **Tamanho:** 322 caracteres (respeitando o limite de 450 caracteres do ElevenLabs Sound Effects).
  - **Direcionamento acústico:** Inclusão de termos negativos (`No music, no melody, no rhythm, no voice, no loop point`) para suprimir cadências rítmicas ou harmonias musicais artificiais, preservando o aspecto bruto de gravação documental de campo.

---

### 2. Sabiá-Una (*Turdus flavipes*)

- **Nome Popular:** Sabiá-Una
- **Nome Científico:** *Turdus flavipes*
- **Objetivo do Áudio:** Reproduzir o canto assobiado do sabiá-una no topo do dossel em floresta montanhosa, mantendo intervalos naturais e ambiência distante.
- **Prompt:**
```text
Naturalistic field recording, mountainous Atlantic Forest treetops, documentary style. Foreground: Sabia-Una thrush singing, clear bright whistled phrases 3-4 seconds long, varied pitch contour, natural pauses 4-5 seconds between phrases. Background: gentle high canopy wind, distant faint forest ambience. No music, no melody structure, no instruments, no voice.
```
- **Observações:**
  - **Tamanho:** 301 caracteres (dentro do limite de 450 caracteres).
  - **Direcionamento acústico:** Remoção de estruturas melódicas musicais (`No music, no melody structure, no instruments, no voice`) para focar exclusivamente na bioacústica natural da ave e na reverberação de copas de árvores.

---

### 3. Mico-leão-dourado (*Leontopithecus rosalia*)

- **Espécie / Som-alvo:** Mico-leão-dourado
- **Autor:** Alex Lacava
- **Data:** 2026-09-27
- **Ferramenta:** ElevenLabs Sound Effects · Prompt influence 25%
- **Objetivo do Áudio:** Traduzir em som a vocalização de trinado do mico-leão-dourado, em condição de close-mic dentro do dossel, sem reverberação de sala — como o animal se ouviria a poucos metros, não como uma gravação de campo documental. A vocalização foi descrita por especificação acústica (trinado curto e repetido, com contorno de pitch) e sintetizada a partir dessa descrição, sem nenhum arquivo de som de referência.
- **Duração Gerada:** 30s por geração (teto do módulo) · 4 variações · 1 geração
- **Prompt:**
```text
Close-mic'd primate trill: a rapid burst of 8 very short whistles, each 0.1 seconds, rising then falling in pitch, thin and reedy. Small monkey, not a bird, no birdsong, no music, no melody. Dry Atlantic Forest canopy at dawn, no reverb. Sound effects foley, one-shot.
```
- **Observações e Ajustes:**
  - **Contagem de caracteres:** 268 / 450
  - **Restrições / Termos negativos:** `no birdsong` (barra o erro mais comum do modelo, que puxa para pássaro), `no music, no melody` (identidade sonora da coleção), `no reverb` (close-mic, sem sala), `one-shot` (pedido de disparo único, sem loop).
  - **Iterações / Ajustes realizados:** nenhuma regeração. As 4 variações foram aproveitadas integralmente: ordenadas por densidade de onsets (0,13 → 2,17 → 8,90 → 17,37 onsets/s) e montadas em 4 seções de 19,5 s cada, formando um arco que abre na tomada mais esparsa e fecha na mais densa. A peça final tem 1:18.
  - **Montagem:** crossfade de potência igual de 2 s nas costuras, masterização em −13,99 LUFS / true peak −3,44 dBTP, 44,1 kHz 16 bit estéreo.

---

### 4. Saúvas carregadeiras (*Atta* sp.)

- **Espécie / Som-alvo:** Saúvas carregadeiras
- **Autor:** Alex Lacava
- **Data:** 2026-09-27
- **Ferramenta:** ElevenLabs Sound Effects · Prompt influence 25%
- **Objetivo do Áudio:** Traduzir o som da colônia de saúvas carregando folhas e terra no chão de mata úmida, em close-mic. O sujeito do som é o **coletivo**, não o indivíduo: o que se ouve é a raspagem massiva de milhares de corpos de inseto sobre a serrapilheira, sem passos individuais e sem compasso.
- **Duração Gerada:** 30s por geração (teto do módulo) · 4 variações (1 duplicada) · 1 geração
- **Prompt:**
```text
Massed granular scrape of thousands of small hard insect bodies dragging across dry leaf litter, continuous dense rustle, steady, no individual footsteps, no melody, no music. Humid Atlantic Forest floor, close-mic'd. Sound effects foley, loop, ambience.
```
- **Observações e Ajustes:**
  - **Contagem de caracteres:** 254 / 450
  - **Restrições / Termos negativos:** `no individual footsteps` (a colônia não pode virar "formiga andando"), `no melody, no music` (identidade sonora da coleção), `close-mic'd` sem reverb de sala.
  - **Iterações / Ajustes realizados:** nenhuma regeração. **1 das 4 variações saiu duplicada byte a byte (mesmo MD5)** e foi descartada; restaram 3, empilhadas como camadas — base contínua entrando em 0 s, segunda em 12 s, terceira em 34 s, cada uma saindo antes do fim —, porque uma colônia não tem compasso e não faz sentido fatiada no tempo. A peça final tem 1:24.
  - **Montagem:** 3 camadas, masterização em −13,99 LUFS / true peak −3,05 dBTP, 44,1 kHz 16 bit estéreo.

---

### 5. Preguiça-de-pescoço-largo (*Bradypus torquatus*)

- **Espécie / Som-alvo:** Preguiça-de-pescoço-largo
- **Autor:** Levi Serrano
- **Data:** 2026-09-28
- **Ferramenta:** ElevenLabs Sound Effects · Prompt influence 80% · Loop desligado · Prompt enhancement desligado
- **Objetivo do Áudio:** Traduzir em som o gemido noturno da preguiça no dossel escuro da Mata Atlântica. É a primeira peça noturna da coleção e o primeiro mamífero depois do mico-leão-dourado: um animal lento e grave contra o trinado rápido e diurno do mico.
- **Duração Gerada:** 20s por geração (abaixo do teto de 30s) · 3 gerações · 4 takes escolhidas de 12 geradas
- **Prompt:**
```text
Night Atlantic Forest canopy, documentary field recording. Foreground: single sloth calling, prominent and close, slow descending groan rising into a long nasal whistle, throaty and low, clearly audible, sparse and irregular. Background: nearly silent forest, very faint sparse insects, slight leaf stir, mostly empty darkness between calls. No music, no melody, no rhythm, no voice, no reverb.
```
- **Observações e Ajustes:**
  - **Contagem de caracteres:** 394 / 450
  - **Restrições / Termos negativos:** `no music, no melody, no rhythm, no voice`, `no reverb`. O `no reverb` é deliberado: o objetivo é preservar o pigarro grave do animal, não o espaço acústico. A sensação de distância é recuperada pela irregularidade (`sparse and irregular`, `mostly empty darkness between calls`), não pelo afastamento da fonte.
  - **Iterações / Ajustes realizados:** 1 regeração de prompt, 3 gerações de áudio. A primeira versão do prompt especificava `wide distant perspective` e `Background: dense night insects`. Ouvido o resultado, o insect wall mascarou o sujeito e a peça não foi reconhecível como preguiça. Reescrito para a versão acima: `wide distant perspective` → `prominent and close`, `dense night insects` → `very faint sparse insects`. Gerações 2 e 3 mantiveram o prompt sem alteração — os problemas restantes eram de saída do modelo, não de prompt.
  - **Nota de escuta:** a principal lição do processo. Numa mix de sound effects, uma cue de background densa é renderizada como camada densa e engole o foreground, por mais bem especificado que ele esteja. Quando há um sujeito a ser identificado, o background precisa ser esvaziado ativamente, não basta removê-lo.
  - **Descartes:** 12 takes gerados em 3 gerações, 4 mantidos, 8 descartados. Áudios em `descartes/preguica/`, registro em `descartes/descartes.md`.

---

### 6. Beija-flor-preto (*Florisuga fusca*)

- **Espécie / Som-alvo:** Beija-flor-preto
- **Autor:** Levi Serrano
- **Data:** 2026-09-28
- **Ferramenta:** ElevenLabs Sound Effects · Prompt influence 80% · Loop desligado · Prompt enhancement desligado
- **Objetivo do Áudio:** Traduzir o canto do beija-flor-preto como fronteira acústica: a única ave capaz de cantar em frequência ultrassônica, cujo som se situa no ponto de encontro entre passerídeo e inseto ou morcego. É a peça mais conceitual da coleção, e a única cuja tradução assume distância em relação ao original.
- **Duração Gerada:** 30s por geração (teto do módulo) · 1 geração · 3 takes escolhidas de 4 geradas
- **Prompt:**
```text
Extreme close-mic'd hummingbird, dense Atlantic Forest understory, macro documentary recording. Foreground: single tiny hummingbird trill, very high thin whistles pitched far above normal birdsong, dry insect-like sharp edges, rapid irregular bursts, then silence. Background: near-absolute quiet, faint canopy air, almost no ambience. No music, no melody, no rhythm, no voice, no reverb.
```
- **Observações e Ajustes:**
  - **Contagem de caracteres:** 388 / 450
  - **Restrições / Termos negativos:** `no music, no melody, no rhythm, no voice`, `no reverb`. **Ausência deliberada de `no birdsong`** — termo idêntico ao usado no mico-leão-dourado, onde bloqueia o modelo de puxar para ave genérico. Aqui o canto *é* birdsong, então suprimir o termo derrubaria a própria peça. O que barra o resultado de virar material melódico são `no music`, `no melody` e `no rhythm`.
  - **Nome científico omitido do prompt:** `Florisuga fusca` não é um beija-flor — é um jacamar (Galbulidae), parente do beija-bobo. Nem o binomial nem o nome popular português servem ao modelo. `hummingbird` foi usado deliberadamente como mentira acústica: é o token que ancora trilo agudo e fino, que é o que se quer.
  - **Iterações / Ajustes realizados:** nenhuma de prompt. 1 geração, 4 takes, 3 mantidos. O take descartado falhou em estabilidade de distância, não em identidade.
  - **Nota de escuta:** o sintetizador não produz 50 kHz. A peça é uma tradução poética, não uma reprodução fiel — o limite é do modelo, não do prompt. Registrar como escolha assumida e não como falha esquecida.
  - **Contraponto à preguiça:** as duas peças também se opõem na densidade. `rapid irregular bursts` contra `sparse and irregular`; `near-absolute quiet` com silêncio como conteúdo contra silêncio como intervalo entre eventos. Loop desligado nas duas: na preguiça contradiria a própria especificação de irregularidade, e no beija-flor aplainaria o pico em vez de deixar o silêncio trabalhar.
  - **Descartes:** 4 takes gerados em 1 geração, 3 mantidos, 1 descartado por variação de distância aparente dentro do take. Áudio em `descartes/beija_flor_preto/`, registro em `descartes/descartes.md`.

---

Copie e preencha a estrutura abaixo para registrar novos prompts de efeitos sonoros:

```markdown
### [Nome Popular / Som-Alvo] (*[Nome Científico, se aplicável]*)

- **Espécie / Som-alvo:** 
- **Autor:** 
- **Data:** AAAA-MM-DD
- **Ferramenta:** ElevenLabs Sound Effects (ou outra)
- **Objetivo do Áudio:** 
- **Duração Gerada:** (ex: 10s)
- **Prompt:**
\`\`\`text
[Insira aqui o prompt completo exatamente como enviado ao modelo]
\`\`\`
- **Observações e Ajustes:**
  - **Contagem de caracteres:** X / 450
  - **Restrições / Termos negativos:** (ex: no music, no voice)
  - **Iterações / Ajustes realizados:** (ex: ajustes de pausas, dinâmica, etc.)
```
