# Registro de Descartes

Documentação dos takes gerados e **descartados** no processo de seleção. Só entra aqui o que foi gerado, ouvido e rejeitado por um critério declarado.

A distinção que importa: **selecionar pelo eixo** é descartar porque o take falhou num critério declarado antes da escuta. **Descartar por gosto** é descartar porque soou menos bonito. Este arquivo existe para deixar visível qual foi qual.

## Escopo

Cobre as seis espécies com descarte registrado: **araponga** (2 descartados), **sabiá-una** (2 descartados), **preguiça-de-pescoço-largo** (8 descartados), **beija-flor-preto** (1 descartado), **anta** (2 descartados) e **sapo-martelo** (1 descartado). As demais peças da coleção ainda não têm registro de descarte.

## Convenções de nome

```
<especie>_ger<GERACAO>_t<TAKE>.wav
```

- `ger1`, `ger2`, `ger3` — a geração do prompt de onde o take veio.
- `t1`–`t4` — o índice do take dentro daquela geração, como o ElevenLabs exportou.

Nomes de origem preservados em `medidas_espectrais.csv`, coluna `file`.

---

## Araponga (*Procnias nudicollis*)

**4 takes gerados · 1 geração · 2 mantidos em `generated/` · 2 descartados em `descartes/araponga/`**

### Geração 1 — 2 de 4 descartados

Descartados: `araponga_ger1_t1.wav` · `araponga_ger1_t4.wav`

- **Intenção:** simular o chamado metálico e estridente da araponga macho (*sharp metallic clang like hammer striking anvil*), com golpes isolados a cada 5–8 segundos em primeiro plano sobre ambiência sutil de floresta.
- **Problema encontrado:**
  - `t1` — **descartado.** Ausência de sujeito em primeiro plano. O modelo gerou apenas ruído de fundo difuso em nível residual (RMS 0,0011 / −59,3 dB; pico de 3,5% / −29,1 dB), sem nenhum dos golpes metálicos característicos ao longo dos 30 s.
  - `t4` — **descartado.** Falha de recorrência e dinâmica temporal. O take dispara uma única batida metálica aos ~2 s e entra em silêncio absoluto pelo restante da faixa (27,8 s contínuos de vazio), violando a diretriz de chamados periódicos espaçados (`isolated strikes every 5-8 seconds`).
- **Decisão:** descartar `t1` por ausência da vocalização da espécie; descartar `t4` por silenciamento prematuro e abandono da cadência temporal.
- **O que aprendemos:** a instrução de temporização irregular (`irregular timing`) pode ser interpretada pelo modelo como permissão para cessar a emissão sonora após o primeiro evento (*one-shot*). Em sons percussivos pontuais, a consistência de múltiplos eventos ao longo do take precisa ser verificada: `t2` e `t3` (mantidos como `araponga_1` e `araponga_2`) sustentaram os golpes distribuídos no tempo, enquanto `t1` e `t4` falharam em estabelecer o sujeito sonoro.

### Medição

- `araponga_ger1_t1.wav`: pico 3,49% (−29,1 dB) e RMS 0,0011 (−59,3 dB) — o take mais baixo e vazio do conjunto, confirmando a ausência do sujeito.
- `araponga_ger1_t4.wav`: pico 16,49% (−15,7 dB) e RMS 0,0037 (−48,6 dB) — nível muito baixo devido ao silêncio prolongado pós-disparo.
- Em contrapartida, os mantidos (`araponga_1` e `araponga_2`) sustentam picos entre 14,8% e 55,6% com RMS em −36,9 dB e −40,8 dB, refletindo a presença ativa dos golpes no plano principal.

---

## Sabiá-Una (*Turdus flavipes*)

**4 takes gerados · 1 geração · 2 mantidos em `generated/` · 2 descartados em `descartes/sabiauna/`**

### Geração 1 — 2 de 4 descartados

Descartados: `sabiauna_ger1_t3.wav` · `sabiauna_ger1_t4.wav`

