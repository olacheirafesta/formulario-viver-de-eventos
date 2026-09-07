# Formulário Viver de Eventos · brief para redesenho visual

**Ficheiro a redesenhar:** `formulario-viver-de-eventos/index.html` (página única, sem build, sem dependências)
**Live:** candidatura.eventbusinessschool.pt (GitHub Pages, `.nojekyll`, CNAME)
**Assets na pasta `assets/`:** `entrada.jpg` (fotografia de fundo), `monogram-black.png` (monograma EBS, PNG preto transparente)

## O que se pede
Só o visual. A estrutura de ecrãs, a lógica de ramos, os ids dos campos, os endpoints e os links mantêm-se exactamente como estão.

## Identidade (fonte de verdade: marca/guia.html + marca/tokens.css)
- Fundos possíveis: branco #FFFFFF com texto preto · fotografia com texto branco (a sombra só aqui) · cor cheia com texto branco. Nunca bege, marfim ou creme.
- Playfair Display 400 nos títulos, numerais e citações. Nunca negrito. Ênfase por itálico.
- Red Hat Display 400 no corpo (17 a 19 px), nas legendas (12 px, maiúsculas, 0.28em) e nos botões.
- Breathing (manuscrito) só numa palavra ou frase curta por composição, em linha própria.
- A cor vive dentro da fotografia e no manuscrito. Fora daí quase não aparece.
- Sem gradientes coloridos, sombras dramáticas, dourado, molduras, ícones, círculos, réguas grossas. Sem travessões na copy.
- Um logótipo por peça.

## Estado actual (o que existe hoje e pode mudar)
- `body` arranca com a classe `dark`: fotografia `entrada.jpg` em fundo fixo com véu escuro em gradiente, texto claro.
- Tipografia: Playfair 500 nos títulos (deve passar a 400) e Helvetica no corpo (deve passar a Red Hat Display). As fontes não estão sequer carregadas na página.
- Botão primário `.btn` preto, maiúsculas, 0.06em. Opções `.opt` com moldura fina. Inputs sem caixa, só linha inferior.
- Barra de progresso de 3 px no topo, botão de voltar fixo em baixo à direita.
- Transições: cada ecrã entra com fade e sobe 26 px.

## Estrutura de ecrãs (não mexer)
Cada ecrã é `<section class="step" data-id="...">`.

Comuns: `inicio` · `nome` · `email` · `telefone` · `instagram` · `divisor`
Ramo A, está a começar: `a1` · `a2` (texto livre) · `a3` · `a4`
Ramo B, tem negócio: `b1` (texto livre) · `b2` · `b3` (texto livre) · `b4` (texto livre) · `b5`
Finais: `fim-call` (embed Calendly) · `fim-code` · `fim-clube`

Ecrãs de escolha usam `<button class="opt">`. Ecrãs de campo usam `input#f-nome`, `#f-email`, `#f-telefone`, `#f-instagram` e `textarea#f-a2`, `#f-b1`, `#f-b3`, `#f-b4`. Cada um tem um `.err` para a mensagem de erro. Navegação em `.nav` com `.btn` e `.enter` (a dica "Enter").

## Regras técnicas
- Toda a lógica está no `<script>` inline no fim do ficheiro. Não tocar: `go()`, `next()`, `valida()`, `txt()`, `impede()`, `fim()`, `voltar()`, `track()`.
- Os `onclick` inline nos botões têm de continuar a existir tal como estão.
- Endpoints POST: `ebs-webhooks.vercel.app/api/funil-evento` (eventos) e `/api/candidatura` (candidatura).
- Calendly: `calendly.com/cheirafesta/sessao-individual`, embed inline no ecrã `fim-call`.
- Links finais: CODE `olacheirafesta.github.io/code` e `/code/escolher.html` (o script troca o href e o texto do `#cta-code` conforme a resposta ao investimento); Clube `clube-viver-de-eventos.circle.so/c/comeca-aqui`.
- Um único ficheiro HTML, CSS embutido, sem frameworks nem CDN de JS. Fontes por Google Fonts; Breathing é ficheiro local (licença comercial ainda por comprar, por isso deixar fallback).
- Tem de funcionar bem no telemóvel: é aí que quase toda a gente responde.

## Textos
Os textos aprovados estão em `TEXTOS.md`, na mesma pasta. Manter palavra a palavra.
