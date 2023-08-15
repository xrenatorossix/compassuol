Olá. Este é o meu resumo do dia 9 da primeira Sprint da minha trilha de aprendizado sobre QA com AWS enquanto estou estagiando pela Compass.uol



# AWS CLOUD PRACTITIONER ESSENTIALS (PARTE 2)

A AWS fez a sua infraestrutura, na forma que foi configurada, uma solução para descentralizar essa infraestrutura. Não é bom o suficiente ter um datacenter gigante com todos os seus recursos. Se acontecesse algo com esse datacenter, como uma queda de energia ou um desastre natural, todas as aplicações seriam desativadas de uma única vez. Você precisa de alta disponibilidade e tolerância a falhas. Então dois datacenters gigantes também não vão resolver todos os seus problemas. Em vez disso, a AWS opera em diversas áreas geográficas diferentes pelo mundo, chamadas regiões.



## INFRAESTRUTURA GLOBAL DA AWS

Para entender a infraestrutura global da AWS, acho melhor começarmos falando sobre as necessidades dos clientes em seus negócios. Você tem uma aplicação que precisa rodar. Um dado que precisa ser armazenado ou analisado. Basicamente, você tem uma série de componentes que precisam coexistir e operar para algum propósito. 

No passado, as empresas tiveram que rodar suas aplicações nos seus próprios data centers porque elas não tinham uma opção. Quando a AWS ficou disponível, várias empresas poderiam rodar suas aplicações em outros data centers que não eram seus e que nem estavam debaixo da sua responsabilidade.

Se você rodar seu próprio data center, você precisa responder à pergunta sobre o que será feito quando um desastre atingir esse prédio Você poderia rodar um segundo data center, por exemplo, mas só o custo de alugar um outro lugar já seria assustador. Além de todo custo duplicado de hardware, funcionários, energia elétrica, aquecimento, ar condicionado e segurança. A maioria das empresas simplesmente acaba armazenando seus backups em algum lugar e fica torcendo para nunca acontecer uma falha de grandes proporções. E confiar apenas na esperança não é um bom plano de negócio.

Em todo o mundo, a AWS cria **regiões** para serem mais próximas de onde o fluxo de negócios mais precisa. Locais como Paris, Tóquio, São Paulo, Dublin, Ohio, dentro de cada região, temos vários data centers que têm diversos recursos de computação, armazenamento e outros serviços que você precisa para rodar suas aplicações.



### Regiões de data centers AWS:

Cada região pode ser conectada com todas as outras regiões por meio de uma rede de fibra óptica de alta velocidade administrada pela AWS. Uma operação realmente global de ponta a ponta, caso você precise disso.

Cada região é isolada umas das outras no sentido de que nenhum dado entra ou sai do seu ambiente nessa região sem que você permita isso de forma explícita, sem que você permita que seus dados sejam movidos. Essa é uma conversa de extrema importância sobre segurança.

Ao determinar a Região certa para seus serviços, dados e aplicativos, considere os quatro fatores de negócios a seguir:

**Conformidade com Governança de dados e requisitos legais:**

Dependendo da sua empresa e localização, talvez seja necessário executar seus dados em áreas específicas. Por exemplo, se sua empresa exige que todos os dados residam dentro dos limites do Reino Unido, você deve escolher a Região Londres.

Nem todas as empresas têm regulamentações de dados específicas para a localização, portanto, você pode precisar se concentrar nos outros três fatores.

Você tem um requisito de que seus dados devem ser armazenados dentro dos limites do Brasil? Então, você deve escolher a região de São Paulo, ponto. Nenhuma das outras opções deve ser considerada. Ou vamos pensar que você deve rodar a sua aplicação dentro do território chinês. Para isso você deve escolher uma das nossas regiões chinesas.

**Proximidade com os clientes:**

A seleção de uma Região próxima de seus clientes ajudará você a obter o conteúdo com mais rapidez. Por exemplo, sua empresa está sediada em Washington, DC, e muitos de seus clientes residem em Singapura. Você pode considerar executar sua infraestrutura na Região Norte da Virgínia por estar perto da sede da empresa e executar os aplicativos a partir da Região Singapura.

O mais próximo que você está da sua base de clientes é um fato importante, porque a velocidade da luz ainda é uma das leis do universo. O tempo que a luz leva para viajar ao redor do mundo deve ser sempre considerado. Se estabelecer perto da sua base de clientes normalmente é a decisão mais assertiva.

**Serviços disponíveis em uma Região:**

Às vezes, a Região mais próxima pode não ter todos os recursos que você deseja oferecer aos clientes. A AWS inova frequentemente ao criar novos serviços e expandir recursos em serviços existentes. No entanto, disponibilizar novos serviços em todo o mundo às vezes exige que a AWS desenvolva o hardware físico de cada Região por vez.

Suponha que seus desenvolvedores queiram criar um aplicativo que use o Amazon Braket (plataforma de computação quântica da AWS). Neste curso, o Amazon Braket ainda não está disponível em todas as Regiões AWS em todo o mundo, por isso, os desenvolvedores precisariam executá-lo em uma das Regiões que já o oferece.

