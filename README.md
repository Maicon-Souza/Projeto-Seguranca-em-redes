# Projeto: Segurança em Redes – Laboratório de Cybersecurity no Packet Tracer

## Objetivo
O objetivo deste projeto é criar uma rede corporativa simulada utilizando o **Cisco Packet Tracer**, aplicando práticas de segurança para proteger a infraestrutura contra ataques comuns. A rede envolve a configuração de diferentes tipos de dispositivos, a implementação de medidas de segurança e a realização de testes para validar a eficácia das proteções.

---

## Escopo do Projeto

### 1. **Configuração da Rede**
- **Setores**:
  - **Administração**: 5 PCs e 1 impressora de rede.
  - **Suporte Técnico**: 4 PCs e 1 servidor de atualizações.
  - **Servidores**: 1 Servidor Web, 1 Servidor DNS e 1 Servidor de E-mail.
- **Configuração de IP**:
  - Foi feito a distribuição de IP's na rede de maneira manual.
  - Tenho 3 redes diferentes 192.168.10.0 , 192.168.20.0 e 198.168.30.0
  - Todas com a Mascara de rede 255.255.255.0
- **Configuração de VLANs**:
  - Criação de VLANs para isolar o tráfego entre os setores de **Administração**, **Suporte Técnico** e **Servidores**.
  - Configuração de **Roteadores** e **Switches** para gerenciar o tráfego de rede entre as VLANs.
![image](https://github.com/user-attachments/assets/3e6b486d-a8a5-4a5d-8851-d31e7999622e)

### 2. **Configuração de Segurança**
- **ACLs (Access Control Lists)**:
  - Implementação de firewalls utilizando **ACLs** nos roteadores para controlar o tráfego de entrada e saída.
  - A configuração permite o acesso somente ao serviço **HTTPS**, bloqueando o HTTP por ser menos seguro.

- **Port Security**:
  - Configuração de **segurança nas portas de switch** para prevenir ataques de **MAC Spoofing**, limitando o número de endereços MAC permitidos em cada porta.

- **DHCP Snooping e Dynamic ARP Inspection (DAI)**:
  - Implementação de **DHCP Snooping** para proteger contra servidores DHCP não autorizados.
  - Implementação de **Dynamic ARP Inspection** (DAI) para proteger contra ataques **Man-in-the-Middle** (MITM) e **ARP Spoofing**.

### 3. **Testes de Segurança**
- **Simulação de ataques**:
  - **MAC Spoofing**: Simulação de um ataque de **Spoofing de MAC** para testar se o **Port Security** bloqueia o dispositivo malicioso.
  - **MITM (Man-in-the-Middle)**: Criação de um **ataque MITM** e observação da eficácia das proteções como **ARP Inspection**.
  - Utilização de **Packet Sniffer** no **Packet Tracer** para monitorar o tráfego e verificar a integridade das proteções de segurança.

---

## Tecnologias Utilizadas
- **Cisco Packet Tracer**: Ferramenta de simulação de redes utilizada para a criação da rede corporativa e configuração dos dispositivos.
- **CLI (Command Line Interface)**: Comandos utilizados para configurar switches, roteadores, firewalls, e as proteções de segurança.
- **Segurança em Redes**: Implementação de **ACLs**, **Port Security**, **DHCP Snooping**, **Dynamic ARP Inspection** e testes de ataques para validar a segurança da rede.

---

## Como Rodar o Projeto

1. **Abrir o Projeto no Packet Tracer**:
   - Importe o arquivo do projeto no **Cisco Packet Tracer**.
   - Verifique as configurações de **VLANs**, **ACLs**, **Port Security**, **DHCP Snooping**, e **DAI** aplicadas.
   
2. **Realizar Testes de Segurança**:
   - Utilize as ferramentas de **Packet Sniffer** para monitorar o tráfego.
   - Simule ataques de **MAC Spoofing** e **MITM** e observe se as proteções de segurança (como **Port Security** e **ARP Inspection**) estão funcionando corretamente.

---

## Comandos de Configuração

Aqui estão alguns exemplos de comandos utilizados para configurar a rede e as medidas de segurança:

### **Configuração de VLANs**
```bash
Switch(config)# vlan 10
Switch(config-vlan)# name Administração
Switch(config)# vlan 20
Switch(config-vlan)# name Suporte_Técnico
Switch(config)# vlan 30
Switch(config-vlan)# name Servidores

