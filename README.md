# 🖥️ Laboratório de Infraestrutura de TI — Active Directory, Redes e Virtualização

Laboratório prático de infraestrutura de TI desenvolvido em ambiente virtualizado, simulando uma rede cliente-servidor com **Windows Server**, **Windows 10**, **Active Directory** e serviços básicos de rede.

O projeto teve como objetivo praticar conceitos de **administração de sistemas, gerenciamento de usuários, redes e troubleshooting** em um ambiente semelhante ao encontrado em pequenas redes corporativas.

---

## 🛠️ Tecnologias e Ferramentas

- **Oracle VirtualBox**
- **Windows Server 2025**
- **Windows 10 Pro**
- **Active Directory Domain Services (AD DS)**
- **DNS**
- **IPv4**
- **NAT Network**
- **PowerShell / Prompt de Comando**

---

## 📸 Evidências do Laboratório

### 🏢 Ambiente Virtualizado e Rede

| VirtualBox | Rede NAT |
|:---:|:---:|
| <img src="https://github.com/user-attachments/assets/85255077-a095-4ea7-a8db-c38b637077c4" alt="Ambiente VirtualBox" width="100%"/> | <img src="https://github.com/user-attachments/assets/1849b77d-c865-4a1f-9d29-151d20ea56f1" alt="Rede NAT" width="100%"/> |

### 🌐 Configuração IPv4

| Windows Server | Windows 10 |
|:---:|:---:|
| <img src="https://github.com/user-attachments/assets/0f036d86-9fde-46d4-8776-428833437079" alt="IPv4 Windows Server" width="100%"/> | <img src="https://github.com/user-attachments/assets/ff9c00a9-2dbb-435c-be53-62c89935e4ca" alt="IPv4 Windows 10" width="100%"/> |

### 🔐 Active Directory e Autenticação

| Gerenciamento do AD | Logon no Domínio |
|:---:|:---:|
| <img src="https://github.com/user-attachments/assets/f83b8b9d-db0f-4123-9ad0-b9589affc07e" alt="Active Directory Users and Computers" width="100%"/> | <img src="https://github.com/user-attachments/assets/b2104c18-8d2d-4927-a4d8-c0799ac925a0" alt="Logon usuário de domínio" width="100%"/> |

### 🧪 Teste de Conectividade

<img src="https://github.com/user-attachments/assets/4e6acdd2-6c3e-42a5-983d-07d7b4954005" alt="Teste de conectividade com Ping" width="600"/>

---

## ⚙️ Implementação

### 1. Ambiente Virtual

Criação de máquinas virtuais utilizando **Oracle VirtualBox**, configuradas em uma **NAT Network** para simular uma pequena infraestrutura de rede.

### 2. Configuração de Rede

- Definição de endereçamento **IPv4 estático**.
- Configuração da rede NAT.
- Configuração do **DNS**.
- Validação da comunicação entre as máquinas utilizando `ping`.

### 3. Active Directory

Instalação da função **Active Directory Domain Services (AD DS)** e promoção do Windows Server a **Controlador de Domínio**.

Foram configurados:

- Domínio corporativo de laboratório.
- Unidades Organizacionais (OUs).
- Usuários.
- Grupos de segurança.
- Permissões e gerenciamento de contas.

### 4. Ingresso no Domínio

A estação **Windows 10 Pro** foi adicionada ao domínio e configurada para utilizar o servidor como DNS.

O funcionamento foi validado realizando login no Windows 10 utilizando uma **conta de usuário do domínio**.

---

## 🎯 Competências Praticadas

- Administração básica de **Windows Server**
- **Active Directory / AD DS**
- Gerenciamento de usuários e grupos
- Organização através de **OUs**
- Configuração básica de **IPv4 e DNS**
- Virtualização com **VirtualBox**
- Diagnóstico de conectividade de rede
- Configuração de ambiente cliente-servidor
- Troubleshooting básico de infraestrutura

---

## ✅ Resultado

Laboratório funcional com:

**Windows Server → Active Directory + DNS → Rede Virtual → Windows 10 Cliente → Autenticação no Domínio**

O projeto demonstra, na prática, conhecimentos básicos de **infraestrutura Windows, redes e administração de usuários**, servindo como ambiente de estudo e evidência técnica.

---

## 📂 Repositório

Projeto desenvolvido para fins de estudo e prática profissional.

**Autor:** Edson Jr.
```
