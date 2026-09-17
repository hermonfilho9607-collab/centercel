# Prompts de imagem: Center Cell

Tentei gerar essas imagens automaticamente nesta sessão (mesma ferramenta de
IA usada em outros projetos do estúdio) e a chamada falhou com **"Requires
basic plan or higher"**, uma restrição do plano da conta conectada, não
um problema do prompt. Duas opções: (1) atualizar o plano dessa conta e me
pedir pra tentar de novo, ou (2) gerar manualmente num serviço à sua escolha
(ChatGPT/DALL·E, Midjourney, Firefly, Stable Diffusion etc.) usando os
prompts abaixo e me mandar o resultado.

Prompts em **inglês de propósito**: geradores de imagem respondem melhor
assim, mesmo pra um site em português. Copie exatamente como está.

Direção de luz: fundo bem escuro (quase preto/verde), **um** ponto de luz de
borda na cor da marca (dourado `#F6C90E`), produto nítido, resto caindo pra
escuridão, mesma lógica cinematográfica da referência que você mandou, só
trocando a cor de azul pra dourado.

---

## 1. Imagem do herói (substitui o card com a logo)

**Onde entra:** seção Herói, `assets/foto-heroi.jpg`, proporção 4:5 (retrato).
Troque o `<img>` dentro de `.heroi-placa` em `index.html` linha ~371.

```
Cinematic product photography of a single modern smartphone floating at a
slight angle, positioned in the upper two-thirds of the frame. Deep near-
black green background (#071B0D) fading to pure black toward the edges.
Dramatic rim lighting in warm gold (#F6C90E) tracing the right edge and top
of the phone, screen off or showing a faint gold glow reflection. Shallow
depth of field, subtle floating dust or light particles, ultra-premium
studio photography, automotive-advertisement lighting style: moody, high-
contrast, minimal. Portrait orientation, 4:5 aspect ratio. No text, no
hands, no logos, no watermark.
```

**Negativo (se o gerador aceitar):** `cluttered background, multiple objects, bright even lighting, blue tones, text, watermark, logo`

---

## 2. Vitrine da loja (celular + smartwatch + acessórios)

**Onde entra:** seção Loja, hoje é um grid de categorias sem foto; dá pra
adicionar essa imagem como banner acima do grid, se quiser.

```
Professional flat-lay product photography on a dark near-black surface: a
modern smartphone, a smartwatch, a power bank and charging cables, arranged
neatly with generous spacing between items. Dramatic golden-yellow (#F6C90E)
accent lighting from one
side, deep green ambient tones in the shadows, otherwise near-black
background. High-end tech retail advertisement style, sharp focus,
commercial studio photography. No text, no visible brand logos. 4:5 aspect
ratio.
```

**Negativo:** `cluttered background, bright white background, warm orange lighting, text, watermark, logo`

---

## 3. Conserto em andamento (para a seção Serviços ou Como funciona, opcional)

```
Extreme close-up macro photography of hands using a precision screwdriver to
repair an open smartphone on a dark workbench, screen and internal
components visible. Dramatic single-source gold rim light (#F6C90E) from the
side, rest of the frame falling into near-black shadow. Sharp focus on the
tool and the phone's internals, shallow depth of field blurring the hands
slightly. Technical, precise, premium repair-shop mood, not messy or
cluttered. No visible face, no logos, no text. 4:3 aspect ratio.
```

**Negativo:** `messy workbench, cluttered tools, bright lighting, visible face, logo, text, cheap-looking`

---

## Depois de gerar (ou de eu tentar de novo com o plano atualizado)

1. Salve os arquivos com os nomes indicados (`foto-heroi.jpg`, `foto-loja.jpg`, etc.) dentro de `assets/`.
2. Comprima antes de subir se o arquivo passar de ~300-400KB.
3. Me avisa que eu conecto cada imagem no lugar certo do código. Hoje o
   herói e a loja já têm um visual completo sem foto (card com a própria
   logo, grid de categorias), então nada quebra enquanto isso não chega.
