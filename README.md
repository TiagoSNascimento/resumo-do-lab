# resumo-do-lab
Este repositório contém o resumo das lições aprendidas durante o desenvolvimento do lab na DIO.


Este módulo se concentra em alguns dos serviços de computador e serviços de rede disponíveis no Azure.
Objetivos de aprendizagem

Ao concluir este módulo, você poderá:

    Comparar tipos de computação, incluindo instâncias de contêiner, máquinas virtuais e funções
    Descrever opções de VM (máquina virtual), incluindo VMs, Conjuntos de Dimensionamento de Máquinas Virtuais, conjuntos de disponibilidade, Área de Trabalho Virtual do Azure
    Descrever os recursos necessários para máquinas virtuais
    Descrever opções de hospedagem de aplicativos, incluindo Aplicativos Web do Azure, contêineres e máquinas virtuais
    Descrever a rede virtual, incluindo a finalidade das Redes Virtuais do Azure, sub-redes virtuais do Azure, emparelhamento, DNS do Azure, Gateway de VPN e ExpressRoute
    Definir pontos de extremidade públicos e privados.


    A Rede Virtual do Azure é um serviço que fornece o bloco de construção fundamental para sua rede privada no Azure. Uma instância do serviço (uma rede virtual) permite que muitos tipos de recursos do Azure se comuniquem com segurança entre si, com a Internet e com as redes locais. Esses recursos do Azure incluem máquinas virtuais (VMs).

Uma rede virtual é semelhante a uma rede tradicional que você operaria em seu datacenter. Mas traz benefícios extras da infraestrutura do Azure, como escala, disponibilidade e isolamento.
Por que usar uma rede virtual do Azure?

Os principais cenários que você pode realizar com uma rede virtual incluem:

    Comunicação dos recursos do Azure com a Internet.

    Comunicação entre os recursos do Azure.

    Comunicação com os recursos locais.

    Filtragem do tráfego de rede.

    Roteamento do tráfego de rede.

    Integração com serviços do Azure.

Comunicação com a Internet

Todos os recursos em uma rede virtual podem comunicar a saída com a Internet, por padrão. Você também pode usar um endereço IP público, um gateway NAT ou um balanceador de carga público para gerenciar suas conexões de saída. Você pode comunicar a entrada com um recurso atribuindo um endereço IP público ou um balanceador de carga público.

Quando você estiver usando apenas um balanceador de carga padrão interno, a conectividade de saída não estará disponível até que você defina como deseja que as conexões de saída funcionem com um endereço IP público no nível da instância ou um balanceador de carga público.
Comunicação entre recursos do Azure

Os recursos do Azure se comunicam com segurança entre si de uma das seguintes maneiras:

    Rede virtual: você pode implantar VMs e outros tipos de recursos do Azure em uma rede virtual. Exemplos de recursos incluem Ambientes do Serviço de Aplicativo, Serviço de Kubernetes do Azure (AKS) e Conjuntos de Dimensionamento de Máquinas Virtuais do Microsoft Azure. Para ver uma lista completa dos recursos do Azure que você pode implantar em uma rede virtual, consulte Implantar serviços dedicados do Azure em redes virtuais.

Observação

Para mover uma máquina virtual de uma rede virtual para outra, você deve excluir e recriar a máquina virtual na nova rede virtual. Os discos da máquina virtual podem ser mantidos para uso na nova máquina virtual.

    Pontos de extremidade de serviço de rede virtual : você pode estender o espaço de endereço privado de sua rede virtual e a identidade de sua rede virtual para os serviços do Azure, por meio de uma conexão direta. Alguns exemplos de recursos incluem as contas do Armazenamento do Microsoft Azure e o Banco de Dados SQL do Azure. Os pontos de extremidade de serviço permitem que você proteja os recursos essenciais do serviço do Azure somente em uma rede virtual. Para obter mais detalhes, confira Pontos de extremidade de serviço de rede virtual.

    Emparelhamento de rede virtual do Azure: você pode conectar redes virtuais usando o emparelhamento virtual. Os recursos em qualquer rede virtual podem se comunicar entre si. As redes virtuais que você conecta podem estar nas mesmas regiões do Azure ou diferentes. Para saber mais, confira Emparelhamento de rede virtual.

Comunicação com os recursos locais

