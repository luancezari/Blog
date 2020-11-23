---
date: "2020-11-22"
draft: false
featured: false
diagram: true
image:
  placement: 1
math: true
categories:
- doubleL
commentable: true

title: Double L Dia 0 - Long & Short
---


  Hoje dou início ao projeto. A ideia desse blog, que eu já vinha carregando a um tempo, é compartilhar tudo o que eu produzir e achar que vale a pena ser compartilhado sobre ciência de dados e mercado. Esse será o meu primeiro projeto, o Double L.

  Pretendo usar esse projeto de Long & Short como um diário de desenvolvimento onde compartilharei todo o processo de desenvolvimento de um modelo de algotrading que, pelo menos a princípio, pretendo utilizar para gerir meu próprio capital. Minha grande motivação por trás desse diário é citá-lo como referência para que os membros da Liga de Controladoria e Finanças da UFMG (onde sou presidente) tenham um norte ao embarcarem no desafio de desenvolver seus próprios modelos no próximo semestre. Enfim, vamos lá.

## O LONG & SHORT

  Antes de mais nada creio que será necessário explicar como um Long & Short funciona. A estratégia de Long & Short consiste em uma operação casada onde de um lado faz-se uma venda a descoberto de um ativo e do outro uma compra. A estrutura dessa estratégia trás consigo algumas vantagens que justificam a sua popularidade.

  Para começar, quando se faz uma operação de venda a descoberto você precisa alugar uma ação que você não tem e vendê-la para, no futuro, recomprá-la (idealmente por um preço mais alto) e lucrar com a variação. Ao realizar o aluguel sua corretora depositará na sua conta uma quantia em dinheiro igual ao volume financeiro tomado emprestado, ou seja, **A CORRETORA TE DARÁ CAIXA** (ao menos provisoriamente). Você pode fazer o que quiser com esse caixa enquanto mantiver a posição vendida, inclusive utilizar esse dinheiro para comprar ações, montando sua posição long.

  Naturalmente a corretora não te permitirá fazer empréstimos infinitos para obter caixa infinito e comprar investimentos infinitos (afinal, nenhuma corretora quer quebrar por causa de um cliente). Em troca de te fornecer o caixa a corretora exigirá na operação que você mantenha uma certa quantidade de dinheiro ou ativos lastreados para garantir que, em uma situação limite, você conseguirá devolver o dinheiro que lhe foi emprestado e recomprar as ações que foram vendidas, essa quantia é chamada de **MARGEM DE GARANTIA**.

  O ponto positivo da margem de garantia é que ela não precisa ser composta necessariamente de dinheiro. Você utiliza ativos financeiros que você tem comprado, incluindo os ativos comprados com o caixa empestado, o que é a regra nesse tipo de operação. Quando colocar o ativo comprado em garantia, naturalmente, ele não valerá o que valeria se fosse vendido imediatamente no mercado. A corretora corre um risco nesse tipo de operação pois se for necessário liquidar o seu investimento para cobrir a venda o a corretora pode sofrer slippage, o que levaria a prejuízos para a instituição. Em razão disso, as corretoras descontam um deságio (cuja fórmula que o define não é explicitamente comunicada) que fornece pra elas uma margem de segurança e precisa ser coberta com seu próprio capital.

  A vantagem que tem que ser observada nisso tudo é que o valor necessário a ser depositado é **INFERIOR** ao valor total do ativo comprado e do ativo vendido, ou seja, você consegue dessa forma alavancar seus ganhos (e suas perdas).

  Outra característica importante do Long & Short que precisa ser destacada é que é possível lucrar mesmo com o mercado em queda pois o que interessa é que a sua posição comprada (long) performe melhor do que a sua posição vendida (short).

  Imagine os seguintes exemplos simples:

  Se seu ativo long subir 3% e seu ativo short cair 2% você ganha 5% na operação (vezes a alavancagem).
  
  {{< figure src="ganholongeshort.jpg" title="Ganho em ambas as pontas" >}}
  
  Se seu ativo long subir 7% e seu ativo short subir 2% você ganha 5% na operação (vezes a alavancagem).
  
  {{< figure src="ganholong.jpg" title="Ganho na ponta long" >}}
  
  Se seu ativo long cair 3% e seu ativo short cair 8% você ganha (advinha) 5% na operação (vezes você sabe o que).
  
  {{< figure src="ganhoshort.jpg" title="Ganho na ponta short" >}}

  Essa foi uma explicação introdutória ao projeto que pretendo iniciar e aos fundamentos de como funciona uma operação Long & Short. No próximo post iniciarei o desenvolvimento do modelo.