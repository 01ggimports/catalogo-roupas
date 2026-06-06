# 🛍️ Catálogo de Roupas — Guia Completo

Site de encomendas de roupas. Os clientes abrem pelo celular, escolhem a peça e o tamanho, e o pedido vai direto pro WhatsApp.

---

## 📁 Estrutura do repositório

```
catalogo-roupas/
├── index.html        ← o site (não mexa aqui)
├── README.md         ← este guia
└── fotos/
    ├── vestido-linho-midi.jpg
    ├── blusa-cropped-rib.jpg
    └── ... (todas as fotos aqui)
```

---

## 📸 Como adicionar fotos

### Pelo navegador (mais fácil, sem instalar nada):

1. Acesse **github.com** e entre no repositório
2. Clique na pasta **`fotos/`**
3. Clique em **"Add file" → "Upload files"**
4. Arraste todas as fotos de uma vez
5. Clique em **"Commit changes"**

> ✅ O site atualiza automaticamente em ~1 minuto!

### Nomes dos arquivos de foto

Cada produto no site já tem um nome de arquivo esperado. Use exatamente esses nomes:

| Produto | Nome do arquivo |
|---|---|
| Vestido Linho Midi | `vestido-linho-midi.jpg` |
| Blusa Cropped Rib | `blusa-cropped-rib.jpg` |
| Calça Cargo Wide | `calca-cargo-wide.jpg` |
| Camiseta Oversized | `camiseta-oversized.jpg` |
| Shorts Linho Masc. | `shorts-linho-masculino.jpg` |
| Vestido Floral Plus | `vestido-floral-plus.jpg` |
| Conjunto Alfaiataria | `conjunto-alfaiataria.jpg` |
| Camisa Social Slim | `camisa-social-slim.jpg` |
| Saia Midi Plissada | `saia-midi-plissada.jpg` |
| Moletom Oversized | `moletom-oversized.jpg` |

> 💡 **Dica:** Se a foto não existir ainda, o site mostra um emoji no lugar. Não quebra nada.

### Recomendações para as fotos:
- Formato: **JPG ou PNG**
- Proporção ideal: **3:4** (retrato) para o catálogo, ex: 900x1200px
- Tamanho: tente manter abaixo de **500KB** por foto (use [squoosh.app](https://squoosh.app) pra comprimir de graça)

---

## ➕ Como adicionar um produto novo

Abra o arquivo `index.html`, procure o trecho `const PRODUCTS = [` e adicione um bloco novo seguindo este modelo:

```js
{
  id: 11,                              // número único, sempre maior que o anterior
  name: "Nome da Peça",               // nome que aparece no site
  category: "feminino",               // feminino | masculino | vestido | casual | plus
  price: 99.90,                       // preço em reais
  emoji: "👗",                        // emoji de fallback se não tiver foto
  img: "fotos/nome-do-arquivo.jpg",   // foto na pasta fotos/
  desc: "Descrição da peça aqui.",    // texto que aparece ao abrir o produto
  sizes: ["PP","P","M","G","GG"],     // tamanhos disponíveis
  unavailable: ["PP"],                // tamanhos esgotados (deixa [] se tiver tudo)
  badge: "Novo"                       // etiqueta (Novo, Destaque, etc.) ou null
},
```

---

## ✏️ Mudar preço ou info de um produto

1. Abra `index.html` no GitHub
2. Clique no ✏️ lápis (editar)
3. Procure o produto pelo nome (`Ctrl+F`)
4. Edite o campo desejado (`price`, `sizes`, `unavailable`, etc.)
5. Clique em **"Commit changes"**

---

## 📵 Marcar tamanho como esgotado

No produto desejado, adicione o tamanho no campo `unavailable`:

```js
unavailable: ["PP", "GG"],  // esses dois ficam bloqueados no site
```

---

## 📱 Como ativar o GitHub Pages (site no ar)

1. No repositório, clique em **Settings**
2. No menu lateral, clique em **Pages**
3. Em "Branch", selecione **main** e clique em **Save**
4. Aguarde ~1 minuto
5. O link do site vai aparecer no topo da página de Pages

**Link do site:** `https://SEU-USUARIO.github.io/catalogo-roupas/`

---

## 📲 Mudar o número do WhatsApp

No `index.html`, procure essa linha:

```js
const WHATSAPP_NUMBER = "5511999999999";
```

Troca pelo número com DDI (55) + DDD + número, sem espaços ou traços.

---

## ❓ Dúvidas frequentes

**O site não atualizou depois que subi as fotos.**
> Aguarda 1-2 minutos e recarrega a página. Às vezes o GitHub demora um pouco.

**A foto não aparece.**
> Confere se o nome do arquivo está igual ao que está no `index.html`, incluindo letras minúsculas e sem acento.

**Quero usar PNG em vez de JPG.**
> Pode! Só lembra de mudar a extensão no `img:` do produto também. Ex: `img: "fotos/vestido.png"`