- **Intenção:** obter frases assobiadas límpidas e brilhantes (3–4 s) com contorno de pitch variado e pausas naturais de 4–5 s no topo do dossel, mantendo fidelidade bioacústica sem virar melodia instrumental artificial.
- **Problema encontrado:**
  - `t3` — **descartado.** Quebra da estrutura temporal de frases e pausas, associada a estridência excessiva. O take apresenta uma sequência inicial densa (0–7 s), seguida por um vazio anômalo de 8 s (10–18 s) e encerra com um bloco contínuo e estridente de assobios ininterruptos nos últimos 8 s (22–30 s), desrespeitando os intervalos de respiração e acumulando 98,1% da energia acima de 4 kHz.
  - `t4` — **descartado.** Saturação e clipagem digital severa. O sinal bate repetidamente no teto de 0 dBFS (*flat factor* de 5,26 dB) com RMS excessivamente alto (0,1325 / −17,6 dB), resultando em um som distorcido, áspero e abafado (centróide rebaixado para 2,7 kHz), incompatível com o timbre límpido e brilhante da ave.
- **Decisão:** descartar `t3` por perda de cadência natural (parede contínua de assobios) e aspereza aguda; descartar `t4` por defeito técnico de saturação/clipagem digital.
- **O que aprendemos:** manter frases separadas por pausas declaradas no prompt (`natural pauses 4-5 seconds between phrases`) é vulnerável à tendência do sintetizador de colar frases contíguas em cascata (como em `t3`) ou de empurrar o ganho até o limite do clipping quando tenta reforçar a presença do primeiro plano (como em `t4`). Os takes aceitos (`sabiauna_1` e `sabiauna_2`) conseguiram articular as frases com dinâmicas limpas (picos de −0,2 a −2,8 dBFS) sem distorcer o sinal.

### Medição

- `sabiauna_ger1_t4.wav`: pico de 100% (0 dBFS, clipagem detectada) e RMS de 0,1325 (−17,6 dB) — a medição evidencia saturação extrema e compressão/distorção por ganho excessivo.
- `sabiauna_ger1_t3.wav`: centróide elevado (~5,0 kHz) e 98,1% de energia acima de 4 kHz, com dinâmica irregular e bloco final contínuo.
- Os takes mantidos (`sabiauna_1` e `sabiauna_2`) operam em faixa dinâmica equilibrada (RMS ~0,056–0,061 e picos abaixo de 0 dBFS), preservando clareza tímbrica e espaçamento.

---

## Preguiça-de-pescoço-largo (*Bradypus torquatus*)

**12 takes gerados · 3 gerações de 4 · 4 mantidos em `generated/` · 8 descartados em `descartes/preguica/`**

Aritmética: 4 (g1) + 2 (g2) + 2 (g3) = 8 descartados. As gerações 2 e 3 produziram 4 takes cada e tiveram 2 mantidos cada.

### Geração 1 — 4 de 4 descartados

`preguica_ger1_t1.wav` · `preguica_ger1_t2.wav` · `preguica_ger1_t3.wav` · `preguica_ger1_t4.wav`

- **Intenção:** testar a versão reescrita do prompt, com sujeito em primeiro plano e background quase mudo. O objetivo era reconhecer a preguiça.
- **Problema encontrado:** som agudo e contínuo pelos 20 s inteiros. Não dava para distinguir o bicho.
- **Decisão:** descartar a geração inteira.
- **O que aprendemos:** esvaziar o background resolveu o insect wall, mas sobrou uma camada aguda. O modelo preenche o silêncio com conteúdo agudo em vez de deixá-lo vazio — o `sparse and irregular` do foreground não foi respeitado. Tirar uma camada da mix não basta: é preciso dizer o que o silêncio deve conter.

### Geração 2 — 2 de 4 descartados

Descartados: `preguica_ger2_t3.wav` · `preguica_ger2_t4.wav`

- **Intenção:** ver se a identidade da espécie aparecia depois do descarte integral da geração 1.
- **Problema encontrado:**
  - `t3` — **descartado.** Já dava para distinguir o bicho, soa como assobio. Mas é contínuo pelos 20 s e ainda tem um som agudo de fundo por cima.
  - `t4` — **descartado.** Muito parecido com os da geração 1: som agudo só.
- **Decisão:** descartar `t3` por continuidade e pelo agudo de fundo por cima; descartar `t4` por repetir o problema da geração 1.
- **O que aprendemos:** continuidade e agudez são **dois problemas separados**. Mesmo quando a identidade da espécie aparece, o material ainda não serve — uma vocalização que não respira não é vocalização, é tom. Avaliar os dois critérios separadamente evita o erro de descartar um take bom num critério porque ele já falhou em outro.

### Geração 3 — 2 de 4 descartados

Descartados: `preguica_ger3_t2.wav` · `preguica_ger3_t3.wav`

