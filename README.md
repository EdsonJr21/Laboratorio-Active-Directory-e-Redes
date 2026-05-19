# 🖥️ Laboratório de Infraestrutura de TI: Active Directory, Redes e Virtualização

Este repositório documenta a criação e a configuração de um laboratório prático de infraestrutura de TI em um ambiente cliente-servidor totalmente virtualizado. O objetivo deste projeto é aplicar conceitos fundamentais de administração de sistemas Windows Server, serviços de rede essenciais (DNS, DHCP, IPv4) e gerenciamento centralizado de identidades com o Active Directory.

---

## 📸 Galeria de Evidências (Visão Rápida)

Para quem quer ver o laboratório em funcionamento imediatamente, aqui estão os principais marcos visuais do projeto organizados por etapas:

| 🏢 Ambiente & Infraestrutura | 🔐 Active Directory & Logons |
| :---: | :---: |
| **Página Inicial do Laboratório (VirtualBox)**<br><img src="https://github.com/user-attachments/assets/85255077-a095-4ea7-a8db-c38b637077c4" alt="Virtualização página inicial da VM" width="100%"/> | **Gerenciamento de Usuários e OUs (ADUC)**<br><img src="https://github.com/user-attachments/assets/f83b8b9d-db0f-4123-9ad0-b9589affc07e" alt="Users and Computers" width="100%"/> |
| **Infraestrutura de Rede NAT**<br><img src="https://github.com/user-attachments/assets/1849b77d-c865-4a1f-9d29-151d20ea56f1" alt="RedeNAT" width="100%"/> | **Logon do Administrador no Windows Server**<br><img src="https://github.com/user-attachments/assets/2f2cb755-0704-4390-9cce-0fee488ac5af" alt="loginServer" width="100%"/> |
| **Teste de Conectividade (Ping)**<br><img src="https://github.com/user-attachments/assets/4e6acdd2-6c3e-42a5-983d-07d7b4954005" alt="pingLab" width="100%"/> | **Logon de Usuário de Domínio no Windows 10**<br><img src="https://github.com/user-attachments/assets/b2104c18-8d2d-4927-a4d8-c0799ac925a0" alt="loginUser" width="100%"/> |

### 🌐 Configuração de Endereçamento IP Estático
| 🖥️ IPv4 do Windows Server | 💻 IPv4 da Estação Windows 10 |
| :---: | :---: |
| <img src="https://github.com/user-attachments/assets/0f036d86-9fde-46d4-8776-428833437079" alt="Ipv4Server" width="100%"/> | <img src="https://github.com/user-attachments/assets/ff9c00a9-2dbb-435c-be53-62c89935e4ca" alt="Ipv4Win10" width="100%"/> |

---

## 🛠️ Tecnologias e Ferramentas Utilizadas

* **Hipervisor:** Oracle VirtualBox
* **Sistema Operacional Servidor:** Windows Server 2025
* **Sistema Operacional Cliente:** Windows 10 Pro
* **Serviços de Rede:** Configuração manual de IPv4, Servidor DNS e NAT Network.
* **Serviços de Diretório:** Active Directory Domain Services (AD DS).

---

## 🚀 Detalhamento Técnico das Etapas

Abaixo estão descritos os fundamentos teóricos e práticos aplicados em cada fase do projeto:

### 1. Preparação do Ambiente Virtual
O laboratório foi construído isolando as máquinas virtuais em uma rede NAT dedicada para simular o perímetro de uma rede corporativa com acesso controlado à internet. Essa abordagem previne conflitos com a rede física local do host e garante o controle total do tráfego.

### 2. Configuração de Endereçamento IP Estático
Para garantir que o Servidor/Controlador de Domínio mantenha sempre o mesmo endereço de rede (requisito obrigatório para o funcionamento correto do Active Directory e das consultas de DNS), os parâmetros de rede foram definidos estaticamente. O cliente Windows 10 foi configurado para apontar diretamente para o servidor como seu DNS primário, permitindo que ele localize o domínio corporativo na rede.

### 3. Conectividade e Diagnóstico de Rede
Antes de executar a promoção do servidor a Controlador de Domínio, validou-se a comunicação fim a fim (camada 3 do modelo OSI) através de pacotes ICMP Request/Reply, garantindo a ausência de bloqueios restritivos em firewalls locais e assegurando que as máquinas conseguiam se enxergar mutuamente.

### 4. Implementação do Active Directory e Gerenciamento
Com a estabilidade de rede comprovada, a role de **Active Directory Domain Services (AD DS)** foi instalada. O servidor foi promovido a primeiro Controlador de Domínio (DC) de uma nova floresta. Através do console *Active Directory Users and Computers (ADUC)*, foram criadas Unidades Organizacionais (OUs) para estabelecer uma hierarquia clara de departamentos, grupos de segurança e contas de usuários.

### 5. Ingresso no Domínio e Validação de Logon
Após populadas as contas na base de dados do diretório, a estação de trabalho Windows 10 Pro realizou com sucesso o ingresso (Join) no domínio corporativo. O teste final consistiu em logar com uma conta de usuário comum diretamente do cliente, validando a autenticação centralizada e a aplicação das políticas de segurança do AD.

---

## 🎯 Aprendizados Adquiridos

1. **Planejamento de Infraestrutura:** Entendimento prático de como isolar ambientes de teste utilizando Redes NAT no VirtualBox.
2. **Serviços de Rede Essenciais:** Importância crítica do alinhamento correto do DNS para o funcionamento e validação do Active Directory.
3. **Administração Centralizada:** Criação, gerenciamento e controle de acessos de usuários através de Unidades Organizacionais e grupos dentro do AD DS.
4. **Resolução de Problemas (Troubleshooting):** Uso de ferramentas de terminal (como o `ping`) para diagnosticar falhas de comunicação pré-configuração de domínio.

---
