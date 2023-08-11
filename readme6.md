Olá. Este é o meu resumo do dia 6 da primeira Sprint da minha trilha de aprendizado sobre QA com AWS enquanto estou estagiando pela Compass.uol



# FUNDAMENTOS DE TESTE DE SOFTWARE

Porque é tão importante testar e como isso influencia no ciclo de vida do software 

## Ciclo de Desenvolvimento

O ciclo de desenvolvimento começa com o planejamento do projeto, como na fase de Captura de Requisitos. A partir deste momento nós já começamos a planejar os nossos testes, aqui nós já começamos a pensar em que tipo de metodologia, técnica e testes iremos aplicar dentro do projeto para uma melhor entrega de qualidade do projeto.

Conforme o projeto irá andando em questão de desenvolvimento, os testes também irão andando junto.

Durante a fase de Análise de projeto nós também já iremos projetar os testes.

Enquanto o time de desenvolvimento está construindo e implementando o projeto, nós também podemos começar a implementar os testes projetados e, em paralelo com o time de desenvolvimento, confome builds vão sendo completadas, nós vamos executando testes em cima dessas funcionabilidades que vão sendo construídas.



# PIRÂMIDE DE TESTES

## TESTES UNITÁRIOS

estes testes estão na base da pirâmide de testes.
O que é um teste unitário? Ele é visto como um método público em uma classe mas, pode ser visto também como um conjunto de classes, métodos ou objetos interagindo entre si.

Os testes unitários verificam o funcionamento da menor unidade de código testada da nossa aplicação, independente da interação dela com outras partes do nosso código, ou seja, a gente não precisa de ter o código completo para fazer um teste unitário.

## TESTES DE INTEGRAÇÃO

O teste de integração avalia a funcionabilidade de vários módulos, quando integrados, para formar uma única unidade. Este teste valida a transição suave entre vários componentes integrados em um software. Então, o objetivo do teste de integração é encontrar defeitos e falhas entre várias interfaces do software.

## TESTES E2E (END TO END)

São os testes de ponta a ponta, ou seja, que simulam o ambiente real. Então vc vai desde o início até o final do seu projeto testando as funcionabilidades, se elas estão funcionando corretamente, como se um usuário estivesse utilizando o software.

## EXEMPLO DE CICLO DE TESTE E2E (Caso de uso em um e-commerce):

**- Cadastrar**
**- Escolher item**
**- Calcular frete**
**- Sacola**
**- Pagamento**
**- Finalizar pedido**
**- Informações do pedido**
**- Boleto**
**- Meus pedidos**

**VOLTANDO PARA A PIRÂMIDE DE TESTES, É IMPORTANTE SEMPRE LEMBRAR QUE A BASE DA PIRÂMIDE É MAIS FÁCIL DE FAZER E MAIS RÁPIDA PARA RODAR, ENQUANTO O TOPO É MAIS DIFÍCIL E LENTO.**
Com isso em mente a pirâmite nos mostra a importância de que a maior parte do seu código seja coberto por testes de unidade, já que eles rodam muito rápido e são muito simples (de fazer e manter).

Já o nível de teste mais complexo e demorado (os de ponta a ponta) deve possuir menos testes (assim o deploy não fica travado por mais de 1h enquanto os testes estão sendo rodados).

Os tetes de integração existem para os cenários que não podem ser cobertos por testes de ponta a ponta, e para cenários que os testes de unidade já cobrem muito bem (até porque não é necessário ter testes redundantes). Nessa lógica,  temos menos testes de integração que de unidade, e (bem) menos testes de ponta a ponta que de integração
