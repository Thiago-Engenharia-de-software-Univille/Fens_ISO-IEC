# Como funciona

O projeto tem três páginas, todas em HTML puro, sem instalação e sem servidor: basta abrir no navegador.

| Página | Para quê |
|---|---|
| `index.html` | Apresentação de slides |
| `trabalho.html` | Trabalho escrito, pronto para imprimir ou gerar PDF |
| `download.html` | Página para baixar o PDF do trabalho |

## O tema

A apresentação imita um computador dando boot por um CD. Cada assunto é uma "imagem `.iso`" que é montada. **É só um trocadilho**: imagens de disco usam a extensão `.iso` por causa da norma ISO 9660, do CD-ROM. O conteúdo do trabalho são as normas ISO/IEC de qualidade de software. O slide 3 explica isso para a turma.

| Tipo de tela | Aparência | Onde aparece |
|---|---|---|
| BIOS | Tela preta de console | Capa (slide 1) |
| Menu de boot | Lista de imagens para escolher | Roteiro (slide 2) |
| Montagem | Terminal executando `mount` e um título gigante | Abertura de cada seção |
| Instalador | Janela cinza sobre fundo azul, com `< Voltar >` `< Continuar >` | Slides de conteúdo |
| Desligamento | `shutdown -h now` | Referências e encerramento |

Cada seção tem uma cor:

| Imagem | Seção | Cor | Variável CSS |
|---|---|---|---|
| `siglas.iso` | ISO, IEC e ABNT | Ciano | `--c1` |
| `normas.iso` | As seis normas | Amarelo | `--c2` |
| `square.iso` | Modelos de qualidade (ISO/IEC 25000) | Verde | `--c3` |
| `ciclo.iso` | Qualidade no ciclo de vida | Laranja | `--c4` |
| `conceitos.iso` | Qualidade interna, externa e em uso | Rosa | `--c5` |

## Controles

| Tecla / ação | O que faz |
|---|---|
| `→`, `Espaço`, `PageDown`, `Enter` | Avança |
| `←`, `PageUp`, `Backspace` | Volta |
| `↑` / `↓` | Rola a janela, se o conteúdo não couber na tela |
| `Home` / `End` | Primeiro / último slide |
| `M` | Menu de boot (roteiro) |
| `F` | Tela cheia |
| No menu de boot: `↑` `↓` e `Enter` | Escolhe uma seção e pula para ela |
| Botões `< Voltar >` / `< Continuar >` | Navegam pelos slides de conteúdo |
| Clique numa tela preta | Avança |
| Deslizar o dedo para o lado (celular) | Avança ou volta |

Passadores de slides (clickers) funcionam, porque enviam `PageUp` e `PageDown`. O número do slide fica no endereço: `index.html#12` abre direto no slide 12.

## Responsividade

A apresentação ocupa a tela inteira, sem faixas pretas, em qualquer proporção.

- Todos os tamanhos (texto, espaçamentos, bordas) usam a unidade `--u`, que vale 1% da largura de um quadro 16:9 que cabe na tela. Num notebook 1366×768 o texto fica proporcional ao de um monitor 1920×1080 ou de um projetor.
- O texto tem tamanho mínimo (15 px), para continuar legível em telas pequenas.
- Em telas estreitas (celular, janela pequena ou tela em pé), as colunas viram uma só, as tabelas empilham e as dicas de teclado somem.
- Se o conteúdo de um slide não couber, a janela ganha rolagem própria; os botões `< Voltar >` `< Continuar >` ficam sempre visíveis.

Testado em 1366×768, 1024×768, 1920×1080, 2560×1080 e 390×844 (celular).

## Estrutura do `index.html`

Cada slide é uma `<section class="slide">`. Só o slide com a classe `on` aparece.

### Slides de conteúdo (`class="slide chrome"`)

Você escreve só o conteúdo. O JavaScript monta em volta a janela do instalador, as barras de cima e de baixo, os botões e a barra de progresso. Atributos:

| Atributo | Para que serve |
|---|---|
| `data-img="normas.iso"` | Nome da imagem na barra de cima |
| `data-cmd="ls -l /mnt/normas"` | Comando mostrado no canto direito da barra de cima |
| `data-tt="Título"` | Título no topo da janela |
| `data-next="Desligar"` | Texto do botão de avançar (padrão: "Continuar") |
| `data-id="normas"` | Nome do slide, usado pelo menu de boot |
| `style="--acc:var(--c2)"` | Cor da seção |

### Telas de console (`data-crt`)

