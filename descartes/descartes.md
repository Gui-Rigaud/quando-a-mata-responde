# Registro de Descartes

Documentação dos takes gerados e **descartados** no processo de seleção. Só entra aqui o que foi gerado, ouvido e rejeitado por um critério declarado.

A distinção que importa: **selecionar pelo eixo** é descartar porque o take falhou num critério declarado antes da escuta. **Descartar por gosto** é descartar porque soou menos bonito. Este arquivo existe para deixar visível qual foi qual.

## Escopo

Cobre as duas espécies com descarte registrado: **preguiça-de-pescoço-largo** (8 descartados) e **beija-flor-preto** (1 descartado). As demais peças da coleção ainda não têm registro de descarte.

## Convenções de nome

```
preguica_ger<GERACAO>_t<TAKE>.wav
```

- `ger1`, `ger2`, `ger3` — a geração do prompt de onde o take veio.
- `t1`–`t4` — o índice do take dentro daquela geração, como o ElevenLabs exportou.

Nomes de origem preservados em `medidas_espectrais.csv`, coluna `file`.

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

## O que os dois processos juntos deixam ver

- **Preguiça:** 12 takes → 4. O caminho foi de *contínuo* para *discreto*, e de *agudo genérico* para *voz identificável*. A peça final é a mais lenta e a mais espaçada da coleção — que é o que uma preguiça é.
- **Beija-flor:** 4 takes → 3. Descarte mínimo, e por motivo de **estabilidade** (distância), não de identidade.

O contraste é o achado mais útil: mesmo prompt, mesma ferramenta e mesma configuração produzem densidades de descarte muito diferentes. Isso indica que **o volume de descarte é informação sobre a espécie e sobre o prompt, não sobre a ferramenta**.
