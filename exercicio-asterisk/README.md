
# 📞 Exercicio Asterisk com Docker Compose

Este exercício demonstra como configurar e realizar chamadas VoIP usando **Asterisk** e **Linphone** em containers Docker.

---

## ✅ **Pré-requisitos**

- Docker
- Docker Compose
- Plugin Docker Compose (opcional)
- X11 rodando (para exibir a interface gráfica do Linphone)

---

## 🚀 **Passos para executar o exercício:**

---

### 🥇 **1º Passo: Preparar o ambiente**

- Copie os seguintes arquivos para a **mesma pasta**:

```
- docker-compose.yaml
- sip.conf
- extensions.conf
```

---

### 🥈 **2º Passo: Liberar o servidor X11**

Antes de iniciar o `docker-compose`, execute:

```bash
xhost +
```

> ✅ **Dica:** Isso permite que os containers acessem sua interface gráfica local.

---

### 🥉 **3º Passo: Iniciar os containers**

Execute um dos comandos abaixo, dependendo da sua instalação:

**Com Docker Compose clássico:**

```bash
docker-compose up -d
```

**Com plugin Docker Compose:**

```bash
docker compose up -d
```

> ✅ **Dica:** A flag `-d` inicia os containers em modo **detached** (em segundo plano).

---

### 🏅 **4º Passo: Configurar o Linphone**

Após subir os containers, abrirão **4 janelas** do Linphone:

- **2 janelas**: tela de **criação/login** de conta.
- **2 janelas**: interface principal do aplicativo.

➡️ Nas janelas de **criação/login**, escolha a opção:  
**"Já tenho uma conta SIP"**.

➡️ Preencha o formulário com as seguintes informações:

| Campo   | Valor   |
|---------|--------|
| Usuário | pedro  |
| Senha   | 1234   |
| Domínio | asterisk |

➡️ **Ignore** a opção de **proxy**.

➡️ Repita o processo para o outro usuário com os seguintes dados:

| Campo   | Valor   |
|---------|--------|
| Usuário | maria  |
| Senha   | 1234   |
| Domínio | asterisk |

---

### 🏆 **5º Passo: Realizar as chamadas**

Se tudo estiver configurado corretamente:

- De **Maria** → ligue para o número: **0800**  
- De **Pedro** → ligue para o número: **0900**

✅ A ligação deverá ser **bem-sucedida**!

---

## 🎯 **Resumo rápido:**

| Ação | Comando/Dica |
|---|---|
| Liberar X11 | `xhost +` |
| Subir containers | `docker-compose up -d` ou `docker compose up -d` |
| Login Linphone | Usuário: `pedro`/`maria` • Senha: `1234` • Domínio: `asterisk` |
| Chamada Maria → Pedro | `0800` |
| Chamada Pedro → Maria | `0900` |

---

## ❗ **Observações importantes:**

- **Não** feche as janelas do Linphone.
- Se a chamada **não conectar**, revise:
  - Configurações de rede no `docker-compose.yaml`.
  - Arquivos `sip.conf` e `extensions.conf`.
- Este exercício funciona bem em **ambientes Linux** com suporte a X11.

---

## 💡 **Dúvidas ou problemas?**

- Verifique se as portas **5060/UDP** e **RTP (16384-16400)** estão corretamente mapeadas.
- Confirme se a variável `DISPLAY` está configurada no ambiente.

---

✅ **Bom aprendizado!**  