- **Intenção:** verificar se a continuidade da geração 2 era um caso isolado.
- **Problema encontrado:** os dois são só barulho agudo, desconfortável.
- **Decisão:** descartar ambos.
- **O que aprendemos:** a continuidade voltou a ser o problema dominante, o que confirma que a ocorrência na geração 2 não foi exceção. Depois de duas gerações com o mesmo prompt, o material não converge para o alvo — o impasse está na geração, não na escrita do prompt.

### Medição

`medidas_espectrais.csv` traz por arquivo: duração, centróide espectral, % de energia acima de 4 kHz, % abaixo de 1,5 kHz, pico e RMS.

O que os números mostram — e, mais importante, o que **não** mostram:

- O centróide espectral é **praticamente idêntico** entre takes mantidos e descartados, na faixa de 11,5–12,4 kHz. As duas peças finalizadas do repo ficam em 11,2 kHz. **A medição não separa os grupos.**
- Portanto "muito agudo" **não corresponde a energia alta medida aqui**. Ou o desconforto é aspereza dentro da banda, e não conteúdo acima de 4 kHz, ou a análise não captura o que incomoda no ouvido.
- O que **diferença de verdade** é o nível. Os descartados da geração 1 têm RMS 0,10–0,17 e pico 14–32; os mantidos têm RMS 0,02–0,16. Há sobreposição, mas os descartados da g1 estão entre os mais altos e mais contínuos.
- `preguica_ger2_t3.wav`, o que mais se aproximou da vocalização, tem o **centróide mais alto do conjunto** (12,4 kHz) com RMS baixo (0,07). Perfil de pico agudo isolado sobre base silenciosa — coerente com "dá pra distinguir o bicho".

**Conclusão registrada:** os critérios que justificaram a seleção foram **identificabilidade da espécie** e **não-continuidade** — ambos perceptivos, ambos declarados antes da escuta. A análise espectral documenta o processo, mas **não é o eixo que sustentou a seleção**. Registrar isso é mais honesto do que apresentar uma métrica que não apoia o que foi decidido.

---

## Beija-flor-preto (*Florisuga fusca*)

**4 takes gerados · 1 geração · 3 mantidos em `generated/` · 1 descartado em `descartes/beija_flor_preto/`**

### Geração 1 — 1 de 4 descartados

`beija_flor_preto_ger1_t2.wav` (original `Extreme_close-mic'd__#2-1790650979400.wav`)

- **Intenção:** manter a proximidade do prompt, ouvindo a ave ainda mais de perto.
- **Problema encontrado:** o som do beija-flor está muito perto e depois muito longe, e muito agudo. Os outros três takes têm o som mais claro.
- **Decisão:** descartar.
- **O que aprendemos:** variação de **distância aparente dentro do take** é defeito, não recurso. O `close-mic'd` do prompt foi o que produziu a oscilação: o modelo interpola a proximidade ao longo dos 30 s. Nos takes aceitos a ave fica em distância estável.

### Medição

`beija_flor_preto_ger1_t2.wav`: centróide 11,9 kHz, %Hi 82,5, pico 1,38, RMS 0,008 — o **nível mais baixo de todo o conjunto**, com os três aceitos entre 2,9 e 5,3 de pico.

Aqui, ao contrário da preguiça, o nível **é** um indicador útil: o take descartado é o mais fraco e o menos presente, coerente com "não está tão claro".

---

## Anta (*Tapirus terrestris*)

**8 takes gerados · 2 gerações de 4 · 3 mantidos em `generated/` · 2 descartados em `descartes/anta/` · 3 não baixados**

Mapeamento dos mantidos: `ger1_t1` → `anta_1`, `ger1_t2` → `anta_2`, `ger2_t1` → `anta_3`.

Os 3 takes restantes (`ger1_t3`, `ger2_t2`, `ger2_t3`) não foram salvos e o motivo não foi anotado na hora. Ficam fora deste registro, que só cobre descarte com critério declarado.

### Geração 1 — 1 de 4 descartado

Descartado: `anta_ger1_t4.wav`

- **Intenção:** anta andando devagar à noite perto de um riacho — passos pesados, galhos, bufos — com um assobio agudo e descendente repetido duas ou três vezes.
- **Problema encontrado:** `t4` — **descartado.** A anta está ausente. O take é praticamente só ambiência noturna, com poucos eventos curtos e fracos (≈2,7 s, ≈3,6 s, ≈10,5 s e ≈21 s).
- **Decisão:** descartar por ausência do sujeito.
- **O que aprendemos:** é o mesmo modo de falha do `araponga_ger1_t1`: o modelo entrega o `Background:` e esquece o `Foreground:`. Aparece em espécies e prompts diferentes, então é um risco do módulo, não da anta.

