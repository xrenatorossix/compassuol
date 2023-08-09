Olá. Este é o meu resumo do dia 5 da primeira Sprint da minha trilha de aprendizado sobre QA com AWS enquanto estou estagiando pela Compass.uol



A IMPORTÂNCIA DOS TESTES X DANO DOS BUGS

A importãncia dos testes está intimamente relacionada com os danos dos bugs. Por que alguém contrataria um especialista de qualidade de testes se não fosse algo crucial para milhares de negócio no mundo e por que o teste se tornou, então, algo tão importante nos últimos anos? Tudo isso é um reflexo dos danos que os defeitos são capazes de causar na vida das pessoas e no cotidiano das empresas.

Então vamos resumir, de uma forma simples e direta, os problemas que os defeitos são capazes de gerar.

Para empresas e organizações os defeitos se refletem em atrasos na entrega de produtos e serviços, gerando problemas como prejuízos financeiros e de imagem como perda de confiança por parte dos clientes e, consequentemente, perda de vendas. Pior do que o prejuízo financeiro é o prejuízo de imagem, pois, prejuízo financeiro é um prejuízo que você perde agora, mas de imagem é um prejuízo que você perde agora e no futuro.

Para governos os defeitos se refletem em vulnerabilidade de informações, decisões estratégicas incorretas e até mesmo derrotas militares.

Para pessoas, bugs e erros podem se refletir em constrangimentos, perda ou supressão de seus direitos, risco de vida e até acidentes.

Erros e defeitos também podem se refletir em problemas para o Meio Ambiente em que vivemos, como alertas atrasados de todo tipo como de terremotos e tsunamis, desperdício de recursos e poluição.



OS 7 FUNDAMENTOS DO TESTE (ISTQB)

Apesar da área de testes de software existir há décadas ela ainda é pouco conhecida, na prática, pelas empresas e organizações. Para guiar essas organizações por um caminho mais efetivo de testes e sanar suas dúvidas, o ISTQB, uma entidade com sede na Bélgica, criou uma lista de 7 Fundamentos do Teste para estabelecer as ideias e conceitos que irão ditar o que o teste consegue e não consegue fazer, evitando expectativas erradas e mitos sobre a área.

É sobre estes fundamentos que iremos descorrer a seguir.

1o FUNDAMENTO: O TESTE DEMONSTRA A PRESENÇA DE DEFEITOS MAS NÃO GARANTE A SUA AUSÊNCIA!

O teste reduz a probabilidade que os defeitos permaneçam em um software, mas mesmo se nenhum defeito for encontrado, isto não prova que o software esteja sem defeitos. Nós, enquanto QA, nos esforçamos e aplicamos testes para que possamos encontrar o maior número de defeitos possível, ainda assim, em hipótese alguma poderemos garantir que todos os defeitos sejam encontrados. Então, enquanto testers, também não podemos pensar e agir que, por mais que tenhamos feito o nosso melhor trabalho, encontramos todos os bugs de um software.

2o FUNDAMENTO: TESTE EXAUSTIVO NÃO É POSSÍVEL!

Testar tudo, todas as combinações de entradas e pré-condições, não é viável, exceto para casos triviais. Ao invés do teste exaustivo, riscos e prioridades são levados em consideração para dar foco aos esforçs de teste. Não há tempo e recursos suficientes para sempre amplicarmos testes exaustivos. O segredo é PRIORIZAR!

3o FUNDAMENTO: TESTE ANTECIPADO!

Quanto mais breve possível você começar as atividades de teste, COM FOCO e no ciclo de desenvolvimento do software ou sistema, mais retorno você terá. Teste não é só no final do desenvolvimento! Teste tem que ocorrer em paralelo a ele, para cada atividade de desenvolvimento tem que ocorrer uma atividade de revisão. Tudo isso para garantir que o desenvolvimento esteja no rumo correto e que o software ou sistema esteja sendo bem feito.
Este fundamento bate com o que entendemos como A Regra 10 de Myers e o consenso de que quanto mais cedo encontrarmos um defeito, mais barata será sua identificação e correção. Por isso realizar as atividades de testes constantemente e com o decorrer do desenvolvimento é crucial.

4o FUNDAMENTO: AGRUPAMENTO DE DEFEITOS!

Os bugs não gostam de ficar sozinhos, eles gostam de ficar juntos. Um número pequeno de módulos de um software ou sistema pode conter a maioria dos defeitos descobertos durante o teste antes de sua entrega, ou, pode exibir a maioria das falhas operacionais. Bugs geralmente estão distribuídos de forma heterogênea. Alguns módulos têm mais defeitos do que outros. Isto ocorre pois há módulos e features de sistemas que são mais complexas ou complicadas de fazer ou, durante o desenvolvimento, estes módulos podem ter sido alterados constantemente, etc.
Com dedicação, conhecimento e experiência nós conseguiremos enxergar quais módulos de um software pode apresentar mais defeitos e saberemos como procurar defeitos mais eficientemente.

