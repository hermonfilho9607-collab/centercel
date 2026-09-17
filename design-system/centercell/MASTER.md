# Center Cell: sistema de design (MASTER)

> Documento de racional interno, não vai pro ar (ver `.vercelignore`).
> Escrito à mão a partir de fontes verificadas (amostragem de pixel da logo
> real + pesquisas pontuais no `ui-ux-pro-max`), não do agregador
> `--design-system`. Ver [[feedback-design-system-verification]] na memória
> do projeto sobre por que esse agregador é pouco confiável pra queries com
> adjetivos genéricos.

## 1. Briefing

- **Marca:** Center Cell (grafia oficial da logo: duas palavras, "CELL" com
  dois L; ficha do Google usa "Center Cell").
- **Negócio:** assistência técnica especializada em smartphones + loja de
  eletrônicos (celular, smartwatch, eletroportáteis, acessórios), foco
  em iPhone. Categoria no Google: "Loja de eletrônicos".
- **Local:** R. Antônio Silva, 59, Centro, Vespasiano, MG.
- **Referência de estrutura:** projeto Viper Cel (`../vipercel`), mesmo tipo
  de negócio (assistência técnica em smartphones). Pedido explícito do
  cliente foi seguir a estrutura "mais ou menos", mas de forma **inovadora,
  sem parecer cópia**.
- **Referência visual fornecida:** `REFERENCIA.jpg`, um template de site de
  eletricista (tema escuro, tipografia bold/condensada, faixa de confiança,
  grid de estatísticas). Usado só como referência de *estrutura de
  autoridade/confiança* e tema escuro; as cores do template (laranja) foram
  descartadas em favor das cores reais da marca.

## 2. Cor: extraída por amostragem de pixel do `logo.jpg` original

Nada abaixo foi "escolhido por adjetivo": são valores lidos diretamente dos
pixels do arquivo enviado pelo cliente (ver script de amostragem usado nesta
sessão) e depois ajustados minimamente para consistência de produção.

| Token | Hex | Origem | Uso |
|---|---|---|---|
| `--fundo` | `#071B0D` | próximo do verde-escuro mais amostrado (`#031905` a `#073C07`) | fundo da página |
| `--superficie` | `#0E2E18` | derivado (mais claro que o fundo p/ hierarquia) | cards, header quando "rolou" |
| `--dourado` | `#F6C90E` | amostrado direto do traço de tinta e do wordmark "CELL" (`#F5CE07` / `#FDCC05`) | acento primário, títulos, ícones |
| `--dourado-claro` | `#FCE271` | derivado | texto sobre fundo escuro que precisa de leveza |
| `--branco` | `#F6F9F5` | amostrado do anel branco do símbolo (`#FBF9FA`) | texto principal |
| `--whatsapp` | `#25D366` | cor oficial WhatsApp | CTA primário |
| `--texto-no-whatsapp` | `#06210F` | n/a | **texto escuro sobre o verde do WhatsApp**, ver nota de contraste abaixo |

**Nota de contraste (repetir em todo projeto que usar botão WhatsApp):** a
Viper Cel teve um bug real de contraste: texto branco sobre o verde
`#25D366` do WhatsApp dá ~2:1 (precisa 4,5:1). Esse projeto já nasce com
`--texto-no-whatsapp` escuro por padrão, mesma lógica do botão preto-no-verde
do Spotify. Não trocar para branco.

O elemento "bandeira do Brasil" da logo (globo azul `#0B2A6B` + verde
bandeira) **não virou paleta principal do site**: decisão consciente. Usar
azul de bandeira em botões/textos correntes quebraria a hierarquia de cor
(dourado = ação/destaque) e o contraste teria que ser revalidado à parte. Em
vez disso, o "recado" de marca nacional foi resolvido com **conteúdo**, não
cor: card `.selo-brasil` na seção Diferenciais ("Comércio local, atendimento
de gente daqui"), com um emblema circular abstrato (arco + ponto, cores da
marca), não uma bandeira literal nem emoji 🇧🇷 (regra do skill: sem emoji
como ícone estrutural).

## 3. Tipografia

**Archivo Expanded** (700/800, títulos) + **Archivo** (400 a 700, texto): uma
família só, dois eixos de largura.

Por quê: o wordmark da logo é um sans bold/condensado robusto. A Viper Cel já
usa Barlow Condensed + Inter (duas famílias, proporção condensada); repetir
a mesma dupla aqui pareceria reskin. Archivo Expanded é
**proporcionalmente o oposto** (expandido, não condensado) e ainda assim tem
o mesmo peso/confiança visual do wordmark original: diferenciação real, não
só de cor. Cross-check no `ui-ux-pro-max --domain typography`: nenhum
pareamento do catálogo é literalmente "Archivo Expanded + Archivo", mas o
resultado "Sports/Fitness" (Barlow Condensed + Barlow) confirma que a lógica
de "uma família, dois pesos/larguras" é um padrão válido pra marca
bold/enérgica; só trocamos a família pra não colidir com a Viper Cel.

## 4. Layout: como diferencia da Viper Cel

| | Viper Cel | Center Cell |
|---|---|---|
| Herói | foto de fundo (bleed direita) + logo grande | grid 2 colunas: texto à esquerda, **card da logo inclinado com brilho** à direita |
| Seção nova | não tem | **Como funciona** (4 passos: diagnóstico, orçamento, reparo, entrega) |
| Loja | lista + 1 foto grande | **grid de 4 categorias** (cards, sem depender de foto) |
| Diferenciais | grid 4 cards uniforme | 4 cards + **1 card "selo Brasil" full-width** destacado |
| Depoimentos | avatar com inicial do nome | ícone de aspas (nomes não foram fornecidos, não inventados) |
| Paleta | azul `#072E95` sobre quase-preto neutro | verde `#071B0D` sobre dourado `#F6C90E` |

## 5. Pesquisas de verificação (`ui-ux-pro-max`, não `--design-system`)

- `--domain product "electronics repair store bold energetic"`: nenhum
  resultado é uma loja de eletrônicos/assistência técnica literal; usado só
  como cross-check de que "Home Services (Plumber/Electrician)" reforça o
  padrão de landing "Conversion-Optimized + Trust" que a própria referência
  do cliente já mostrava.
- `--domain color "green gold dark electronics tech"`: resultado "Card &
  Board Game" (`#15803D` + `#D97706` sobre `#0F172A`) confirmou que
  verde+dourado sobre fundo escuro é uma combinação acessível/plausível antes
  de eu hand-author os tokens finais a partir da logo real.
- `--domain style "bold condensed sports energetic dark"`: nenhum estilo do
  catálogo é um match literal; `dark-mode-oled` confirmou a escolha de fundo
  quase-preto (não cinza neutro) como acessível e "on-brand" pro pedido do
  cliente.

## 6. Imagens

Ver `PROMPTS-IMAGENS.md`. A geração automática via MCP (Higgsfield/GPT
Image) falhou nesta sessão com `Requires basic plan or higher`, não é bug
de prompt, é restrição de plano da conta conectada. Até resolver:
- Herói usa o recorte "lockup" da própria logo (`assets/logo-lockup.jpg`)
  num card inclinado com brilho dourado, funciona como visual completo sem
  depender de foto de produto.
- Loja usa grid de categorias (ícone + texto), não foto.
- `assets/compartilhamento.jpg` (imagem de link/OG) foi montada
  programaticamente (fundo com glow + lockup), não gerada por IA.
