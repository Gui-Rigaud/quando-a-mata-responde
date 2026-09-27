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