Será que podemos esperar que o serviço esteja disponível em todas as regiões? Essa é uma boa expectativa. Mas se você quiser usar ele hoje, esse pode ser o seu ponto decisivo.


**Definição de preços:**

Suponha que você pretenda executar aplicativos nos Estados Unidos e no Brasil. Com a estrutura tributária do Brasil, pode custar 50% mais caro executar a mesma carga de trabalho na Região São Paulo em comparação com a Região Oregon. Você aprenderá com detalhes que vários fatores determinam o preço, mas, por enquanto, saiba que o custo dos serviços pode variar entre as regiões.

O preço pode ser determinado por muitos fatores. Então, a AWS tem muitos preços granulares e transparentes, que nós vamos discutir nessa aula. Mas é importante lembrar que cada região tem uma tabela de preços diferente. Então, se o orçamento financeiro é a sua principal preocupação, mesmo que os seus clientes estejam no Brasil, você ainda pode pensar em operar num país diferente. Novamente, se o preço for a sua principal motivação, sua principal decisão.



### Zonas de Disponibilidade (AZ): 

Uma Zona de Disponibilidade é um único data center ou um grupo de data centers em uma Região. As Zonas de Disponibilidade estão localizadas a dezenas de quilômetros de distância umas das outras. A proximidade é suficiente para haver baixa latência (tempo entre o momento em que o conteúdo foi solicitado e recebido) entre as Zonas de Disponibilidade. No entanto, se ocorrer um desastre em uma parte da Região, há distância suficiente para reduzir a chance de que várias Zonas de Disponibilidade sejam afetadas.




### Local de Borda: 

Um local de borda é um site que o Amazon CloudFront usa para armazenar cópias em cache do seu conteúdo mais próximo dos seus clientes para uma entrega mais rápida.

**Origem:** Suponha que os dados da sua empresa estejam armazenados no Brasil e que você tenha clientes que residem na CHina. Para entregar conteúdo a esses clientes, você não precisa mover todo o conteúdo para uma das regiões chinesas.

**Local de borda:** Em vez de exigir que seus clientes obtenham os dados a partir do Brasil, você pode armazenar localmente em cache uma cópia em um local de borda próximo de seus clientes na China.

**Cliente:** Quando um cliente na China solicita um de seus arquivos, o Amazon CloudFront recupera o arquivo a partir do cache no local de borda e entrega o arquivo ao cliente. O arquivo é entregue ao cliente mais rápido porque veio do local de borda próximo à China em vez da fonte original no Brasil.

Quando você armazena em cash uma cópia dos seus dados para ficar mais perto dos seus clientes em todo o mundo, você está usando o conceito de Redes de entrega de conteúdo, ou CDNs.

As CDNs são muito utilizadas nas arquiteturas E, na AWS, A nossa CDN se chama Amazon Cloudfront. O Amazon Cloudfront é um serviço que ajuda a fornecer dados, vídeos, aplicações e APIs para os clientes em todo o mundo, com baixa latência e alta velocidade de transferência. O Amazon Cloudfront usa que nós chamamos de Edge Locations, pontos de presença espalhados pelo mundo para ajudar a acelerar a comunicação com os usuários, Não importa onde eles estejam.

As Edge locations são separadas das regiões. Logo, você pode enviar um conteúdo de dentro de uma região para uma coleção desses pontos de presença em todo mundo, para acelerar a comunicação e a entrega de conteúdo. As Edge locations da AWS também executam mais do que apenas o store front. Elas executam um serviço de DNS conhecido como Amazon Route 53 que ajuda os clientes a direcionar as requisições corretamente para os seus servidores web, com baixa latência e confiabilidade.

Mas, e se sua empresa quiser usar os serviços da AWS dentro do seu próprio prédio? Sim, a AWS pode e tem um serviço para atender essa necessidade. Esse é o AWS Outposts, onde a AWS basicamente vai instalar e configurar uma mini-região totalmente operacional direto do seu próprio datacenter. Toda responsabilidade e propriedade é da AWS. Ela que vai operar e administrar tudo, mas de forma isolada, dentro do seu próprio prédio. Não é uma solução que a maioria dos clientes precisa. Mas se você tiver necessidades específicas que podem ser resolvidas apenas mantendo as suas aplicações dentro do seu próprio prédio, nós entendemos. E o AWS Outposts pode te ajudar.

Vamos então para os nossos pontos-chave. Número um: as regiões são áreas geograficamente isoladas onde você pode acessar os serviços para rodar suas aplicações de negócio. Número dois: as regiões contêm zonas de disponibilidade, as AZs que permitem que você rode suas aplicações de forma separada fisicamente, dezenas de quilômetros de distância, enquanto mantém a parte lógica da aplicação unificada. As zonas de disponibilidade ajudam você a construir cenários de alta disponibilidade e de recuperação de dados sem esforço adicional da sua parte. Número três: as Edge Location, os pontos de presença da AWS que executam o Amazon Cloudfront para ajudar a obter conteúdo mais aproximado dos seus clientes não importa onde eles estejam ao redor do mundo.



