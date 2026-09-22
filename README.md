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

**Completo**, nove páginas: composição dos pavimentos, alternativas de
adensamento, verificação de conformidade item a item com o dispositivo de
cada exigência, estudos e licenças incidentes, vagas de estacionamento,
quadro de parâmetros, memória de cálculo das três relações da lei, o que
não conta nos parâmetros, o que cabe no afastamento frontal, peças gráficas,
alertas e premissas.

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
