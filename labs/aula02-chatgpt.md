# Guia Prático — Importação da Máquina Virtual Ubuntu Server 22.04.4 LTS no Oracle VirtualBox 7.2

## Ambiente do Laboratório

- Instituição: SENAC São Paulo — Unidade Lapa Tito
- Sistema Operacional Host: Microsoft Windows 11
- Virtualizador: Oracle VirtualBox 7.2
- Imagem da VM: `UbuntuServer-OnPremises.ova`
- Local do arquivo: Pasta `Downloads`
- Rede do laboratório: `10.24.80.0`
- Hardware do laboratório:
  - CPU: Intel Core i7 14700K
  - RAM: 32GB
  - Armazenamento: 1TB

---

# Objetivo da Atividade

Importar a máquina virtual Ubuntu Server 22.04.4 LTS desenvolvida pelo Professor Robson Vaamonde, configurar a rede em modo Bridge (Ponte) utilizando a rede cabeada do laboratório e iniciar a máquina virtual para acesso remoto via SSH.

---

# Etapa 1 — Abrir o Oracle VirtualBox

## Passos

1. Clique no Menu Iniciar do Windows.
2. Pesquise por:

```text
Oracle VirtualBox
```

3. Clique no aplicativo.

### Ícone esperado

🟦 VirtualBox

---

# Etapa 2 — Importar a Máquina Virtual (.OVA)

## Passos

1. No menu superior do VirtualBox clique em:

```text
Arquivo → Importar Appliance
```

📦 Ícone: Importar

2. Clique no ícone da pasta 📁.

3. Navegue até:

```text
Downloads
```

4. Selecione o arquivo:

```text
UbuntuServer-OnPremises.ova
```

5. Clique em:

```text
Próximo
```

---

# Etapa 3 — Revisar as Configurações da Importação

O VirtualBox exibirá as configurações da máquina virtual.

## Conferir os seguintes itens:

| Configuração | Valor Esperado |
|---|---|
| Nome da VM | UbuntuServer-OnPremises |
| Tipo | Linux |
| Versão | Ubuntu (64-bit) |
| Memória RAM | Conforme imagem importada |
| Disco Virtual | VDI/VMDK |

---

## Importar

1. Clique em:

```text
Finalizar
```

⏳ Aguarde o término da importação.

O processo pode levar alguns minutos.

---

# Etapa 4 — Configurar Rede em Modo Bridge (Ponte)

## Objetivo

Permitir que a máquina virtual receba IP da rede física do laboratório (`10.24.80.0`) e possa ser acessada remotamente via SSH.

---

## Passos

1. Selecione a VM:

```text
UbuntuServer-OnPremises
```

2. Clique em:

```text
Configurações
```

⚙️ Ícone: Engrenagem

---

## Configurar Adaptador de Rede

1. No menu lateral clique em:

```text
Rede
```

2. Em "Adaptador 1":

### Marque:

✅ Habilitar Placa de Rede

---

## Alterar modo de rede

No campo:

```text
Conectado a:
```

Selecione:

```text
Placa em modo Bridge
```

---

## Selecionar Interface Física

No campo:

```text
Nome:
```

Selecione a placa de rede cabeada do laboratório.

Exemplos:

```text
Intel Ethernet
Realtek PCIe
Ethernet
```

⚠️ Não selecionar Wi‑Fi.

---

## Modo Promíscuo

Alterar para:

```text
Permitir Tudo
```

---

## Cabo Conectado

Verifique:

✅ Cabo Conectado

---

## Salvar Configuração

Clique em:

```text
OK
```

---

# Etapa 5 — Iniciar a Máquina Virtual

## Passos

1. Selecione a VM.
2. Clique em:

```text
Iniciar
```

🟢 Ícone: Start

---

# Etapa 6 — Login no Ubuntu Server

Após o boot do sistema:

## Informar usuário e senha

Utilize as credenciais fornecidas pelo Professor.

Exemplo:

```text
login: aluno
senha: ********
```

---

# Etapa 7 — Verificar Endereço IP da Máquina Virtual

## Executar o comando:

```bash
ip addr
```

ou

```bash
ip a
```

---

## Localizar interface de rede

Exemplo:

```text
enp0s3
```

---

## Identificar IP recebido

Exemplo:

```text
10.24.80.120
```

⚠️ O IP deve estar na mesma rede do laboratório:

```text
10.24.80.0
```

---

# Etapa 8 — Testar Conectividade

## Testar comunicação com gateway

```bash
ping 10.24.80.1
```

---

## Testar acesso à Internet

```bash
ping 8.8.8.8
```

---

## Resultado esperado

Recebimento de respostas:

```text
64 bytes from...
```

---

# Etapa 9 — Verificar Serviço SSH

## Verificar status do OpenSSH Server

Executar:

```bash
sudo systemctl status ssh
```

---

## Resultado esperado

```text
active (running)
```

✅ Serviço SSH ativo.

---

# Etapa 10 — Acesso Remoto via SSH

## No Windows 11

Abrir:

```text
PowerShell
```

ou

```text
Prompt de Comando
```

---

## Executar conexão SSH

Substituir pelo IP identificado na VM:

```bash
ssh usuario@10.24.80.120
```

Exemplo:

```bash
ssh aluno@10.24.80.120
```

---

## Aceitar chave SSH

Na primeira conexão será exibida a mensagem:

```text
Are you sure you want to continue connecting?
```

Digite:

```text
yes
```

---

## Informar senha

Digite a senha do usuário Linux.

---

# Resultado Esperado

Ao finalizar:

✅ Máquina virtual importada com sucesso

✅ Rede configurada em modo Bridge

✅ VM recebendo IP da rede 10.24.80.0

✅ SSH funcionando corretamente

✅ Ambiente pronto para as aulas práticas de Inteligência Artificial

---

# Dicas Importantes

## Caso a VM não receba IP

Verifique:

- Cabo de rede conectado
- Adaptador em modo Bridge
- Interface Ethernet correta selecionada
- DHCP ativo na rede do laboratório

---

## Caso o SSH não funcione

Executar na VM:

```bash
sudo systemctl restart ssh
```

Depois testar novamente.

---

# Comandos Utilizados

## Verificar IP

```bash
ip a
```

---

## Testar rede

```bash
ping 8.8.8.8
```

---

## Verificar SSH

```bash
sudo systemctl status ssh
```

---

## Reiniciar SSH

```bash
sudo systemctl restart ssh
```

---

# Conclusão

A máquina virtual Ubuntu Server 22.04.4 LTS foi importada no Oracle VirtualBox 7.2, configurada em modo Bridge utilizando a rede física cabeada do laboratório SENAC Lapa Tito e preparada para acesso remoto via SSH, permitindo a utilização do ambiente nas aulas práticas de Inteligência Artificial aplicada a Redes de Computadores.

