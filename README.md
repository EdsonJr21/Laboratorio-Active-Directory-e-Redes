# 🖥️ Laboratório de Infraestrutura de TI: Active Directory, Redes e Virtualização

Este repositório documenta a criação e a configuração de um laboratório prático de infraestrutura de TI em um ambiente cliente-servidor totalmente virtualizado. O objetivo deste projeto é aplicar conceitos fundamentais de administração de sistemas Windows Server, serviços de rede essenciais (DNS, DHCP, IPv4) e gerenciamento centralizado de identidades com o Active Directory.

---

## 🛠️ Tecnologias e Ferramentas Utilizadas

* **Hipervisor:** Oracle VirtualBox
* **Sistema Operacional Servidor:** Windows Server 2025
* **Sistema Operacional Cliente:** Windows 10 Pro
* **Serviços de Rede:** Configuração manual de IPv4, Servidor DNS e NAT Network.
* **Serviços de Diretório:** Active Directory Domain Services (AD DS).

---

## 🚀 Etapas do Projeto e Evidências

As etapas abaixo descrevem a ordem de implementação do laboratório, acompanhadas das capturas de tela organizadas de forma limpa e padronizada para melhor legibilidade:

### 1. Preparação do Ambiente Virtual
O laboratório foi construído isolando as máquinas virtuais em uma rede NAT dedicada para simular uma rede corporativa com acesso controlado à internet.

* **Página Inicial da VM:** Interface do gerenciador do VirtualBox demonstrando o provisionamento e o status das máquinas virtuais criadas.
  <br>
  <img src="https://github.com/user-attachments/assets/85255077-a095-4ea7-a8db-c38b637077c4" alt="Virtualização página inicial da VM" width="100%"/>

* **Configuração de Rede:** Criação e atribuição da infraestrutura de Rede NAT para o isolamento seguro das VMs.
  <br>
  <img src="https://github.com/user-attachments/assets/1849b77d-c865-4a1f-9d29-151d20ea56f1" alt="RedeNAT" width="85%"/>

---

### 2. Configuração de Endereçamento IP Estático
Para garantir que o Servidor/Controlador de Domínio mantenha sempre o mesmo endereço de rede (requisito obrigatório para o funcionamento correto do Active Directory e das consultas de DNS), os parâmetros de rede foram definidos estaticamente.

* **IPv4 no Windows Server:** Configuração manual de IP estático, máscara de sub-rede, gateway padrão e apontamento do DNS para a interface de loopback/IP local do servidor.
  <br>
  <img src="https://github.com/user-attachments/assets/0f036d86-9fde-46d4-8776-428833437079" alt="Ipv4Server" width="45%"/>

* **IPv4 no Windows 10:** Parametrização da máquina cliente para operar no mesmo escopo de sub-rede, utilizando o endereço IP do Windows Server como Servidor DNS Primário.
  <br>
  <img src="https://github.com/user-attachments/assets/ff9c00a9-2dbb-435c-be53-62c89935e4ca" alt="Ipv4Win10" width="45%"/>

---

### 3. Conectividade e Diagnóstico de Rede
Antes de executar a promoção do servidor a Controlador de Domínio, validou-se a comunicação fim a fim (camada 3 do modelo OSI) através de pacotes ICMP Request/Reply, garantindo a ausência de bloqueios restritivos em firewalls locais.

* **Teste de Ping:** Comando `ping` executado com total sucesso partindo do cliente em direção ao servidor.
  <br>
  <img src="https://github.com/user-attachments/assets/4e6acdd2-6c3e-42a5-983d-07d7b4954005" alt="pingLab" width="85%"/>

---

### 4. Implementação do Active Directory e Gerenciamento
Com a estabilidade de rede comprovada, a role de **Active Directory Domain Services (AD DS)** foi instalada. O servidor foi promovido a primeiro Controlador de Domínio (DC) de uma nova floresta.

* **Active Directory Users and Computers (ADUC):** Criação e estruturação lógica de Unidades Organizacionais (OUs), estabelecendo uma hierarquia clara para os departamentos corporativos, grupos de segurança e contas de usuários.
  <br>
  <img src="https://github.com/user-attachments/assets/f83b8b9d-db0f-4123-9ad0-b9589affc07e" alt="Users and Computers" width="75%"/>

---

### 5. Ingresso no Domínio e Validação de Logon
Após populadas as contas na base de dados do diretório, a estação de trabalho Windows 10 Pro realizou com sucesso o ingresso (Join) no domínio corporativo.

* **Logon do Administrador no Servidor:** Tela de autenticação e validação de credenciais administrativas do Windows Server.
  <br>
  <img src="https://github.com/user-attachments/assets/2f2cb755-0704-4390-9cce-0fee488ac5af" alt="loginServer" width="85%"/>

* **Logon de Usuário do Domínio no Cliente:** Tela de autenticação em ambiente Windows 10 Pro, comprovando a eficácia e centralização de credenciais operadas pelo Active Directory.
  <br>
  <img src="https://github.com/user-attachments/assets/b2104c18-8d2d-4927-a4d8-c0799ac925a0" alt="loginUser" width="85%"/>

---

## 🎯 Aprendizados Adquiridos

1. **Planejamento de Infraestrutura:** Entendimento prático de como isolar ambientes de teste utilizando Redes NAT no VirtualBox.
2. **Serviços de Rede Essenciais:** Importância crítica do alinhamento correto do DNS para o funcionamento e validação do Active Directory.
3. **Administração Centralizada:** Criação, gerenciamento e controle de acessos de usuários através de Unidades Organizacionais e grupos dentro do AD DS.
4. **Resolução de Problemas (Troubleshooting):** Uso de ferramentas de terminal (como o `ping`) para diagnosticar falhas de comunicação pré-configuração de domínio.

---
