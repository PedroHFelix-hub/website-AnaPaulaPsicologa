# Design System — v2

> **v1 foi descartada.** Registro do que era, do porquê caiu e do que ficou no lugar.
> Decisão sem registro vira discussão repetida daqui a dois meses.

---

## 1. Por que a v1 foi descartada

A v1 era: fundo creme quente, Lora (serifada) nos títulos, Inter no corpo, verde sálvia dessaturado como acento, container centralizado, seções empilhadas.

Cada token era defensável isoladamente. O conjunto era o problema: **fundo creme + serifada de display + um acento dessaturado é hoje o visual mais reconhecível de interface gerada por IA**, e também o template padrão de site de psicólogo. Trocar terracota por sálvia não muda o gênero.

O erro de método: as decisões foram tomadas token a token, nunca avaliadas como conjunto.

---

## 2. De onde vem a v2

A direção deixou de perguntar "o que é bonito num site de psicóloga" e passou a perguntar **o que existe no mundo da TCC e em nenhum outro lugar**.

A psicanálise tem o divã. A TCC tem o **registro de pensamentos**: uma ficha estruturada onde um pensamento automático é escrito e examinado por perguntas — que evidência sustenta isso, que leitura alternativa existe, que efeito isso produz.

Daí vem o sistema inteiro: rótulos de campo, trilha lateral, filetes, a serifada reservada à fala interna, e o elemento de assinatura da página inicial.

---

## 3. Cor

Dois chãos, não um.

| Token | Valor | Papel |
|---|---|---|
| `--ink-900` | `#12211C` | faixas escuras (dobra, rodapé) e texto sobre papel |
| `--ink-700` | `#24382F` | superfície escura secundária |
| `--ink-400` | `#4A5A52` | texto de apoio sobre papel |
| `--ink-200` | `#A9B6AE` | texto de apoio sobre tinta |
| `--paper-100` | `#EDEEEA` | chão da página |
| `--paper-50` | `#F7F8F5` | cartão sobre o papel |
| `--rule` | `#CFD4CB` | filetes |
| `--marker` | `#DCE49E` | único elemento cromático |

**O verde sálvia da decisão D9 sobreviveu mudando de papel:** deixou de ser acento sobre creme e virou o próprio fundo, muito escurecido e dessaturado.

**Menos luminância é decisão funcional**, não estética: parte do público navega de madrugada, no celular.

**Camadas de token mantidas** (crítica do Pedro, v1): primitivos (`--ink-900`) separados dos semânticos (`--color-button-bg`). O token semântico diz para que serve, nunca que cor é.

### Uso do acento
`--marker` aparece em **três lugares e só neles**: a palavra destacada da dobra, o filete do registro, o indicador do acordeão (mais o link de página atual na navegação). Acento espalhado deixa de ser acento.

---

## 4. Tipografia

Três faces, três papéis. **O papel encoda significado.**

| Face | Onde | Por quê |
|---|---|---|
| **IBM Plex Sans** | títulos, corpo, interface | Sans institucional lê "segurança/confiança" (D10). Serifada de display é o clichê da categoria |
| **Literata** | **só** pensamento citado | É a voz interna de quem lê, não a voz do site |
| **IBM Plex Mono** | rótulos, campos, anos | Vocabulário de ficha. Nunca em texto corrido |

Plex Sans e Plex Mono são a mesma superfamília: combinam por desenho, não por acaso.

**Descartadas:** Lora e Inter (v1); Playfair Display e Cormorant Garamond (contraste alto demais para tela pequena, associação de luxo — colide com o D10 negativo); DM Serif Display (peso único).

**Dívida conhecida:** três famílias custam mais que duas. Na publicação, hospedar e subsetar.

### Escala
Base 17px. Razão ~1.25. Os três degraus maiores são fluidos com `clamp()`, sempre com parte em `rem` — sem ela o zoom do usuário para de funcionar.

`--tracking-tight: -0.025em` no display grande; `--tracking-wide: 0.12em` no mono em caixa alta.

---

## 5. Espaçamento, forma, movimento

- Escala de espaçamento base **4px**, de `--space-1` a `--space-10`.
- **Raio: 3px, único.** Nem pílula (genérico), nem canto reto absoluto (a estética de jornal também virou clichê).
- **Não existe sombra no sistema.** A página é feita de camadas de papel, não de objetos flutuando. Onde a v1 usaria sombra, a v2 usa filete.
- Movimento: **uma** sequência de entrada na dobra. Efeitos espalhados são o que faz um layout parecer gerado.

---

## 6. Layout

- Container `min(100% - 3rem, 78rem)`.
- **Trilha lateral:** rótulo em mono à esquerda, conteúdo à direita — a anatomia de um campo de ficha. Em tela estreita o rótulo sobe, como num formulário de papel.
- Breakpoints: **720px** (a trilha aparece) e **1040px** (dobra e "sobre" em duas colunas). *Ainda não medidos no conteúdo — pendência.*
- Colunas assimétricas em toda parte (`1.1fr / 0.9fr`, `5fr / 7fr`): duas colunas iguais partem a página ao meio e o olho não sabe qual lado manda.
- Numeração `01/02/03` **só** em "Como funciona", onde a ordem é informação real.

---

## 7. Acessibilidade

- Contraste verificado nos pares principais (v1: 13.61 / 5.76 / 5.73 / 6.07). **Os pares da v2 ainda precisam ser medidos.**
- `:focus-visible` global, com variante para superfícies escuras — contorno da cor do fundo é contorno invisível.
- `role="list"` obrigatório onde há `list-style: none` (Safari/VoiceOver perde a semântica de lista).
- `aria-current="page"` na navegação, com indicação visual correspondente.
- `prefers-reduced-motion` respeitado globalmente.
- Área mínima de toque de 44px em todo alvo interativo.

---

## 8. Pendências

- Medir os breakpoints no conteúdo (720/1040 ainda são estimativa)
- Medir contraste de todos os pares da v2
- Arquivo intermediário (~900w) para o `srcset` funcionar em telas de densidade dupla
- `assets/img/hero-ana-paula-*.webp` ficaram órfãs
- Hospedar e subsetar as fontes