## COMO PROVISIONAR RECURSOS AWS

Falamos de alguns recursos da AWS bem como infraestrutura global e você pode estar se perguntando: como eu realmente interajo com esses serviços? E a resposta é: APIs. 



### APIs:

Na AWS, tudo é uma chamada de API. Uma API é uma interface de programação de aplicação. Isso significa que há maneiras pré-determinadas de interagir com o serviço da AWS. E você pode invocar ou chamar essas APIs para provisionar, configurar e gerenciar os seus recursos da AWS.

Por exemplo, você pode iniciar uma instância EC2 ou criar uma função do Lambda, cada um desses pedidos diferentes são chamadas de API para a AWS. Você pode usar a Console de Gerenciamento da AWS, a CLI, para utilizar linhas de comando. Pode utilizar também as SDKs com linguagens de programação como Java C++, Botnet, Python entre outras. Há também várias outras ferramentas como a AWS Cloud Formation para criar ambientes inteiros de forma centralizada utilizando chamadas de API da AWS para criar e gerenciar esses recursos.



### Maneiras de interagir com os serviços AWS:

**AWS Management Console:** 

O AWS Management Console é uma interface baseada na web para acessar e gerenciar os serviços AWS. Você pode acessar rapidamente os serviços usados recentemente e pesquisar outros serviços por nome, palavra-chave ou acrônimo. O console inclui assistentes e fluxos de trabalho automatizados que podem simplificar o processo de conclusão de tarefas.

Você também pode usar o aplicativo móvel AWS Console para executar tarefas como monitoramento de recursos, visualização de alarmes e acesso a informações de cobrança. Várias identidades podem permanecer em sessão no aplicativo móvel AWS Console ao mesmo tempo.

**Interface da Linha de Comando:**

Para economizar tempo ao fazer solicitações de API, você pode usar o AWS Command Line Interface (AWS CLI). O AWS CLI permite que você controle vários serviços AWS diretamente a partir da linha de comando em uma ferramenta. O AWS CLI está disponível para usuários no Windows, macOS e Linux.

Usando o AWS CLI, você pode automatizar as ações que seus serviços e aplicativos executam por scripts. Por exemplo, você pode usar comandos para executar uma instância do Amazon EC2, conectar uma instância do Amazon EC2 a um grupo específico de Auto Scaling e muito mais.

**Kits de Desenvolvimento de Software (SDKs):**

Outra opção para acessar e gerenciar serviços AWS são os kits de desenvolvimento de software (SDKs). Os SDKs facilitam o uso dos serviços AWS por uma API projetada para sua linguagem de programação ou plataforma. Os SDKs permitem que você use serviços AWS com seus aplicativos existentes ou crie aplicativos totalmente novos que serão executados na AWS.

Para ajudar você a começar a usar SDKs, a AWS fornece a documentação e um código de exemplo para cada linguagem de programação compatível. As linguagens de programação compatíveis são C++, Java, .NET e muito mais.



## COMO PROVISIONAR RECURSOS AWS - PARTE 2

Vamos continuar a conversar sobre como interagir com a AWS. Você tem a Console de Gerenciamento da AWS, a CLI e as SDKs para provisionar e gerenciar seu ambiente da AWS. Se você deseja provisionar um recurso, pode fazer o login na console e selecionar o recurso, com alguns cliques, ele estará disponível. Você pode escrever alguns comandos ou pode escrever uma aplicação para fazer isso. Há também outras maneiras de gerenciar o seu ambiente da AWS usando ferramentas como o **AWS Elastic Beanstalk** e o **AWS CloudFormation**.



### AWS Elastic Beanstalk:

Com o AWS Elastic Beanstalk, você fornece definições de código e configuração, e o Elastic Beanstalk implanta os recursos necessários para executar as seguintes tarefas:

- Ajustar capacidade.
- Balancear carga.
- Dimensionar de forma automática.
- Monitorar a integridade do aplicativo.



### AWS CloudFormation:

Com o AWS CloudFormation, você pode considerar sua infraestrutura como código. Isso significa que você pode criar um ambiente escrevendo linhas de código em vez de usar o AWS Management Console para provisionar recursos individualmente.

O AWS CloudFormation provisiona os recursos de maneira segura e repetível, permitindo que você crie frequentemente a infraestrutura e os aplicativos sem precisar executar ações manuais ou criar scripts personalizados. Ele determina quais são as operações mais adequadas para gerenciar sua pilha e reverte as alterações automaticamente se detectar erros.



### Amazon CloudFront:

O Amazon CloudFront é um serviço de entrega de conteúdo. Ele usa uma rede de locais de borda para armazenar conteúdo em cache e entregar conteúdo para clientes em todo o mundo. Quando o conteúdo é armazenado em cache, ele é mantido localmente como uma cópia. Esse conteúdo pode ser arquivos de vídeo, fotos, páginas da web e assim por diante.



