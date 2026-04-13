🌐 Projeto de Rede Corporativa com Integração Cliente e IoT

📌 Visão Geral

Este projeto simula uma infraestrutura de rede corporativa completa utilizando o Cisco Packet Tracer, com segmentação por departamentos, roteamento dinâmico, serviços de rede e comunicação com um cliente externo integrado a dispositivos IoT.
Com a intenção de automatizar o processo de cuidado em fazendas, o IoT poderá otimizar a vivência de animais e otimizar também o tempo dos donos.

A arquitetura segue o modelo hierárquico de redes:

Camada de Acesso
Camada de Distribuição
Camada de Core (Roteamento)
Conectividade WAN (ISP)

🏢 Estrutura da Rede (Empresa)

A rede foi segmentada utilizando VLANs para separar logicamente os departamentos:

Departamento	VLAN	Sub-rede

TI	10	192.168.1.0/25
Administração/Vendas	20	192.168.1.128/25
RH e Marketing	30	192.168.2.0/25
Servidores	40	192.168.2.128/25

🔀 VLANs (Virtual LAN)

As VLANs foram utilizadas para:

Isolamento de tráfego
Redução de broadcast
Organização por setores
Melhoria na segurança
Configuração básica:
Portas Access → dispositivos finais
Portas Trunk → comunicação entre switches

🔄 Roteamento Inter-VLAN

Realizado através de switches multilayer (Camada 3), permitindo comunicação entre diferentes VLANs.

Exemplo:

interface vlan 10
ip address 192.168.1.1 255.255.255.128

🌐 Core e Roteamento WAN

Roteadores utilizados:

R1 (Núcleo)
R2 (Núcleo)
R3 (Cliente)
Características:
Links ponto a ponto utilizando sub-redes /30
Comunicação via ISP
Redundância de caminhos

📡 Protocolo de Roteamento – OSPF

Foi implementado o OSPF (Open Shortest Path First) para:

Descoberta automática de rotas
Alta disponibilidade
Rápida convergência
Benefícios:
Failover automático
Escalabilidade
Menor configuração manual

🌍 Comunicação com o Cliente

Fluxo de comunicação:

Empresa → R1/R2 → ISP → R3 → Rede do Cliente

🏠 Rede do Cliente
Sub-rede: 192.168.20.0/25
Dispositivos:
PCs
Impressora
Switch local

📡 Integração IoT

O cliente possui dispositivos IoT conectados:

Sensor de temperatura
Sensor de umidade
Sensor de fumaça
Sensor de presença/luz

Funcionalidades:
Monitoramento remoto
Comunicação via rede sem fio
Controle por smartphone

📥 DHCP (Dynamic Host Configuration Protocol)

Responsável por fornecer automaticamente:

Endereço IP
Gateway padrão
Servidor DNS
Benefícios:
Automação
Evita conflitos de IP
Facilita administração

🌐 DNS (Domain Name System)

Servidor DNS configurado para resolução de nomes na rede.

📍 Configuração:
IP do DNS: 192.168.2.131
Função:
www.empresa.net → 192.168.2.131

Permite acesso por nome ao invés de IP.
Se você quiser, pode testar no web browser de algum pc da empresa o "empresa.com" e entrará no site!

🖥️ Servidores

Localizados na VLAN 40:

Servidor DHCP
Servidor DNS/Web (192.168.2.131)
Servidor de E-mail
🔐 Segurança

Medidas implementadas:

Segmentação por VLAN
Separação de servidores
Redução de broadcast

🚀 Conclusão

Este projeto representa uma implementação completa de rede corporativa moderna, incluindo:

Comunicação interna eficiente
Integração com redes externas
Serviços essenciais (DHCP, DNS)
Escalabilidade e redundância
Aplicação de conceitos reais de mercado

📎 Tecnologias Utilizadas
Cisco Packet Tracer
VLAN (802.1Q)
OSPF
DHCP
DNS
IoT Simulation