### Geração 2 — 1 de 4 descartado

Descartado: `anta_ger2_t4.wav`

- **Intenção:** segunda geração com o mesmo prompt e a mesma configuração, sem ajuste.
- **Problema encontrado:** `t4` — **descartado.** O take simula um ruído que soa mais como voz humana do que como animal. Todos os eventos ficam entre 3 e 15 s; de 15 a 30 s só resta ambiência.
- **Decisão:** descartar por troca de identidade (voz humana no lugar do animal).
- **O que aprendemos:** `no voice` estava no prompt e não impediu. Hipótese: a vocalização pedida (`squeal`) é o trecho do prompt mais próximo de voz, e quando o modelo tentou vocalizar, puxou para humano. Junto com os takes mantidos — nenhum tem o assobio —, a geração 2 sugere que o modelo não tem um som de anta para ancorar: ou omite o chamado, ou o troca por voz.

### Medição

Medido com ffmpeg (`ebur128` para loudness e true peak, `astats` para RMS, mix mono).

| Take | Situação | Loudness integrada | True peak | RMS |
|---|---|---:|---:|---:|
| `anta_1` (`ger1_t1`) | mantido | −34,9 LUFS | −8,2 dBTP | −39,7 dB |
| `anta_2` (`ger1_t2`) | mantido | −23,0 LUFS | +0,3 dBTP | −30,8 dB |
| `anta_3` (`ger2_t1`) | mantido | −41,3 LUFS | −18,7 dBTP | −48,6 dB |
| `anta_ger1_t4` | descartado | −45,3 LUFS | −19,2 dBTP | −52,5 dB |
| `anta_ger2_t4` | descartado | −35,0 LUFS | −8,3 dBTP | −42,5 dB |

- `anta_ger1_t4` é o take **mais baixo do conjunto**, coerente com "anta ausente" — como no `araponga_ger1_t1`, o nível serve de indicador.
- `anta_ger2_t4` **não se separa dos mantidos pelo nível** (−35,0 LUFS, praticamente igual ao `anta_1`). O que o separa é perceptivo (voz) e temporal (metade final vazia). Mesma conclusão da preguiça: o nível não sustenta esse descarte.
- `anta_2` passa de 0 dBTP (+0,3) sem clipar na amostra (pico de amostra −0,8 dBFS): estouro só na reconstrução do sinal, corrigido pelo limitador da montagem.
- Nos espectrogramas dos 5 takes não há traço tonal descendente — os eventos são faixas verticais de banda larga (passos, galhos, respiração). Confirmado na escuta: **o assobio não aparece em nenhum take**, nem nos mantidos.

---

## Sapo-martelo (*Boana faber*)

**8 takes gerados · 2 gerações de 4 · 3 mantidos em `generated/` · 1 descartado em `descartes/sapo_martelo/` · 4 não baixados**

Mapeamento dos mantidos: `ger1_t4` → `sapo_martelo_1`, `ger2_t3` → `sapo_martelo_2`, `ger2_t4` → `sapo_martelo_3`.

Os 4 takes restantes (`ger1_t1`, `ger1_t3`, `ger2_t1`, `ger2_t2`) não foram salvos e o motivo não foi anotado na hora. Ficam fora deste registro, que só cobre descarte com critério declarado.

### Geração 1 — 1 de 4 descartado

Descartado: `sapo_martelo_ger1_t2.wav`

- **Intenção:** um sapo-martelo cantando de dentro do ninho de barro — batidas ocas e curtas, cerca de duas por segundo, em sequências longas com pausas breves.
- **Problema encontrado:** `t2` — **descartado.** Soa como outro bicho, sem parecer batidas. Os primeiros 13 s são duas rajadas contínuas de ~7 s (34 e 27 pulsos seguidos, sem pausa), sobre uma faixa de inseto forte e contínua em ~6,5 kHz; depois disso sobram pulsos soltos.
- **Decisão:** descartar por troca de identidade.
- **O que aprendemos:** pancada repetida rápido demais e sem pausa deixa de ser pancada e vira trinado — e trinado é outro animal. A fronteira entre as duas leituras é o intervalo entre pulsos, justamente o parâmetro que o modelo menos respeitou também nos takes mantidos (ver Medição).

### Geração 2 — nenhum descarte registrado