### AWS Outposts:

O AWS Outposts é uma família de soluções totalmente gerenciadas que fornecem infraestrutura e serviços da AWS para praticamente qualquer local da borda ou on-premises para uma experiência híbrida verdadeiramente consistente. As soluções do Outposts permitem que os clientes estendam e executem serviços da AWS nativos on-premises e estão disponíveis em uma variedade de formatos, de servidores Outposts 1U e 2U a racks Outposts 42U e várias implantações de rack.

Com o AWS Outposts, você pode executar alguns produtos da AWS localmente e se conectar a uma ampla gama de serviços disponíveis na região local da AWS. Execute aplicações e workloads on-premises usando serviços, ferramentas e APIs familiares da AWS. O Outposts é compatível com workloads e dispositivos que exigem acesso de baixa latência a sistemas on-premises, processamento de dados local, residência de dados e migração de aplicações com interdependências do sistema local.



## CONECTIVIDADE COM A AWS:



### Amazon Virtual Private Cloud (Amazon VPC)

Uma VPC, Virtual Private Cloud, é o serviço que você utiliza para criar a sua própria rede privada na AWS. A VPC permite que você defina o seu intervalo de preços privados para fazer a alocação de recursos, como instâncias EC2 e Load Balancing dentro da sua rede.

Imagine os milhões de clientes que usam os serviços AWS. Imagine também os milhões de recursos que esses clientes criaram, como as instâncias do Amazon EC2. Sem limites para todos esses recursos, o tráfego de rede fluiria entre eles sem restrições.

Um serviço de rede que você pode usar para definir limites para seus recursos AWS é o Amazon Virtual Private Cloud (Amazon VPC).

O Amazon VPC permite que você provisione uma seção isolada da nuvem AWS. Nessa seção isolada, você pode executar os recursos em uma rede virtual que definir. Em uma Virtual Private Cloud (VPC), você pode organizar seus recursos em sub-redes. Uma sub-rede é uma seção de uma VPC que pode conter recursos como instâncias do Amazon EC2.



### Gateway da Internet:

Para permitir que o tráfego público da internet acesse sua VPC, é preciso anexar um gateway da internet à VPC.

Um gateway da internet é uma conexão entre uma VPC e a internet. Você pode pensar em um gateway da internet como sendo semelhante a uma porta que os clientes usam para entrar na cafeteria. Sem um gateway da internet, ninguém pode acessar os recursos em sua VPC.

**E se você tiver uma VPC apenas com recursos privados?**



### Gateway Privado Virtual:

Para acessar recursos privados em uma VPC, você pode usar um gateway privado virtual. 

Veja um exemplo de como um gateway privado virtual funciona. Você pode pensar na internet como o caminho entre sua casa e a cafeteria. Suponha que você está viajando com um guarda-costas para proteção. Você ainda usa o mesmo caminho que outros clientes, mas com uma camada extra de proteção.

O guarda-costas é como uma conexão de rede privada virtual (VPN) que criptografa (ou protege) seu tráfego de internet de todas as outras solicitações ao redor.

O gateway privado virtual é o componente que permite que o tráfego protegido da internet ingresse na VPC. Mesmo que sua conexão com a cafeteria tenha proteção extra, os engarrafamentos são possíveis porque você usa o mesmo caminho que outros clientes.

Um gateway privado virtual permite estabelecer uma conexão VPN (rede virtual privada) entre a VPC e uma rede privada, como um data center local ou uma rede corporativa interna. Um gateway privado virtual permitirá o tráfego na VPC somente se ele for proveniente de uma rede aprovada.



### AWS Direct Connect:

O AWS Direct Connect é um serviço que permite estabelecer uma conexão privada dedicada entre seu data center e uma VPC.

Suponha que haja um prédio com um corredor que liga o prédio diretamente à cafeteria. Somente os moradores do prédio podem passar por esse corredor.

Esse corredor privado fornece o mesmo tipo de conexão dedicada que o AWS Direct Connect. Os moradores conseguem entrar na cafeteria sem precisarem usar a estrada pública compartilhada com outros clientes.

A conexão privada que o AWS Direct Connect fornece ajuda você a reduzir os custos de rede e a aumentar a quantidade de largura de banda que pode trafegar pela sua rede.



### Sub-redes e listas de controle de acesso à rede:

Para saber mais sobre a função das sub-redes em uma VPC, revise o exemplo da cafeteria a seguir.

Primeiro, os clientes fazem os pedidos ao operador de caixa. O operador de caixa, em seguida, passa os pedidos para o barista. Esse processo permite que a fila prossiga sem problemas à medida que mais clientes entram. 

Suponha que alguns clientes tentem pular a fila do caixa e fazer seus pedidos diretamente ao barista. Isso interrompe o fluxo de tráfego e faz com que os clientes acessem uma parte da cafeteria que é restrita a eles.