5o FUNDAMENTO: PARADOXO DO PESTICIDA!

Pode ocorrer de um mesmo conjunto de testes repetidos várias vezes não encontrarem novos defeitos após determinado momento.
Para superar este "parodoxo do pesticida", os casos de testes necessitam ser frequentemente revisados e atualizados. Um conjunto de testes novo e diferente precisa ser escrito para exercitar diferentes partes do  software ou sistema com o objetivo de aumentar a possibilidade de encontrar outros erros. Inove seus testes regularmente! 

6o FUNDAMENTO: TESTE DEPENDE DO CONTEXTO!

Testes devem ser realizados de forma diferente conforme o contexto.
Exemplo: Software de piloto automático de um avião deve ser testado com aplitude e profundidade diferentes de um software de um quiosque de informações em um shopping. É importante entender os riscos do cliente.

7o FUNDAMENTO: A ILUSÃO DA AUSÊNCIA DE ERROS!

Encontrar e concertar defeitos não ajuda se o sistema construído não atende às expectativas e necessidades dos usuários. É imprescindível saber para qual finalidade o cliente quer o software.
Por isso, é muito importante que você, enquanto QA de uma equipe, fique atento que o software corresponda tecnicamente ao que ele deve ser, o que chamamos de verificação, e, por outro lado, fique também atento se aquela solução, aquele software atende os ogjetivos do cliente.



DIFERENÇA ENTRE TESTE E QA

Embora muitos profissionais e empresas confundem, teste e QA são coisas diferentes, porém elas se complementam.

O teste é focado em avaliar o produto, ou seja, ver se aquele software funciona conforme o cliente gostaria. Então, o teste, o testador, ele olha o produto, e ele pode olhar o produto também de forma automatizada sem problemas.

O QA é focado em melhorar o processo, a forma de fazer ao invés do produto, é alguém que vai trabalhar sobre as lições aprendidas. 
O QA deverá entender a causa raiz dos defeitos encontrados, aprimorar processos, prevenir reincidência de erros, melhorar a qualidade dos sistemas futuros...

Os testes devem ser integrados como uma das atividades de QA (garantia de qualidade) juntamente aos padrões de desenvolvimento, treinamento, análise de defeitos e outras ações.



ERRO, OCORRÊNCIA, DEFEITO E FALHA

Um erro leva a um defeito que leva a uma falha.
Software são feitos por pessoas e para pessoas e pessoas cometem erros, que produzem defeitos (bugs) no código, em um software ou sistema ou em um documento. Se um defeito no código for executado, o sistema falhará ao tentar fazer o que deveria (ou, em algumas vezes, o que não deveria), causando uma falha.

Nem todos os defeitos causam falhas (a falha só existe quando o defeito é executado).

Falhas geram insatisfação com a qualidade.

Em QA, só devemos chamar de "erros" ou "defeitos" quando são erros e defeitos causados por nós mesmos. Só que normalmente um QA não vai encontrar e avaliar erros que eles mesmos causaram, pois eles não estão efetivamente desenvolvendo um software. Portanto, os erros que os QA analisarão geralmente são causados por outros, para evitar atritos, é recomendado que chamemos esses defeitos de "OCORRÊNCIAS" ou "INCIDENTES".

A lição importante aqui é que um QA deve saber questionar e argumentar sobre essas ocorrências com os outros membros da equipe, e de maneira alguma acusar ou responsabilizar eles pelos bugs encontrados. Lembre-se que geralmente ninguém erra por que quer ou para sabotar o próprio ambiente de trabalho, mas sim por engano, sem intenção.

Quando um bug ou defeito é encontrado pelo usuário e/ou cliente, ou quando executamos um código com erros, aí então chamamos estes erros de FALHAS.



TIPOS DE TESTES BASEADOS NA IEC/ISO 25010

A qualidade está sempre em evolução, antes da IEC/ISO já existiam outras normas de QA, hoje em dia, essa norma é o padrão do mercado que deve ser seguido. Essa norma também é conhecida pela sigla SQuaRE, que significa Requerimentos e Avaliação da Qualidade de Sistemas e Sofware, em inglês.

A NORMA IEC/ISO 25010 Irá se subdividir em 8 grandes características, as quais chamamos de AF U C C E M P S. Vamos abordar cada uma dessas características a seguir.

AF - ADEQUAÇÃO FUNCIONAL!

Também chamado de Funcionalidade,a Adequação Funcional é um teste que fazemos para saber se um software cumpre com essa adequação Funcional, ou seja, se ele cumpre com as suas funcionalidades, se ele faz o que deveria fazer. Este teste é o que chamamos de Teste De Negócio, sendo o único chamado assim, os demais testes nós chamamos de testes técnicos.

Este teste é subdividido em 3 subcaracterísticas: 

Completude: Representa se aquela funcionalidade está completa, se faz tudo o que deveria fazer.

