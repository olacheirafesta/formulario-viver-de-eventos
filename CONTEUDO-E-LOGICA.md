# Formulário Viver de Eventos · conteúdo e lógica

Aplica o design que já tens a este formulário. 15 ecrãs, um de cada vez, estilo Typeform.
Os textos ficam palavra a palavra. Tudo obrigatório.

---

## 1. inicio
Título: O caminho para *viveres dos eventos* começa aqui.
Texto: Responde a estas perguntas para eu perceber em que momento estás. No fim, mostro-te o passo certo para ti. Demora menos de 2 minutos.
Botão: Começar

## 2. nome · campo de texto (id f-nome)
Como te *chamas*?  ·  placeholder: O teu nome  ·  erro: Escreve o teu nome.

## 3. email · campo email (id f-email)
Qual é o teu *email*?  ·  placeholder: nome@email.com  ·  erro: Escreve um email válido.

## 4. telefone · campo telefone (id f-telefone)
E o teu *telemóvel*?  ·  placeholder: 912 345 678  ·  erro: Escreve um número válido.

## 5. instagram · campo de texto (id f-instagram)
Qual é a tua conta de *Instagram*?  ·  placeholder: @atuaconta  ·  erro: Escreve o teu @.

## 6. divisor · escolha  ← parte o caminho em dois
Já fazes eventos para *clientes*?
- Sim, já tenho negócio de eventos → ramo B (b1)
- Ainda não, estou a começar → ramo A (a1)

---

# Ramo A · está a começar

## a1 · escolha
Gostavas de ser *organizadora* de eventos?
- Sim, é o que eu quero
- Estou a explorar a ideia
(as duas seguem para a2)

## a2 · resposta escrita (id f-a2)
Porque queres criar o teu próprio negócio de eventos? O que isso iria trazer à tua *vida*?
placeholder: Escreve aqui…

## a3 · escolha
O que te impede de *começar*?
- Não sei por onde começar → a4
- Medo de trocar o certo pelo incerto → a4
- Medo de não ter clientes → a4
- Todas as opções anteriores → a4
- Já decidi, só preciso de aprender → a4

⚠ Alterado a 12/09/2026: antes as quatro primeiras iam directas para fim-clube e nunca respondiam ao investimento. Agora **toda a gente passa pelo a4**. Quem responder *neste momento não consigo* é que segue para fim-clube, que é onde a aula gratuita entra.

## a4 · escolha, com texto de apresentação em cima
Título: Estás pronta para *investir* em ti, no teu negócio e na tua nova vida?
Texto: O primeiro passo para viveres de eventos é tornares-te profissional, para entregares um trabalho de qualidade que atrai interessados. Mas isso sozinho não chega. Se queres mesmo viver de eventos, fazer o que gostas, ser bem paga por isso e ter mais tempo para ti enquanto impactas o dia mais importante da vida das outras pessoas, é essencial criares o teu negócio. É assim que sabes qual o preço certo a cobrar e como ter clientes todos os meses. É isso que ensino no CODE, a certificação em organização e decoração de eventos.
- Sim, consigo investir já → fim-code
- Sim, com um plano de pagamento → fim-code
- Sim, mas gostava de ter mais informações → fim-code
- Neste momento não consigo → fim-clube

---

# Ramo B · já tem negócio

## b1 · resposta escrita (id f-b1)
Que tipo de negócio de eventos *tens*?  ·  placeholder: Ex.: organizo casamentos e batizados…

## b2 · escolha
Qual foi a tua *faturação* no último ano?
- Menos de 5.000 €
- Entre 5.000 € e 10.000 €
- Entre 10.000 € e 50.000 €
- Mais de 50.000 €
(todas seguem para b3)

## b3 · resposta escrita (id f-b3)
Qual é o teu maior *objetivo* com o teu negócio de eventos?

## b4 · resposta escrita (id f-b4)
Qual é a maior *dificuldade* que sentes hoje em atingir esse objetivo?

## b5 · escolha, com apresentação da Mentoria
Título: A Mentoria EBS é um acompanhamento de 12 meses com ajuda direta da Adriana e uma comunidade de empreendedoras que *Vivem de Eventos*.
Texto: Análise completa do teu negócio, plano personalizado e acompanhamento da implementação, passo a passo. O investimento é de 5.000 €, com opção de pagamento em prestações.
Pergunta: Consegues fazer este investimento em ti e no teu negócio?
- Sim, a pronto → fim-call
- Sim, em prestações → fim-call
- Neste momento não → fim-clube

---

# Ecrãs finais

## fim-call · agenda
Título: Escolhe o dia da nossa *conversa*.
Texto: Recebi a tua candidatura. Marca já o dia e a hora que te dão mais jeito. No fim recebes um convite para adicionares a marcação ao teu calendário (Google, iPhone ou Android).
Embed inline do Calendly numa div id="agenda". Precisa de espaço largo e alto, sobretudo no telemóvel.

## fim-code
Título: O CODE é o caminho *certo* para ti.
Texto: É a certificação da EBS para começares o teu negócio de eventos do zero.
Botão id="cta-code": o texto e o destino mudam por script.
- quem disse que consegue investir → "Escolher como pagar", olacheirafesta.github.io/code/escolher.html
- quem pediu informações → "Conhecer o CODE", olacheirafesta.github.io/code

## fim-clube
Monograma EBS em cima.
Título: Começa por *aqui*.
Texto: 1. Entra no Clube Viver de Eventos, é gratuito. 2. Lá dentro, assiste à masterclass "Por onde começar". Quando terminares, envia-me mensagem por lá se tiveres alguma dúvida. Vou-te ajudar rumo a viver de eventos.
Botão: Entrar no Clube gratuito → clube-viver-de-eventos.circle.so/c/comeca-aqui

---

# Elementos de interface que existem em todos os ecrãs
- Barra de progresso fina no topo (o total ronda os 11 ecrãs por caminho).
- Monograma EBS fixo no canto superior esquerdo.
- Botão de voltar fixo em baixo à direita. Não aparece no ecrã de entrada nem nos finais.
- Nos ecrãs de campo: botão OK e a dica "Enter ↵" ao lado, escondida no telemóvel.
- Cada campo tem uma linha de erro por baixo, escondida até fazer falta.
- Transição entre ecrãs: o que sai desliza para cima e desaparece, o que entra sobe e aparece.

# O que não pode partir
Um único ficheiro index.html, CSS embutido, sem frameworks nem JavaScript de CDN.
Cada ecrã é uma section com data-id igual aos nomes acima. Os ids dos campos mantêm-se: f-nome, f-email, f-telefone, f-instagram, f-a2, f-b1, f-b3, f-b4.
A lógica de ramos, os POST para ebs-webhooks.vercel.app e os links não se tocam.
Mobile primeiro: é aí que quase toda a gente responde.