Para corrigir isso, os proprietários da cafeteria dividem a área do balcão colocando o operador de caixa e o barista em estações de trabalho separadas. A estação de trabalho do operador de caixa é voltada para o público e projetada para receber clientes. A área do barista é privada. O barista ainda pode receber pedidos do operador de caixa, mas não diretamente dos clientes.

Isso se parece à forma como você pode usar os serviços de redes da AWS para isolar recursos e determinar exatamente como o tráfego de rede flui.

Na cafeteria, você pode pensar na área do balcão como uma VPC. A área do balcão divide-se em duas áreas separadas para a estação de trabalho do operador de caixa e para a estação de trabalho do barista. Em uma VPC, sub-redes são áreas separadas usadas para agrupar recursos.



### Sub-redes:

Uma sub-rede é uma seção de uma VPC na qual você pode agrupar recursos com base em necessidades operacionais ou de segurança. As sub-redes podem ser públicas ou privadas. 

**Sub-redes Públicas:** contêm recursos que precisam ser acessíveis ao público, como o site de uma loja on-line.

**As sub0redes Privadas:** contêm recursos que devem ser acessíveis apenas pela sua rede privada, como um banco de dados contendo informações pessoais dos clientes e históricos de pedidos.

Em uma VPC, as sub-redes podem se comunicar entre si. Por exemplo, um aplicativo que envolve instâncias do Amazon EC2 em uma sub-rede pública que se comunicam com bancos de dados localizados em uma sub-rede privada.



### Tráfego de rede em uma VPC:

Quando um cliente solicita dados de um aplicativo hospedado na nuvem AWS, essa solicitação é enviada como um pacote. Um pacote é uma unidade de dados enviada pela internet ou por uma rede.

Ele entra em uma VPC por um gateway da internet. Antes de um pacote poder entrar em uma sub-rede ou sair de uma sub-rede, ele verifica se há permissões. Essas permissões indicam quem enviou o pacote e como ele tenta se comunicar com os recursos em uma sub-rede.

O componente da VPC que verifica as permissões de pacotes para sub-redes é uma lista de controle de acesso (ACL) de rede.



### Lista de controle de acesso (ACL) de rede:

Uma lista de controle de acesso (ACL) de rede é um firewall virtual que controla o tráfego de entrada e saída no nível de sub-rede.

Por exemplo, saia da cafeteria e imagine que você está em um aeroporto. No aeroporto, os viajantes estão tentando entrar em um país diferente. Você pode pensar nos viajantes como pacotes e no oficial de controle de passaportes como uma ACL de rede. O oficial de controle de passaportes verifica as credenciais dos viajantes quando entram e saem do país. Se um viajante estiver em uma lista aprovada, ele poderá passar. No entanto, se ele não estiver na lista aprovada ou estiver explicitamente em uma lista de viajantes proibidos, ele não poderá entrar.

Cada conta AWS tem uma ACL de rede regular. Ao configurar sua VPC, você pode usar a ACL de rede comum da sua conta ou criar ACLs de rede personalizadas. 

Por padrão, a ACL de rede comum da conta permite todo o tráfego de entrada e saída, mas você pode modificá-la adicionando suas próprias regras. Para ACLs de rede personalizadas, todo o tráfego de entrada e saída é negado até que você adicione regras para especificar qual tráfego permitir. Além disso, todas as ACLs de rede têm uma regra de negação explícita. Essa regra garante que, se um pacote não corresponder a nenhuma das outras regras na lista, ele será negado.



### Filtragem de pacotes stateless: 

As ACLs de rede executam a filtragem de pacotes stateless. Elas não se lembram de nada e verificam os pacotes que atravessam a fronteira da sub-rede em todos os sentidos: entrada e saída.

Lembre-se do exemplo anterior de um viajante que quer entrar em um país diferente. Isso se parece com o envio de uma solicitação de uma instância do Amazon EC2 e para a internet.

Quando uma resposta de pacote para essa solicitação volta para a sub-rede, a ACL de rede não se lembra da solicitação anterior. A ACL de rede verifica a resposta do pacote em relação à lista de regras para determinar se deseja permitir ou negar.

Depois que um pacote entra em uma sub-rede, ele deve ter as permissões avaliadas para recursos dentro da sub-rede, como as instâncias do Amazon EC2.

O componente da VPC que verifica as permissões de pacote para uma instância do Amazon EC2 é um grupo de segurança.



### Grupos de Segurança:

Um grupo de segurança é um firewall virtual que controla o tráfego de entrada e saída de uma instância do Amazon EC2.

Por padrão, um grupo de segurança nega todo o tráfego de entrada e permite todo o tráfego de saída. Você pode adicionar regras personalizadas para configurar o tráfego a ser permitido ou negado.

Para este exemplo, suponha que você esteja em um prédio com um porteiro que cumprimenta os visitantes no lobby. Você pode pensar nos visitantes como pacotes e no porteiro como um grupo de segurança. À medida que os visitantes chegam, o porteiro verifica uma lista para garantir que eles podem entrar no edifício. No entanto, o porteiro não verifica a lista novamente quando os visitantes saem do edifício