Capa, aberturas de seção e encerramento. Toda linha com a classe `ln` aparece em sequência, como um terminal imprimindo. Quem ativa "reduzir movimento" no sistema vê tudo de uma vez.

### Peças prontas para o conteúdo

- `<h2>` título, `<h3>` subtítulo, `<p>` parágrafo, `<p class="small">` nota
- `<div class="cols c2">` ou `c3`: duas ou três colunas
- `<div class="kv">`: linha "chave ........ valor"
- `<table class="ls">`: lista em tabela
- `<div class="note">`: destaque com barra vermelha
- `<div class="box">`: caixa com borda (`box core` = caixa preta de destaque)
- `<ol class="steps">`: passos numerados
- `<span class="chip prod|proc|in|ex|us">`: etiquetas produto, processo, interna, externa, em uso

### Como adicionar um slide

Copie uma `<section class="slide chrome" ...>` inteira, cole onde quiser e troque o conteúdo. A numeração e a barra de progresso se ajustam sozinhas. Para criar um atalho no menu de boot, dê um `data-id` ao slide e acrescente uma linha `<li><button data-goto="...">` no slide 2.

## Trabalho escrito e PDF

`trabalho.html` contém o trabalho completo com capa, sumário, seções numeradas, quadros e referências. A formatação segue a ABNT para impressão: folha A4, margens de 3 cm (superior e esquerda) e 2 cm (inferior e direita), fonte Times New Roman 12, espaçamento 1,5, recuo de parágrafo de 1,25 cm e número da página no canto superior direito (a capa não é numerada).

Para gerar o PDF de novo depois de editar o texto:

- **Pelo navegador:** abra `trabalho.html`, `Ctrl+P`, destino "Salvar como PDF", desmarque "Cabeçalhos e rodapés" e salve como `FENS_Trabalho_ISO-IEC.pdf`.
- **Pelo terminal (Chrome):**
  ```
  google-chrome --headless --no-pdf-header-footer --print-to-pdf=FENS_Trabalho_ISO-IEC.pdf trabalho.html
  ```

Depois, atualize o tamanho e o número de páginas em `download.html` e recrie o `.zip` (veja abaixo).

Limitação: o sumário não mostra números de página, porque o HTML não calcula em que página cada seção cai.

## Slides em PDF

O `index.html` tem um modo de impressão: cada slide vira uma página 16:9, sem botões nem animação. Para gerar `FENS_Slides_ISO-IEC.pdf` de novo depois de editar os slides:

- **Pelo navegador (Chrome):** abra `index.html`, `Ctrl+P`, destino "Salvar como PDF", desmarque "Cabeçalhos e rodapés" e marque "Gráficos de plano de fundo".
- **Pelo terminal:**
  ```
  google-chrome --headless --no-pdf-header-footer --virtual-time-budget=5000 --print-to-pdf=FENS_Slides_ISO-IEC.pdf index.html
  ```

## Página de download

`download.html` usa o mesmo visual de instalador e oferece:

- o **trabalho escrito** em PDF (`FENS_Trabalho_ISO-IEC.pdf`);
- os **slides** em PDF (`FENS_Slides_ISO-IEC.pdf`);
- **os dois juntos** num `.zip` (`FENS_ISO-IEC_PDFs.zip`).

Os botões usam o atributo `download`, então o navegador salva o arquivo em vez de abri-lo. Cada PDF também tem um link para abrir em nova aba. O último slide da apresentação tem um link para essa página.

Depois de gerar os PDFs de novo, recrie o `.zip` (`zip -j FENS_ISO-IEC_PDFs.zip FENS_Trabalho_ISO-IEC.pdf FENS_Slides_ISO-IEC.pdf`) e atualize tamanhos e número de páginas no `download.html`.

Abrindo direto do disco (`file://`), alguns navegadores ignoram o atributo `download` e abrem o PDF. Hospedado (por exemplo, no GitHub Pages), o download funciona normalmente.

## Dependências

- Fontes do Google Fonts: **VT323** (títulos pixelados) e **IBM Plex Mono** (texto). Sem internet, o navegador usa uma fonte monoespaçada padrão e tudo continua funcionando.
- Nenhuma biblioteca JavaScript.

## Antes de apresentar e entregar

- Teste a apresentação no computador e no projetor da sala, em tela cheia (`F`).
- Nas referências de sites, acrescente o "Acesso em: dia mês. ano." exigido pela NBR 6023, no `trabalho.html` e no último slide.
- Confira datas e números com as fontes oficiais, principalmente "+170 países" da ISO.
