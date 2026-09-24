# Simulador de Envoltória Máxima Edificável — São João da Barra/RJ

Ferramenta de consulta prévia de viabilidade construtiva. Escolha a zona no
mapa, desenhe o lote e empilhe os pavimentos: o simulador aplica os parâmetros
do Plano Diretor, da Lei de Uso, Ocupação e Parcelamento do Solo e do Código de
Obras e Edificações, aponta as desconformidades e emite relatório em PDF com
planta de implantação, corte esquemático e volumetria.

**Não substitui a análise da Prefeitura.** O estudo é anterior ao projeto e
serve como base de informações para ele.

## Como usar

1. Clique numa zona do mapa ou escolha na lista da aba **Entrada**.
2. Informe testada e profundidade, ou desenhe o polígono do lote e marque as
   testadas.
3. Monte a pilha de pavimentos de baixo para cima, com posição, ocupação e
   pé-direito.
4. Leia o veredito e a verificação de conformidade na aba **Resultado**.
5. Use **Gerar relatório para impressão / PDF** para emitir o documento em A4.

Há também busca por endereço e por coordenadas (`-21,6395 -41,0505`), que
funciona sem rede.

## Dois escopos de relatório

A caixa que se abre antes de imprimir oferece duas saídas do mesmo estudo,
com os mesmos dados e a mesma ressalva.

**Completo**, dez páginas: composição dos pavimentos, alternativas de
adensamento, verificação de conformidade item a item com o dispositivo de
cada exigência, estudos e licenças incidentes, vagas de estacionamento,
quadro de parâmetros, memória de cálculo das três relações da lei, o que
não conta nos parâmetros, o que cabe no afastamento frontal, a legenda do
Anexo II com as seis notas transcritas, peças gráficas, alertas e premissas.

**Síntese**, quatro páginas: ficha, veredito, quadro de parâmetros com a
linha de vagas, apenas os itens que não atendem ou trazem condicionante,
alertas e peças gráficas. Ela se declara extrato logo abaixo da ficha, para
que a ausência de um item não se leia como ausência de exigência.

## Dois modos de estudo

**Envoltória máxima**, o padrão: a projeção é o menor valor entre a envoltória
dos afastamentos, a taxa de ocupação e o lote menos a permeabilidade mínima. O
indicador diz qual dos três amarrou — em lote pequeno costuma ser a envoltória,
e aí a taxa de ocupação resultante fica abaixo da permitida pela lei.

**Perímetro desenhado**: em **Desenhar edificação** você traça a forma da
edificação dentro do lote, com o limite dos afastamentos visível como guia. A
partir de três pontos, essa forma passa a ser a projeção do estudo — área,
taxa de ocupação, áreas por pavimento, Coeficiente de Aproveitamento e volume
saem dela, as três peças gráficas desenham a forma de verdade, e a taxa de
ocupação e a envoltória voltam a poder reprovar. Apagar o desenho volta ao
cálculo da envoltória máxima.

## Encostar na divisa

Ao lado do desenho do lote há um check por lado. Cada lado é classificado
como testada, lateral ou fundos, e o check só fica disponível onde a lei
dispensa o afastamento: a nota (2) do Anexo II libera qualquer divisa que
não seja testada para uso não residencial, misto, hotel e similares e para
o pavimento de uso comum exclusivo em multifamiliar; a nota (3) dispensa
uma lateral nas tipologias residenciais. Onde o check está travado, o
motivo aparece escrito nele.

A dispensa alcança o 1º e o 2º pavimentos acima do solo. Marcar um lado
refaz o modelo inteiro: o embasamento ganha a projeção maior, a torre
mantém a sua, e as três peças gráficas saem escalonadas. O quadro de
pavimentos traz a coluna **Projeção** dizendo de qual das duas cada piso
tira a área.

Quando a taxa de ocupação ou a permeabilidade cortam a envoltória do
embasamento, a redução **não** é homotética. A testada nunca cede — o
afastamento frontal é mínimo legal e aumentá-lo só empurra a edificação
para o fundo do lote. A folga sai, nesta ordem: dos lados que já são
recuo, depois do fundo — ainda que tenha sido escolhido, porque encurtar
a edificação e deixar quintal é o que um projeto faz —, depois das
laterais encostadas. A divisa que deixa de ser alcançada sai do desenho
e é declarada em alerta.

**A torre se apoia no embasamento.** Onde o embasamento recuou, a torre
recua junto: nenhum pavimento avança além da base que o sustenta. Isso
tem consequência de conta — em edificação alta, encostar pode reduzir a
área total, porque dois pavimentos mais largos não pagam cinco mais
estreitos. O simulador mantém a escolha marcada e informa quanto ela
custa, com o número do estudo sem encostar ao lado.