Se você tiver várias instâncias do Amazon EC2 em uma sub-rede, poderá associá-las ao mesmo grupo de segurança ou usar grupos de segurança diferentes para cada instância.



### Filtragem de pacotes Stateful:

Os grupos de segurança fazem a filtragem de pacotes stateful. Eles se lembram de decisões anteriores tomadas para pacotes recebidos.

Considere o mesmo exemplo de envio de uma solicitação de uma instância do Amazon EC2 para a internet.

Quando uma resposta de pacote para essa solicitação retorna para a instância, o grupo de segurança lembra da solicitação anterior. O grupo de segurança permite que a resposta prossiga, independentemente das regras do grupo de segurança de entrada.

As ACLs de rede e os grupos de segurança permitem que você configure regras personalizadas para o tráfego em sua VPC. Conforme você aprende mais sobre a segurança e a rede da AWS, verifique se entendeu as diferenças entre ACLs de rede e grupos de segurança.



### Redes Globais:

Conversamos muito sobre como você interage com sua infraestrutura na AWS. Mas como seus clientes interagem com sua infraestrutura na AWS? Se você tiver um site hospedado na AWS, os clientes, geralmente, entram em seu site em um navegador, apertam enter e alguma magia acontece e o site se abre.

Mas como é que essa magia funciona? Bem, assim como essa moeda mágica que eu tenho aqui, você sabe, você dá uma mordida e ela está de volta. Não é bem assim, mas eu vou guiar você pelos dois serviços que ajudariam no caso do site. O primeiro e o Route 53, que é um serviço de nome de domínio da AWS, ou DNS, e é altamente disponível e escalável. Mas, espere. O que é o DNS que você disse? Pense em DNS como um serviço de tradução. Mas em vez de traduzir entre idiomas, traduz nomes de sites para endereços IP, ou Internet Protocol, que, dessa forma, os computadores podem ler.



### Domain Name System (DNS):

Suponha que a AnyCompany tenha um site hospedado na nuvem AWS. Os clientes digitam o endereço da web no navegador e podem acessar o site. Isso acontece devido à resolução Domain Name System (DNS). A resolução de DNS envolve um servidor DNS que se comunica com um servidor web.

Você pode pensar no DNS como sendo a lista telefônica da internet. A resolução de DNS é o processo de conversão de um nome de domínio para um endereço IP. 

Por exemplo, suponha que você deseja acessar o site da AnyCompany. 

- Quando você insere o nome de domínio no navegador, essa solicitação é enviada para um resolvedor de DNS do cliente.

- O resolvedor de DNS do cliente solicita ao servidor DNS da empresa o endereço IP que corresponde ao site da AnyCompany.

- O servidor DNS responde com o endereço IP para o site da AnyCompany, 192.0.2.0.



### Amazon Route 53:

O Amazon Route 53 é um serviço web de DNS. Oferece aos desenvolvedores e empresas uma maneira confiável de rotear os usuários finais para aplicativos da internet hospedados na AWS.

O Amazon Route 53 conecta solicitações de usuários à infraestrutura em execução na AWS (como instâncias do Amazon EC2 e balanceadores de carga). Ele pode direcionar os usuários para a infraestrutura fora da AWS.

Outro recurso do Route 53 é a capacidade de gerenciar os registros DNS para nomes de domínio. Você pode registrar novos nomes de domínio diretamente no Route 53. Você também pode transferir registros DNS para nomes de domínio existentes gerenciados por outras empresas de registro de domínio. Isso permite que você gerencie todos os seus nomes de domínio em um único local.

No módulo anterior, você conheceu o Amazon CloudFront, um serviço de entrega de conteúdo. O exemplo a seguir descreve como o Route 53 e o Amazon CloudFront trabalham juntos para entregar conteúdo aos clientes:

Suponha que o aplicativo da AnyCompany esteja em execução em várias instâncias do Amazon EC2. Essas instâncias estão em um grupo do Auto Scaling que é anexado a um balanceador de carga de aplicativo. 

- Um cliente solicita dados do aplicativo acessando o site da AnyCompany. 

- O Amazon Route 53 usa a resolução de DNS para identificar o endereço IP correspondente da AnyCompany.com, 192.0.2.0. Essas informações são enviadas de volta para o cliente. 

- A solicitação do cliente é enviada para o local de borda mais próximo por intermédio do Amazon CloudFront. 

- O Amazon CloudFront se conecta ao balanceador de carga de aplicativo, que envia o pacote de entrada para uma instância do Amazon EC2.



## ARMAZENAMENTO DE INSTÂNCIAS E AMAZON ELASTIC CLOCK STORE (AMAZON EBS)

Assim como em servidores on premises, aplicações dentro das EC2 precisam de acesso a recursos físicos, como CPU, memória, rede e armazenamento. As instâncias EC2 oferecem acesso a todos esses diferentes componentes e agora nós vamos nos concentrar na parte de armazenamento. À medida que as aplicações são executadas, elas, muitas vezes, precisam de acesso ao armazenamento de blocos.