Correção: Ou correção funcional, ou corretude, se trata de ver se o resultado do teste está correto.

Apropriado: Representa saber se o software é apropriado, ou seja, se ele apresenta o resultado e/ou a informação de forma apropriada. 

U - USABILIDADE!

A usabilidade é um teste para saber a facilidade que o usuário terá de usar aquele software. Ela se divide em 6 subcaracterísticas, sendo elas:

Reconhecibilidade: Seria a facilidade que o usuário tem de reconhecer os elementos e comportamentos da tela, como botões, funcionabilidades, etc.

Aprendizibilidade: Seria a facilidade que o usuário têm de aprender a usar aquele software. Se ele possui dicas e recursos de ajuda para o usuário usar melhor o software.

Operabilidade: Seria a facilidade de navegação e operação daquele software. Ou seja, a facilidade que o usuário terá de operar aquele software.

Proteção Contra Erro do Usuário: Ou seja, seria a forma que o sistema irá proteger que o usuário cometa erros ao utilizar aquele software.

Estética: Da Interface do usuário. Se essa estética é agradável, se é ergonômica, se facilita visualmente a experiência de uso do usuário naquele ambiente de forma confortável. Se o Design daquele sistema é bem feito.

Acessibilidade: Seria sobre a facilidade do software ser acessado por todas as pessoas, sejam pessoas com deficiência motora, visual, sonora, etc.

C - COMPATIBILIDADE! 

A compatibilidade é um teste que se trata sobre saber se o software é compatível com outros softwares e possui 2 subcaracterísticas, sendo elas:

Coexistência: Se o software tem facibilidade de coexistir com outros softwares, sem problemas. Pois, no mundo real não haverá apenas um software, mas, vários softwares coexistindo em um mesmo ambiente, aparelho, equipamento, sistema, etc.

Interoperabilidade: Se o software vai ter facilidade de se conectar e comunicar com outros softwares. Se ele terá facilidade em estabelecer uma conexão com outros softwares, enviar dados, receber dados, etc. Pois, hoje em dia, softwares conversam entre si e não operam sozinhos.

C  - CONFIANÇA!

Ou confiabilidade, é um teste para se ter certeza se um software está disponível e confiável de ser usado. 

O teste de confiabilidade se divide em 4 subcaracterísticas:

Maturidade: Perceber a falha e previní-la antes que ela aconteça.

Disponibilidade: É a caracterísica pela qual eu deveria maximizar o tempo em que a minha aplicação fica disponível para o usuário/cliente.

Tolerância a Falhas: Serve para Perceber e compensar as falhas em tempo real.

Recuperabilidade: É a característica de teste para saber a capacidade do software de recuperar-se de falhas e travamentos.

E - EFICIÊNCIA!

Também conhecida como eficiência de desempenho, é um teste que serve para sabermos se o software é rápido e eficiente no seu funcionamento. Essa característica de teste possui 3 subcaracterísticas:

Comportamento em Relação ao Tempo: Seria a performance, o desempenho em si.

Utilização de Recursos: Observar como o software utiliza os recursos, como memória ram, processamento, memória, quais recursos são mais e menos utilizados, etc. É melhor um software que usa os recursos de uma máquina, mesmo que utilize bastantes recursos, do que um software que não saiba utilizar esses recursos.

Capacidade: Observar qual a quantidade de usuários, por exemplo, que o software é capaz de suportar. É sobre a capacidade do software de atender transações e usuários.

M - MANUTENIBILIDADE!

A manutenibilidade é um teste para sabermos a facilidade que o software tem para a realização de manutenções. Ela pode se dividir em 5 subcaracterísticas, são elas:

Modularidade: Se o software é organizado em módulos, para que possamos controlar melhor o software, desligar, religar, trocar e modificar tais módulos deste software sem afetar seu funcionamento.

Reusabilidade: Se uma estrutura de um software pode ser reutilizado em outras partes deste software, se o software é construído pensando que não só você irá usar, mas também será usado por várias pessoas.

Analisabilidade: Se o software é fácil de ser analisado e entendido por outros desenvolvedores e colegas de trabalho que venham trabalhar com o software em questão.

Modificabilidade: Se o software é fácil de ser modificado, como por exemplo, se apenas uma parte ou componente de um software pode ser modificado para alterar ou atualizar o software, sem precisar codificar. 

Se eu preciso codificar para alterar o softeware, então estamos falando de Analisabilidade, se não precisamos codificar para alterá-lo então estamos falando de Modificabilidade.

Testabilidade: Se o software é viável e fácil de testar. Existem testes que não se testa ou se testa com extremo cuidado, são raros mas existem. Existem testes que só se consegue fazer manualmente e existem testes que possuem ferramentas de automação para se testar mais rápido. 

Toda vez que você receber um software para testar, a primeira coisa a ser feita é justamente avaliar a testabilidade daquele software. Entender se você possui as ferramentas, recursos, conhecimentos e habilidades necessárias para testar o software.