Você pode conectar seus computadores e redes locais a uma rede virtual usando qualquer uma das seguintes opções:

    VPN (rede virtual privada) ponto a site: estabelecida entre uma rede virtual e um único computador em sua rede. Cada computador que deseja estabelecer conectividade com uma rede virtual precisa configurar suas conexões. Esse tipo de conexão é útil se você estiver apenas começando a usar o Azure ou para desenvolvedores, pois isso requer pouca ou nenhuma alteração em uma rede existente. A comunicação entre seu computador e uma rede virtual é enviada via Internet, por um túnel criptografado. Para saber mais, consulte Sobre a VPN ponto a ponto.

    VPN site a site: estabelecida entre o dispositivo VPN local e um Gateway de VPN do Azure implantado em uma rede virtual. Esse tipo de conexão permite que qualquer recurso local que você autorizou acesse uma rede virtual. A comunicação entre o dispositivo VPN local e um gateway de VPN do Azure é enviada via Internet, por um túnel criptografado. Para obter mais informações, confira VPN site a site.

    Azure ExpressRoute: estabelecido entre sua rede e o Azure, por meio de um parceiro de ExpressRoute. Essa conexão é privada. O tráfego não passa pela Internet. Para saber mais, consulte O que é o Azure ExpressRoute?.

Filtrar tráfego de rede

Você pode filtrar o tráfego de rede entre sub-redes usando uma das seguintes opções ou ambas:

    Grupos de segurança de rede: grupos de segurança de rede e grupos de segurança de aplicativo podem conter várias regras de segurança de entrada e saída. Essas regras permitem a você filtrar o tráfego de e para recursos por endereço IP de origem e de destino, porta e protocolo. Para saber mais, consulte Grupos de segurança de rede e Grupos de segurança de aplicativos.

    Soluções de virtualização de rede: uma solução de virtualização de rede é uma VM que executa uma função de rede, como um firewall ou uma otimização WAN. Para ver uma lista de dispositivos virtuais de rede disponíveis que você pode implantar em uma rede virtual, acesse Azure Marketplace.

Rotear tráfego de rede

O Azure roteia o tráfego entre sub-redes, redes virtuais conectadas, redes locais e a Internet, por padrão. Você pode implementar uma ou ambas as opções a seguir para substituir as rotas padrão que o Azure cria:

    Tabelas de roteamento: é possível criar tabelas de roteamento personalizadas que controlam para onde o tráfego será roteado para cada sub-rede.

    Rotas BGP (Border gateway protocol): se você conectar sua rede virtual à rede local usando um Gateway de VPN do Azure ou uma conexão do ExpressRoute, será possível propagar as rotas BGP locais para suas redes virtuais.

Integrar aos serviços do Azure

A integração dos serviços do Azure a uma rede virtual do Azure permite o acesso privado ao serviço de máquinas virtuais ou recursos de computação na rede virtual. Você pode usar as seguintes opções para essa integração:

    Implante instâncias dedicadas do serviço em uma rede virtual. Os serviços podem ser acessados de maneira privada dentro da rede virtual e de redes locais.

    Use o Link Privado do Azure para acessar de forma privada uma instância específica do serviço a partir da sua rede virtual e de redes locais.

    Acesse o serviço em pontos de extremidade públicos estendendo uma rede virtual para o serviço, por meio de pontos de extremidade de serviço. Pontos de extremidade de serviço permitem que os recursos de serviço da rede virtual sejam protegidos.

Limites

Há limites para o número de recursos do Azure que você pode implantar. A maioria dos limites de rede do Azure estão com os valores máximo. No entanto, você pode aumentar certos limites de rede. Para obter mais informações, consulte Limites de rede.
Redes virtuais e zonas de disponibilidade

As redes virtuais e sub-redes abrangem todas as zonas de disponibilidade de uma região. Você não precisa dividi-las por zonas de disponibilidade para acomodar recursos zonais. Por exemplo, se você configurar uma VM zonal, não precisará levar em consideração a rede virtual ao selecionar a zona de disponibilidade para a VM. O mesmo é verdadeiro para outros recursos de zona.
Preços

Não há custo para usar a Rede Virtual do Azure. Ela é gratuita. Cobranças padrão se aplicam a recursos, como VMs e outros produtos. Para saber mais, consulte Preços da Rede Virtual e a calculadora de preços do Azure.