Você pode pensar em armazenamento de blocos como um local para armazenar arquivos. Um arquivo sendo uma série de bytes que são armazenados em blocos no disco. Quando um arquivo é atualizado nem toda série de blocos é substituída. Em vez disso, apenas as partes atualizadas são alteradas e isso torna o armazenamento eficiente para trabalhar com aplicações como banco de dados, softwares corporativos e sistemas de arquivos.



### Armazenamentos de Instâncias: 

Os volumes de armazenamento a nível de bloco se comportam como discos rígidos físicos.

Um armazenamento de instâncias fornece armazenamento temporário a nível de bloco para uma instância do Amazon EC2. Um armazenamento de instância é o armazenamento em disco fisicamente anexo ao computador host para uma instância do EC2 e, portanto, tem a mesma vida útil da instância. Quando a instância é encerrada, todos os dados no armazenamento de instâncias são perdidos.



### Amazon Elastic Block Store ( Amazon EBS):

O Amazon Elastic Block Store (Amazon EBS) é um serviço que fornece volumes de armazenamento a nível de bloco que você pode usar com instâncias do Amazon EC2. Se você interromper ou encerrar uma instância do Amazon EC2, todos os dados no volume do EBS anexo permanecerão disponíveis.

Para criar um volume do EBS, defina a configuração (como tamanho e tipo do volume) e a provisão. Depois de criar um volume do EBS, ele pode ser anexado a uma instância do Amazon EC2.

Como os volumes do EBS são para dados que precisam perdurar, é importante fazer backup dos dados. Você pode fazer backups complementares de volumes do EBS criando snapshots do Amazon EBS.



### Snapshots do Amazon EBS:

Um snapshot do EBS é um backup incremental. Isso significa que o primeiro backup de um volume copia todos os dados. Nos backups subsequentes, somente os blocos de dados que foram alterados desde o snapshot mais recente são salvos. 

Os backups complementares são diferentes dos backups completos, nos quais todos os dados em um volume de armazenamento são copiados cada vez que ocorre um backup. O backup completo inclui dados que não foram alterados desde o backup mais recente.



### Amazon Simple Storage Service (Amazon S3):

Bem-vindo a este vídeo do Amazon Simple Storage Service, ou S3. Pelo nome você provavelmente já adivinhou que é um serviço de armazenamento e é bem simples. A maioria das empresas tem dados que precisam ser armazenados em algum lugar. Para a cafeteria Isso pode ser recibos, imagens, planilhas do Excel, vídeos de treinamentos de funcionários e até arquivos de textos, entre outros. Armazenar esses arquivos é onde o S3 é útil porque um armazenamento de dados que permite que você armazene e recupere uma quantidade ilimitada de dados em qualquer escala.

Os dados são armazenados como objetos. Mas em vez de armazenar em um diretório de arquivos, você os armazena no que chamamos de buckets. Pense em um arquivo no disco rígido. Isso é um objeto. E pense em um diretório de arquivos. Isso é um bucket. O tamanho máximo do objeto que você pode fazer upload é de 5 terabytes. Você pode criar versões de objetos para protegê-los contra exclusão acidental o que significa que você sempre vai reter as versões anteriores de um objeto como um rastro de papel. Você pode até criar vários buckets e armazená-los em diferentes classes ou níveis de dados. Em seguida, você pode criar permissões para limitar quem pode ver ou até mesmo quem pode acessar os objetos.

No armazenamento de objetos, cada objeto consiste em dados, metadados e uma chave.

Os dados podem ser uma imagem, vídeo, documento de texto ou qualquer outro tipo de arquivo. Os metadados contêm informações sobre o que são os dados, como eles são usados, o tamanho do objeto e assim por diante. A chave de um objeto é seu identificador exclusivo.

O Amazon Simple Storage Service (Amazon S3) é um serviço que fornece armazenamento a nível do objeto. O Amazon S3 armazena dados como objetos em buckets.

É possível fazer upload de qualquer tipo de arquivo para o Amazon S3, como imagens, vídeos, arquivos de texto e assim por diante. Por exemplo, você pode usar o Amazon S3 para armazenar arquivos de backup, arquivos de mídia para um site ou documentos arquivados. O Amazon S3 oferece espaço de armazenamento ilimitado. O tamanho máximo de arquivo para um objeto no Amazon S3 é de 5 TB.

Ao fazer upload de um arquivo para o Amazon S3, é possível definir permissões para controlar a visibilidade e o acesso a ele. Você também pode usar o recurso de versionamento do Amazon S3 para rastrear alterações em seus objetos ao longo do tempo.



### Classes de Armazenamento do Amazon S3:

Com o Amazon S3, você paga somente pelo que usar. Você pode escolher dentre diversas categorias de armazenamento aquela que melhor se ajusta às suas necessidades de negócios e de custo. Ao selecionar uma categoria de armazenamento do Amazon S3, considere esses dois fatores:

- Com que frequência você planeja recuperar seus dados.

- Seus dados precisam estar muito ou pouco disponíveis.

