# Design System — Poliana Bertunes (site oficial)

Extraído do site em produção (`polianabertunes.com.br/cobertura-de-cicatriz/`), WordPress + Elementor.
Serve de referência de qualidade/raciocínio para as próximas LPs do grupo Bertunes (Kathleen, Poliana, futuras).

---

## 1. Personalidade da marca

Clínica de estética avançada, tom **acolhedor + clínico**, nunca "vendedor". A página alterna
deliberadamente entre dois registros:

- **Clínico/técnico** — explica a técnica, credenciais, tecnologia ("Camuflagem paramédica",
  "Tecnologia Avançada", "Resultados progressivos").
- **Emocional/inspiracional** — fala da liberdade e autoestima recuperadas ("Recupere a liberdade
  de vestir o que quiser", "Sua cicatriz não precisa definir você").

Essa alternância é a espinha dorsal do copywriting: cada seção técnica é seguida (ou precedida) por
uma seção emocional. Nunca duas seções do mesmo registro seguidas.

---

## 2. Paleta de cores

| Token | Hex | Uso |
|---|---|---|
| `--cream` | `#FFFDF7` | Fundo principal (seções "brancas") |
| `--beige` | `#F3EFE3` | Fundo alternado (seções pares, contraste sutil sem quebrar a paleta) |
| `--mocha` | `#776956` | Cor primária de texto/heading, bordas de badge, ícones |
| `--green` | `#3C9C48` | Cor de destaque/confiança — bordas de chip, texto de prova social |
| `--green-tint` | `#3C9C4826` (15% opacidade) | Fundo suave atrás de chips/badges com borda verde |
| `--tan` | `#C0AD94` | Acento secundário — fundos de bloco de destaque |
| `--white` | `#FFFFFF` | Cards, superfícies elevadas |
| `--black` | `#000000` | Uso pontual (nunca como texto de corpo) |

**Regra de uso:** nunca mais que 2 cores de acento (mocha + green, ou mocha + tan) numa mesma
seção. O verde é reservado para prova social e confiança — não usar como cor de heading.

---

## 3. Tipografia

- **Display/serif:** `Volkhov` — headlines emocionais, números de destaque.
- **Corpo/sans:** `Urbanist` — parágrafos, botões, labels.

(O kit padrão do Elementor no site usa Roboto/Montserrat como fallback global, mas a página em si
sobrescreve tudo com Volkhov + Urbanist — é isso que define a identidade visual real.)

**Escala de tamanho observada (px):** 12, 14, 15, 16, 17, 19, 22, 24, 25, 29, 39, 41, 70

| Papel | Tamanho aprox. |
|---|---|
| Hero headline | 70px |
| Subheadline / heading de seção | 39–41px |
| Heading de card/feature | 22–29px |
| Corpo | 16–17px |
| Legenda / fine print | 12–14px |

**Pesos:** 300 (leve, corpo longo), 400 (corpo padrão), 500 (ênfase), 700 (headings, botões).

**Tracking:**
- Labels em caixa alta (eyebrows, badges): `letter-spacing: 4.8px` + `text-transform: uppercase`.
- Texto corrido com leve destaque: `letter-spacing: 1.1px`.

Regra: **toda vez que um texto está em uppercase, ele tem tracking largo (~4-5px)** — nunca uppercase
"apertado". Isso é o que dá o ar premium/clínico ao badge.

---

## 4. Layout & espaçamento

- Container: `max-width: 1140px` (1024px em tablet ≤1024px, 767px em mobile ≤767px).
- Espaçamento entre widgets dentro de uma seção: `20px` (linha) / `20px` (coluna) como padrão do kit.
- Spacers pontuais entre blocos de texto: `13px` e `19px` — ou seja, respiro pequeno e controlado
  entre headline → subheadline → CTA, não blocos genéricos de "80px" soltos.
- Padding de bloco/section: variações de `12px`, `22px`, `30px` verticais — seções compactas,
  sem excesso de whitespace decorativo.

**Leitura disso para nós:** o site oficial é mais compacto e "denso" que nosso padrão interno
(que usa 90-100px de padding por seção). Se quisermos aproximar desse padrão de produção, vale
reduzir o respiro vertical entre seções em ~30-40%.

---

## 5. Componentes

### Botão / CTA
- `border-radius: 30px` (pill quase completo) no kit padrão do site — bem mais arredondado que
  nosso padrão atual (2px).
- `padding: 16px` uniforme, `font-weight: 700`, `font-size: 14px`, uppercase.
- CTAs sempre nomeados com verbo de ação + benefício, nunca genérico:
  - "MELHORE SUA AUTOESTIMA!"
  - "AGENDE SUA CONSULTA"
  - "TENHA RESULTADOS SEMELHANTES!"
  - (nunca só "Agendar" ou "Saiba mais")

### Badges / chips (prova social, números)
- Borda `1px solid` na cor de acento (mocha ou green).
- `border-radius`: escala **6 / 10 / 14 / 18px** dependendo do tamanho do elemento (quanto menor
  o componente, menor o raio — não é um valor fixo único).
- Fundo com tint de 15% de opacidade da cor da borda (ex: `#3C9C4826` sobre borda `#3C9C48`).

### Cards de feature (3 colunas)
- Título curto (2-4 palavras) + 1 frase de descrição.
- Nunca mais que 3 por linha — o site usa exatamente 3 (Tecnologia Avançada / Menos Dor, Mais
  Conforto / Resultados Visíveis).

### Transições
- `transition: background 0.3s, border 0.3s, border-radius 0.3s, box-shadow 0.3s;` — hover states
  suaves em tudo que é interativo (não usar transições abruptas ou sem easing).

---

## 6. Estrutura de página (a "linha de raciocínio")

Ordem exata das seções na página de referência — este é o roteiro persuasivo, não só o visual:

1. **Hero** — autoridade rápida ("Especialista há 8 anos") + headline emocional + CTA de avaliação.
2. **Explicação da técnica** — registro clínico, ganha credibilidade técnica cedo. CTA: "MELHORE SUA AUTOESTIMA!"
3. **Benefício emocional** — "Recupere a liberdade de vestir o que quiser" — a régua emocional principal da página.
4. **Prova social numérica** — "+200 clientes", "8 anos", nome do serviço. Números sempre curtos e concretos.
5. **3 features técnicas** — tecnologia, conforto, resultado. Registro clínico de novo.
6. **CTA principal isolado** — headline que resume a promessa ("tratamento que devolve confiança, sem dor e sem cirurgia") + botão.
7. **Reasseguramento emocional** — "Sua cicatriz não precisa definir você" — repete o eixo emocional antes de pedir confiança social.
8. **Depoimentos** (prova social qualitativa, depois da numérica).
9. **Sobre a profissional** — bio + CTA repetido. Vem DEPOIS da prova social, não antes — a confiança já foi construída, agora se humaniza.
10. **Antes/depois** — a prova mais forte, perto do fim, com CTA final específico ("TENHA RESULTADOS SEMELHANTES!").
11. **Footer** — marca + CNPJ (transparência legal).

**Padrão-chave:** técnico → emocional → técnico → emocional → prova social → bio → prova visual.
Nunca dois blocos emocionais ou dois técnicos seguidos. Cada CTA ao longo da página é reescrito
para o contexto da seção (nunca repete o mesmo texto de botão duas vezes seguidas).

---

## 7. Voz & copy

- Frases curtas, diretas, sem jargão técnico não explicado.
- Uppercase reservado a CTAs e 1-2 palavras de ênfase dentro de frases longas (ex: "não precisa
  **DEFINIR** você").
- Números sempre em destaque tipográfico próprio (não dentro de parágrafo corrido).
- Sempre fecha seção de prova/benefício com CTA — nenhuma seção fica "solta" sem porta de saída
  para o WhatsApp.

---

## 8. Aplicação prática para novas LPs

Quando for pedido "no padrão da Poliana", isso agora significa duas coisas possíveis — perguntar
qual, se não estiver claro:

- **Padrão do site oficial** (este documento): paleta mocha/green/tan, tipografia Volkhov+Urbanist,
  botões bem arredondados (30px), seções mais compactas, estrutura técnico↔emocional.
- **Padrão do nosso `poliana/index.html` interno** (rose/blush, Cormorant Garamond + DM Sans,
  cantos quase retos 2-4px, seções generosas ~90-100px) — usado nas LPs internas atuais
  (`clinica-bertunes-v1`, `clinica-bertunes-v2`).

Os dois são coerentes com a marca, mas visualmente distintos — não misturar tokens dos dois
sistemas numa mesma página.