Mesmo prompt e mesma configuração. `t3` e `t4` mantidos; `t1` e `t2` não baixados.

### Medição

Medido com ffmpeg: loudness e true peak com `ebur128`; batidas detectadas na banda de 800–2500 Hz em janelas de 20 ms (limiar a meio caminho entre o piso mediano e o pico, intervalo mínimo de 0,15 s entre pulsos); pulsos separados por menos de 0,35 s contam como uma rajada.

| Take | Situação | Loudness integrada | True peak | Rajadas por minuto | Pulsos por rajada (média / máx.) | Intervalo mediano entre rajadas |
|---|---|---:|---:|---:|---:|---:|
| `sapo_martelo_1` (`ger1_t4`) | mantido | −25,7 LUFS | −7,5 dBTP | 20 | 7,2 / 16 | 3,24 s |
| `sapo_martelo_2` (`ger2_t3`) | mantido | −23,4 LUFS | −5,1 dBTP | 40 | 3,8 / 6 | 1,48 s |
| `sapo_martelo_3` (`ger2_t4`) | mantido | −15,8 LUFS | 0,0 dBTP | 28 | 2,6 / 4 | 2,34 s |
| `sapo_martelo_ger1_t2` | descartado | −25,2 LUFS | −10,8 dBTP | — | 34 e 27 nas duas primeiras | — |

- **Rápido demais.** Dentro das rajadas, os pulsos vêm a cada ~0,18 s (mediana, nos quatro takes) — cerca de 5 por segundo, contra ~2 por segundo do canto real (107–124 por minuto). Como o detector não separa pulsos a menos de 0,15 s, o valor real pode ser ainda mais rápido. O modelo trocou a cadência regular pedida (`about two per second`) por rajadas rápidas separadas por pausas.
- **Agudo demais.** Nos 3 mantidos a energia se concentra em 1,2–2,5 kHz; a faixa de 200–700 Hz fica 15 a 24 dB abaixo. Na escuta, o canto soa mais agudo que as gravações de referência. O prompt não pedia altura (`loud hollow knocking`) e o modelo resolveu no médio-agudo. Sem frequência dominante publicada, a comparação fica na escuta, não em número.
- **A identidade ficou, com ressalvas.** Na escuta, os mantidos "parecem um pouco" o sapo-martelo: a batida oca repetida está lá, mas o ritmo e a altura não batem com o real.
- `sapo_martelo_3` chega a 0,0 dBTP (pico de amostra −0,04 dBFS), sem clipagem (flat factor 0). O limitador da montagem resolve.
- **Próxima tentativa:** pedir altura e cadência explicitamente — `deep, low-pitched knock` e `one knock every half second, steady, not in fast bursts`.

---

## Muriqui-do-sul (***Brachyteles arachnoides***)

**Nenhum descarte de prompt registrado.**

As gerações utilizadas para a peça final foram aprovadas após escuta e montagem. Não houve, durante o processo documentado, uma tentativa explicitamente rejeitada por um critério declarado que permita registrar um descarte sem reconstruir informações posteriormente.

---

---

## Mutum-de-Alagoas (***Mitu mitu***)

**4 abordagens de prompt registradas · 3 descartadas · 1 aproveitada como base para a geração final**

### Geração 1 — tentativa de controlar a peça inteira 

- **Intenção:** construir uma paisagem sonora completa da Mata Atlântica nordestina, com chamadas do mutum-de-Alagoas surgindo gradualmente até restar uma única vocalização, seguida pela ambiência da floresta.

- **Problema encontrado:** o resultado não correspondia à vocalização desejada do mutum-de-Alagoas. O prompt tentava controlar simultaneamente a ambiência, a quantidade de chamadas e a progressão temporal da peça, sem produzir uma vocalização satisfatória para o sujeito principal.

- **Decisão:** descartar a abordagem para a vocalização principal.

- **O que aprendemos:** tentar descrever toda a composição em um único prompt reduziu o controle sobre o sujeito sonoro. A partir dessa tentativa, a vocalização passou a ser tratada separadamente da ambiência, permitindo que a montagem temporal fosse feita posteriormente.

### Geração 2 — descrição acústica genérica 

- **Intenção:** testar uma vocalização de ave grave, ressonante e oca, buscando aproximar a sonoridade do mutum por características acústicas.

- **Problema encontrado:** o resultado ficou excessivamente grave, fechado e oco, afastando-se da sonoridade desejada para a vocalização.

- **Decisão:** descartar.