As categorias de armazenamento do Amazon S3 são:

**S3 Standard:**

- Projetado para dados acessados com frequência.
- Armazena dados em um mínimo de três Zonas de Disponibilidade.

O S3 Standard fornece alta disponibilidade para objetos. Isso o torna uma boa escolha para diversos casos de uso, como sites, distribuição de conteúdo e análise de dados. O S3 Standard tem um custo mais alto do que outras categorias de armazenamento para dados acessados com pouca frequência e armazenamento de arquivamento.

**S3 Standard-Infrequent Access (S3 Standard-IA):**

- Ideal para dados com pouca frequência de acesso.
- Semelhante ao S3 Standard, mas com um preço de armazenamento mais baixo e um preço de recuperação mais alto.

O S3 Standard-IA é ideal para dados acessados com pouca frequência, mas que precisam ter alta disponibilidade para quando necessário. O S3 Standard e o S3 Standard – IA armazenam dados em um mínimo de três Zonas de Disponibilidade. O S3 Standard – IA fornece o mesmo nível de disponibilidade do S3 Standard, mas com um preço de armazenamento mais baixo e um preço de recuperação mais alto.

**S3 One Zone-Infrequent Access (S3 One Zone - IA):**

- Armazena dados em uma única Zona de Disponibilidade.
- Tem um preço de armazenamento menor do que o S3 Standard – IA.

Comparado com o S3 Standard e o S3 Standard – IA, que armazenam dados em um mínimo de três Zonas de Disponibilidade, o S3 One Zone – IA armazena em uma única Zona de Disponibilidade. Isso o torna uma boa categoria de armazenamento nas seguintes condições:

- Você quer economizar custos com armazenamento.
- Você pode reproduzir facilmente seus dados em caso de falha na Zona de Disponibilidade.

**S3 Intelligent-Tiering:**

- Ideal para dados com padrões de acesso desconhecidos ou em alteração.
- Requer uma pequena taxa mensal de monitoramento e automação por objeto.

Na categoria de armazenamento S3 Intelligent-Tiering, o Amazon S3 monitora os padrões de acesso dos objetos. Se você não acessou um objeto por 30 dias consecutivos, o Amazon S3 o move automaticamente para o nível de acesso pouco frequente S3 Standard – IA. Se você acessar um objeto no nível de acesso pouco frequente, o Amazon S3 o move automaticamente para o nível de acesso frequente S3 Standard.

**S3 Glacier:**

- Armazenamento de baixo custo projetado para arquivamento de dados.
- Capaz de recuperar objetos em poucos minutos a horas.

O S3 Glacier é uma categoria de armazenamento de baixo custo, ideal para o arquivamento de dados. Por exemplo, você pode usar essa categoria para armazenar registros de clientes arquivados ou arquivos de fotos e vídeos mais antigos.

**S3 Glacier Deep Arquive:**

- Categoria de armazenamento de objetos com menor custo, ideal para arquivamento.
- Capaz de recuperar objetos em 12 horas.

Ao decidir entre o Amazon S3 Glacier e o Amazon S3 Glacier Deep Archive, considere a prontidão com que você precisa recuperar objetos arquivados. É possível recuperar objetos armazenados na categoria de armazenamento S3 Glacier de alguns minutos a algumas horas. Em comparação, é possível recuperar objetos armazenados na categoria de armazenamento S3 Glacier Deep Archive em até 12 horas.



### Armazenamento de Arquivos:

No armazenamento de arquivos, vários clientes (como usuários, aplicativos, servidores e assim por diante) podem acessar dados armazenados em pastas de arquivos compartilhadas. Nessa abordagem, um servidor de armazenamento usa armazenamento em bloco com um sistema de arquivos local para organizar os arquivos. Os clientes acessam dados através de caminhos de arquivo.

Comparado ao armazenamento em blocos e ao armazenamento de objetos, o armazenamento de arquivos é ideal para casos de uso em que um grande número de serviços e recursos precisam acessar os mesmos dados ao mesmo tempo.

O Amazon Elastic File System (Amazon EFS) é um sistema de arquivos escalável usado com os serviços de nuvem AWS e recursos locais. À medida que você adiciona e remove arquivos, o Amazon EFS expande e retrai automaticamente. Ele pode dimensionar sob demanda para petabytes sem interromper os aplicativos. 



### AMAZON EBS X AMAZON EFS

**Amazon EBS:** Um volume do Amazon EBS armazena dados em uma única Zona de Disponibilidade. 

Para anexar uma instância do Amazon EC2 a um volume do EBS, tanto a instância do Amazon EC2 quanto o volume do EBS devem residir na mesma Zona de Disponibilidade.

**Amazon EFS:** O Amazon EFS é um serviço regional. Ele armazena dados em várias Zonas de Disponibilidade e entre elas. 

O armazenamento duplicado permite que você acesse dados simultaneamente de todas as Zonas de Disponibilidade na Região em que um sistema de arquivos está localizado. Além disso, os servidores locais podem acessar o Amazon EFS usando o AWS Direct Connect.