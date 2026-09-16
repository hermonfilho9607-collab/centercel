# Center Cell — manual do site

Site de uma página só (`index.html`), sem framework, sem build — HTML, CSS e
um pouco de JavaScript puro. Roda em qualquer hospedagem estática (o projeto
já está configurado para a Vercel).

---

## 1. O que falta antes de publicar

1. **Tempo de mercado e garantia.** Os outros sites do estúdio (ex: Viper
   Cel) destacam "+X anos de mercado" e "X dias de garantia" no herói. Você
   ainda não confirmou esses dois números pra Center Cell, então **não
   inventei nenhum** — os 3 dados em destaque no herói hoje usam só números
   reais (4,3★ no Google, foco em iPhone, 5 categorias na loja). Me manda os
   dois valores que eu adiciono como um 4º e 5º dado.
2. **Redes sociais.** O rodapé só linka pro Google Maps (dado real) por
   enquanto. Manda o Instagram/Facebook se vocês tiverem, que eu adiciono.
3. **Fotografia real ou gerada por IA.** Ver seção 2 abaixo.

## 2. As fotos

Você pediu pra gerar as fotos com IA, mas a chamada automática falhou nesta
sessão com **"Requires basic plan or higher"** (restrição de plano da conta
conectada, não um problema de prompt). Os prompts prontos estão em
[`PROMPTS-IMAGENS.md`](PROMPTS-IMAGENS.md) — dá pra atualizar o plano e me
pedir pra tentar de novo, ou gerar manualmente em qualquer serviço e me
mandar o resultado.

Até lá, o site **não depende de foto nenhuma** pra ficar completo:
- **Herói:** um recorte da própria logo (`assets/logo-lockup.jpg`, símbolo +
  "CENTER CELL IMPORTADOS", sem o canto da bandeira) dentro de um card
  inclinado com brilho dourado. Quando a foto do produto chegar, ela entra
  no lugar desse card — ver instrução no topo do `PROMPTS-IMAGENS.md`.
- **Loja:** grid de 4 categorias (celular, smartwatch, eletroportáteis,
  acessórios) com ícone, sem depender de foto.

## 3. A marca (logo)

O arquivo `logo.jpg` que você mandou tem um fundo com textura "suja"
(pincelada verde/dourada + emblema da bandeira) — diferente do fundo azul
chapado que outros clientes mandaram, então **não deu pra remover o fundo
por chroma-key** (tentei: como a pincelada também é dourada, a mesma cor do
texto, o recorte automático não separa um do outro de forma limpa).

Em vez de forçar um recorte ruim, usei o próprio fundo texturizado como
parte do visual — mesma lógica de um "selo"/"card" de marca, comum quando não
existe arte vetorial:
- `assets/logo-lockup.jpg` — símbolo + "CENTER CELL" + "IMPORTADOS", sem o
  canto da bandeira. Usado grande no herói, dentro de um card com borda e
  brilho dourado.
- `assets/logo-icon.jpg` — só o símbolo (o "C" com o celular), recorte
  quadrado. Usado no cabeçalho, rodapé e como base dos favicons.
- `assets/favicon-16.png`, `favicon-32.png`, `apple-touch-icon.png` —
  gerados a partir do `logo-icon.jpg`.

Se um dia vocês tiverem a logo em vetor (AI/EPS/SVG) ou quiserem investir
num fundo transparente de verdade (teria que ser refeito à mão, recorte
automático não funciona nessa arte), vale substituir — o resultado fica mais
nítido em qualquer fundo.

O arquivo original está preservado em `../fotos-originais/centercel-logo-original.jpg`.

## 4. Como o site foi construído

Direção de arte: **verde profundo + dourado**, extraída por amostragem de
pixel direto do seu `logo.jpg` (não estimada) — ver o racional completo,
com os hex exatos e o porquê de cada decisão, em
[`design-system/centercell/MASTER.md`](design-system/centercell/MASTER.md).

A estrutura segue "mais ou menos" a Viper Cel (mesmo tipo de negócio), mas
com diferenças reais de layout pra não parecer reskin: herói em duas
colunas (não foto de fundo), uma seção nova "Como funciona", a loja em grid
de categorias (não lista + 1 foto), e um card "selo Brasil" destacado nos
diferenciais. Detalhes da comparação também estão no MASTER.md, seção 4.

O conteúdo (endereço, telefone, horário, avaliação, serviços, depoimentos)
veio direto da sua ficha do Google Meu Negócio, que você colou no chat —
nada foi inventado. Os 3 depoimentos são reais, mas sem nome de autor (não
veio na ficha) — por isso aparecem como "Avaliação verificada no Google" com
um ícone de aspas, em vez de um nome/inicial inventado.

## 5. Rodar no seu computador

Precisa de Python (já vem instalado no Windows/Mac na maioria dos casos). Na
pasta do projeto:

```bash
python -m http.server 5179
```

Depois abra `http://localhost:5179` no navegador. (Se você usa o Claude
Code, já existe um atalho configurado em `.claude/launch.json` — é só pedir
pra abrir o preview do "centercel".)

## 6. Mapa dos arquivos

```
index.html              a página
404.html                 página de erro
assets/
  estilo.css              todo o CSS
  logo-lockup.jpg          logo completa (símbolo + wordmark + "importados")
  logo-icon.jpg            só o símbolo, recorte quadrado
  favicon-*.png, apple-touch-icon.png
  compartilhamento.jpg    imagem de preview ao compartilhar o link (WhatsApp etc.)
robots.txt, sitemap.xml   SEO básico
vercel.json, _headers     cabeçalhos de segurança (Vercel e alternativas)
design-system/centercell/ racional de design (não vai pro ar — ver .vercelignore)
PROMPTS-IMAGENS.md        prompts prontos pras fotos pendentes (ver seção 2)
logo.jpg, REFERENCIA.jpg  arquivos originais que você enviou (não vão pro ar)
```

---

**Antes de publicar de vez:** troque `centercel.vercel.app` (aparece em
`index.html`, `sitemap.xml` e `robots.txt`) pelo domínio real, se vocês
usarem um domínio próprio em vez do subdomínio padrão da Vercel.
