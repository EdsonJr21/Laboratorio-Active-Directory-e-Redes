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

As etapas abaixo descrevem a ordem de implementação do laboratório, acompanhadas das capturas de tela que comprovam o funcionamento de cada recurso:

### 1. Preparação do Ambiente Virtual
O laboratório foi construído isolando as máquinas virtuais em uma rede NAT dedicada para simular uma rede corporativa com acesso controlado à internet.
* **Página Inicial da VM:** Interface do gerenciador do VirtualBox com as máquinas criadas.
  * *Evidência:* `Virtualização página inicial da VM.png`
* **Configuração de Rede:** Criação e atribuição da Rede NAT para as VMs do laboratório.
  * *Evidência:* `RedeNAT.png`

### 2. Configuração de Endereçamento IP Estático
Para garantir que o Servidor/Controlador de Domínio mantenha sempre o mesmo endereço de rede (requisito obrigatório para o AD e DNS), os parâmetros de rede foram definidos manualmente.
* **IPv4 no Windows Server:** Configuração de IP estático, máscara de sub-rede, gateway e apontamento do DNS para ele mesmo.
  * *Evidência:* `Ipv4Server.png`
* **IPv4 no Windows 10:** Configuração da máquina cliente para fazer parte da mesma sub-rede e apontar para o IP do Windows Server como servidor DNS primário.
  * *Evidência:* `Ipv4Win10.png`

### 3. Conectividade e Diagnóstico de Rede
Antes de promover o domínio, foi realizado o teste de comunicação básica ICMP entre a máquina cliente e o servidor para validar o roteamento e as configurações de firewall da rede virtual.
* **Teste de Ping:** Comando `ping` executado com sucesso entre o cliente e o servidor.
  * *Evidência:* `pingLab.png`

### 4. Implementação do Active Directory e Gerenciamento
Com a conectividade validada, a função de **Active Directory Domain Services (AD DS)** foi instalada no Windows Server, promovendo-o a Controlador de Domínio (DC).
* **Active Directory Users and Computers (ADUC):** Estruturação de Unidades Organizacionais (OUs) para organizar os departamentos, grupos de segurança e contas de usuários da corporação.
  * *Evidência:* `Users and Computers.png`

### 5. Ingresso no Domínio e Validação de Logon
Após a configuração das contas no AD, a estação de trabalho Windows 10 Pro foi ingressada com sucesso no domínio corporativo criado.
* **Logon do Administrador no Servidor:** Tela de autenticação administrativa do Windows Server.
  * *Evidência:* `loginServer.png`
* **Logon de Usuário do Domínio no Cliente:** Tela de login no Windows 10 validando a autenticação de uma conta de usuário comum gerenciada centralmente pelo Active Directory.
  * *Evidência:* `loginUser.png`

---

## 🎯 Aprendizados Adquiridos

1. **Planejamento de Infraestrutura:** Entendimento prático de como isolar ambientes de teste utilizando Redes NAT no VirtualBox.
2. **Serviços de Rede Essenciais:** Importância crítica do alinhamento correto do DNS para o funcionamento e validação do Active Directory.
3. **Administração Centralizada:** Criação, gerenciamento e controle de acessos de usuários através de Unidades Organizacionais e grupos dentro do AD DS.
4. **Resolução de Problemas (Troubleshooting):** Uso de ferramentas de terminal (como o `ping`) para diagnosticar falhas de comunicação pré-configuração de domínio.

---