- **O que aprendemos:** descritores como `deep`, `low-pitched`, `booming` e `hollow` empurraram o modelo para uma sonoridade excessivamente fechada, sem garantir a identidade sonora desejada.

### Geração 3 — vocalização excessivamente grave

- **Intenção:** especificar diretamente a vocalização do mutum-de-Alagoas, incluindo três sílabas, tom grave e uma última sílaba mais forte.

- **Problema encontrado:** o resultado ficou muito fechado e abafado. Na escuta, a vocalização chegou a lembrar um efeito artificial semelhante a um "zíper abrindo e fechando", em vez de uma vocalização natural de ave.

- **Decisão:** descartar.

- **O que aprendemos:** a concentração de descritores como `low`, `hollow`, `deep` e `rounded tone` condicionou excessivamente o modelo para uma sonoridade grave e fechada. A tentativa mostrou que era necessário reduzir a descrição do timbre e priorizar características mais simples da estrutura da vocalização.

### Geração 4 — vocalização simplificada 

- **Intenção:** testar uma vocalização com três notas claramente separadas, altura moderada e acento na nota final, evitando os descritores que haviam produzido os resultados abafados das gerações anteriores.

- **Problema encontrado:** nenhum descarte registrado nesta abordagem.

- **Decisão:** aproveitar a geração como base para a composição final.

- **O que aprendemos:** características estruturais como `three clear vocal notes`, `moderate pitch` e `strong final note` deram ao modelo uma orientação mais controlada do que a descrição excessivamente detalhada do timbre utilizada anteriormente.

---

## O que os processos juntos deixam ver

- **Araponga:** 4 takes → 2. Descarte por **ausência de sinal em primeiro plano** (t1 vazio) e **falha de persistência temporal** (t4 disparando um único golpe isolado e silenciando pelo resto do áudio).
- **Sabiá-una:** 4 takes → 2. Descarte por **distorção/clipagem digital** (t4 atingindo 0 dBFS com achatamento de onda) e **aglomeração contínua sem pausas naturais** (t3 gerando bloco ininterrupto de 8 s).
- **Preguiça:** 12 takes → 4. O caminho foi de *contínuo* para *discreto*, e de *agudo genérico* para *voz identificável*. A peça final é a mais lenta e a mais espaçada da coleção — que é o que uma preguiça é.
- **Beija-flor:** 4 takes → 3. Descarte mínimo, e por motivo de **estabilidade** (distância aparente oscilante), não de identidade.
- **Anta:** 8 takes → 3. Descarte por **ausência do sujeito** (`ger1_t4`) e **troca de identidade** (`ger2_t4`, voz humana). A falha mais importante ficou nos mantidos: o assobio pedido não apareceu em nenhum take. A peça entrou na coleção pelo corpo do animal, não pelo chamado.
- **Sapo-martelo:** 8 takes → 3. Descarte por **troca de identidade** (`ger1_t2`, trinado contínuo que soa como outro bicho). Os mantidos têm a identidade — a batida oca repetida —, mas falham em dois parâmetros: cadência ~2,5× mais rápida que a real, em rajadas, e altura mais aguda. É o primeiro caso da coleção em que a limitação dos mantidos pôde ser medida em número (pulsos por segundo), e não só percebida.
- **Muriqui:** nenhum descarte registrado. O processo convergiu sem uma tentativa explicitamente rejeitada por critério declarado. A estratégia utilizada foi diferente das peças que tentaram gerar o sujeito e a ambiência simultaneamente: **vocalização e floresta foram geradas separadamente** e organizadas posteriormente na montagem. O controle passou a estar menos no prompt único e mais na relação entre as camadas.

- **Mutum-de-Alagoas:** 4 abordagens → 3 descartadas. O processo mostrou uma mudança clara de estratégia: primeiro tentou-se descrever a peça inteira, depois uma característica acústica grave e, por fim, a estrutura da vocalização. As duas primeiras abordagens produziram resultados **fechados e abafados**, enquanto a abordagem final simplificou a descrição para notas claras, altura moderada e acento final. O caso mostra que, para uma espécie cuja vocalização não estava convergindo, **simplificar o timbre e descrever a estrutura** funcionou melhor do que acumular características acústicas.


O contraste é o achado mais útil: mesmo prompt, mesma ferramenta e mesma configuração produzem densidades de descarte e modos de falha muito diferentes. Isso indica que **o volume e a natureza do descarte são informação sobre a espécie e sobre o prompt, não sobre a ferramenta**.