Nas peças gráficas a parede na divisa aparece como massa cheia: faixa
preenchida na planta, ao longo da extensão real da edificação; massa e
traço reforçado na face correspondente da volumetria, com o lote
desenhado como placa cuja borda é a divisa; e faixa junto à linha de eixo
no corte. A volumetria abre com a câmera na rua, à frente da testada, que
é de onde se vê ao mesmo tempo a divisa encostada e a frente recuada;
girar o desenho passa o controle da câmera ao usuário.

## Os dois sentidos do corte

O corte tem dois sentidos, à escolha, e o relatório completo traz os dois.

**Transversal**, plano paralelo à testada: as duas divisas laterais
aparecem uma em cada extremo. É o sentido em que se veem a parede na
divisa lateral e o recuo da torre sobre o embasamento.

**Longitudinal**, perpendicular à testada: a via de um lado, a divisa de
fundos do outro. É o sentido em que se veem o afastamento frontal, a
profundidade da edificação e o que resta de quintal.

Em qualquer dos dois, a largura de cada pavimento é a extensão real do
seu contorno medida naquela direção — não é esquema proporcional à área.
Cada extremo é nomeado pelo que é: testada, divisa lateral ou divisa de
fundos.

As notas (1), (4), (5) e (6) do Anexo II também entram no cálculo: a
outorga onerosa eleva o gabarito, o volume técnico e a casa de máquinas
não contam no número de pavimentos, hotel e similares têm regime próprio
na ZM1, e o subsolo segue a nota (6).

## O que a ferramenta verifica

Coeficiente de Aproveitamento (art. 25, I e art. 26), taxa de ocupação,
taxa de permeabilidade, afastamentos, gabarito e altura, pé-direito mínimo dos
compartimentos, uso admitido na zona, área e testada mínimas do modelo de
parcelamento, vagas de estacionamento e as exigências de EIV, RIV,
licenciamento ambiental e elevador.

A permeabilidade entra como **mínimo reservado**, não como taxa calculada: o
relatório informa ao lado a **área livre do lote** que de fato resulta da
projeção, que costuma ser bem maior que o mínimo e só conta como permeável
conforme o tratamento de piso do art. 27.

O quadro de parâmetros tem duas colunas de papéis distintos: **Estudo**, com o
que o cálculo produziu, e **Estipulado em lei**, com a regra tal como está
escrita — valor derivado da lei não entra ali. Onde os dois coincidem, é porque
a envoltória máxima encostou no limite. Onde a lei não fixa parâmetro, o
relatório declara a lacuna em vez de estimar um valor.

## O que o relatório informa além do cálculo

- **Como se calcula** — as relações do art. 25 escritas como fração, com os
  números do estudo em curso no lugar de um exemplo fixo.
- **O que não conta nos parâmetros** — as exclusões do Coeficiente de
  Aproveitamento (art. 26), da taxa de permeabilidade (art. 27), e as do
  Código de Obras que valem em todo o Município: piscina descoberta (art. 221),
  pergolados (art. 161 a 164) e placas fotovoltaicas (art. 205 a 207). Só na
  Zona de Desenvolvimento Econômico entra a relação dos arts. 110 e 111.
- **O que cabe no afastamento frontal** — os sete incisos do art. 28.

## Divergências registradas

A aba **Base legal** lista as divergências encontradas entre o arquivo de
zoneamento, o texto da lei e os anexos. Entre elas, duas de interpretação:
o sentido do verbo no art. 27, que o material didático da Prefeitura aplica
invertido, e a relação de exclusões da taxa de ocupação, geral na lei anterior
e restrita à ZDE na vigente. Nenhuma foi resolvida pela ferramenta — estão
registradas para encaminhamento ao Município.

## Base legal

- Plano Diretor de Desenvolvimento Sustentável
- Lei de Uso, Ocupação e Parcelamento do Solo
- Código de Obras e Edificações
- Código de Posturas
- Plano de Mobilidade Urbana

Origem do dado espacial: Anexo III (zoneamento urbano) — arquivo KMZ fornecido
pelo Município.

## Técnico

Arquivo único, sem dependências externas. Leaflet e o zoneamento em GeoJSON
estão embutidos; abre offline, e só as imagens de satélite do mapa de fundo
precisam de conexão. Para publicar, basta servir `index.html` como página
estática.

## Autoria

NEPLAN — Núcleo de Engenharia em Planejamento e Infraestrutura Urbana
Universidade Federal de Viçosa · neplan@ufv.br
