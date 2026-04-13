
Translator

Portuguese

English (UK)
🌐 Projeto de Rede Corporativa com Integração Cliente e IoT

📌 Visão Geral

Este projeto simula uma infraestrutura de rede corporativa completa utilizando o Cisco Packet Tracer, com segmentação por departamentos, roteamento dinâmico, serviços de rede e comunicação com um cliente externo integrado a dispositivos IoT. Com a intenção de automatizar o processo de cuidado em fazendas, o IoT poderá otimizar a vivência de animais e otimizar também o tempo dos donos.

A arquitetura segue o modelo hierárquico de redes:

Camada de Acesso Camada de Distribuição Camada de Core (Roteamento) Conectividade WAN (ISP)

🏢 Estrutura da Rede (Empresa)

A rede foi segmentada utilizando VLANs para separar logicamente os departamentos:

Departamento VLAN Sub-rede

TI 10 192.168.1.0/25, Administração/Vendas 20 192.168.1.128/25, RH e Marketing 30 192.168.2.0/25, Servidores 40 192.168.2.128/25.

🔀 VLANs (Virtual LAN)

As VLANs foram utilizadas para:

Isolamento de tráfego Redução de broadcast Organização por setores Melhoria na segurança Configuração básica: Portas Access → dispositivos finais Portas Trunk → comunicação entre switches

🔄 Roteamento Inter-VLAN

Realizado através de switches multilayer (Camada 3), permitindo comunicação entre diferentes VLANs.

Exemplo:

interface vlan 10 ip address 192.168.1.1 255.255.255.128

🌐 Core e Roteamento WAN

Roteadores utilizados:

R1 (Núcleo) R2 (Núcleo) R3 (Cliente) Características: Links ponto a ponto utilizando sub-redes /30 Comunicação via ISP Redundância de caminhos

📡 Protocolo de Roteamento – OSPF

Foi implementado o OSPF (Open Shortest Path First) para:

Descoberta automática de rotas Alta disponibilidade Rápida convergência Benefícios: Failover automático Escalabilidade Menor configuração manual

🌍 Comunicação com o Cliente

Fluxo de comunicação:

Empresa → R1/R2 → ISP → R3 → Rede do Cliente

🏠 Rede do Cliente Sub-rede: 192.168.20.0/25 Dispositivos: PCs Impressora Switch local

📡 Integração IoT

O cliente possui dispositivos IoT conectados:

Sensor de temperatura Sensor de umidade Sensor de fumaça Sensor de presença/luz

Funcionalidades: Monitoramento remoto Comunicação via rede sem fio Controle por smartphone

📥 DHCP (Dynamic Host Configuration Protocol)

Responsável por fornecer automaticamente:

Endereço IP Gateway padrão Servidor DNS Benefícios: Automação Evita conflitos de IP Facilita administração

🌐 DNS (Domain Name System)

Servidor DNS configurado para resolução de nomes na rede.

📍 Configuração: IP do DNS: 192.168.2.131 Função: www.empresa.net → 192.168.2.131

Permite acesso por nome ao invés de IP. Se você quiser, pode testar no web browser de algum pc da empresa o "empresa.com" e entrará no site!

🖥️ Servidores

Localizados na VLAN 40:

Servidor DHCP Servidor DNS/Web (192.168.2.131) Servidor de E-mail 🔐 Segurança

Medidas implementadas:

Segmentação por VLAN Separação de servidores Redução de broadcast

🚀 Conclusão

Este projeto representa uma implementação completa de rede corporativa moderna, incluindo:

Comunicação interna eficiente Integração com redes externas Serviços essenciais (DHCP, DNS) Escalabilidade e redundância Aplicação de conceitos reais de mercado

📎 Tecnologias Utilizadas Cisco Packet Tracer, VLAN (802.1Q), OSPF, DHCP, DNS, IoT Simulation.

🌐 Corporate Network Project with Client and IoT Integration


📌 Overview


This project simulates a complete corporate network infrastructure using Cisco Packet Tracer, featuring departmental segmentation, dynamic routing, network services and communication with an external client integrated with IoT devices. With the aim of automating farm management processes, IoT can improve animal welfare and also save time for owners.


The architecture follows the hierarchical network model:


Access Layer Distribution Layer Core Layer (Routing) WAN Connectivity (ISP)


🏢 Network Structure (Company)


The network has been segmented using VLANs to logically separate the departments:


Department VLAN Subnet


IT 10 192.168.1.0/25, Administration/Sales 20 192.168.1.128/25, HR and Marketing 30 192.168.2.0/25, Servers 40 192.168.2.128/25.


🔀 VLANs (Virtual LAN)


VLANs were used for:


Traffic isolation Reduction of broadcast traffic Organisation by department Improved security Basic configuration: Access ports → end devices Trunk ports → communication between switches


🔄 Inter-VLAN Routing


Performed via multilayer (Layer 3) switches, enabling communication between different VLANs.


Example:


interface vlan 10 ip address 192.168.1.1 255.255.255.128


🌐 Core and WAN Routing


Routers used:


R1 (Core) R2 (Core) R3 (Client) Features: Point-to-point links using /30 subnets Communication via ISP Path redundancy


📡 Routing Protocol – OSPF


OSPF (Open Shortest Path First) was implemented for:


Automatic route discovery High availability Fast convergence Benefits: Automatic failover Scalability Reduced manual configuration


🌍 Communication with the Client


Communication flow:


Company → R1/R2 → ISP → R3 → Client Network


🏠 Client Network Subnet: 192.168.20.0/25 Devices: PCs Printer Local switch


📡 IoT Integration


The client has connected IoT devices:


Temperature sensor Humidity sensor Smoke sensor Presence/light sensor


Features: Remote monitoring Wireless network communication Smartphone control


📥 DHCP (Dynamic Host Configuration Protocol)


Responsible for automatically providing:


IP address Default gateway DNS server Benefits: Automation Prevents IP conflicts Simplifies administration


🌐 DNS (Domain Name System)


DNS server configured for name resolution on the network.


📍 Configuration: DNS IP: 192.168.2.131 Function: www.empresa.net → 192.168.2.131


Allows access by name rather than IP. If you wish, you can test ‘company.com’ in the web browser of any company PC and you will be taken to the website!


🖥️ Servers


Located on VLAN 40:


DHCP server DNS/Web server (192.168.2.131) Email server 🔐 Security


Measures implemented:


VLAN segmentation Server separation Broadcast reduction


🚀 Conclusion


This project represents a complete implementation of a modern corporate network, including:


Efficient internal communication Integration with external networks Essential services (DHCP, DNS) Scalability and redundancy Application of real-world concepts


📎 Technologies Used Cisco Packet Tracer, VLAN (802.1Q), OSPF, DHCP, DNS, IoT Simulation.
Glossary


