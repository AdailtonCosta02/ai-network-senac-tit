# 📘 Documentação de Rede — Estação Windows

## 📂 Categoria: Informações Gerais do Equipamento

| Informação | Valor |
|---|---|
| 🖥️ Nome do Host | `TIT0728096W11-1` |
| 🌐 Domínio DNS | `senacsp.edu.br` |
| 🔀 Tipo de Nó | Híbrido |
| 📡 Roteamento IP | Não habilitado |
| 🧩 Proxy WINS | Não habilitado |
| 🔍 Sufixo DNS de Pesquisa | `senacsp.edu.br` |

### 📝 Resumo
Este equipamento está integrado ao domínio institucional `senacsp.edu.br`, indicando que faz parte de uma rede corporativa gerenciada. O roteamento IP não está habilitado, portanto o computador não atua como roteador de rede.

---

# 📂 Categoria: Adaptadores de Rede

---

## 📁 Sub-Categoria: Adaptador Físico Principal

| Informação | Valor |
|---|---|
| 🖧 Nome do Adaptador | Ethernet |
| 🏭 Fabricante / Modelo | Intel(R) Ethernet Connection (17) I219-LM |
| 🔢 Endereço MAC | `D8-43-AE-E0-B6-B7` |
| 📥 DHCP | Habilitado |
| 🌍 IPv4 | `10.24.82.46` |
| 🎭 Máscara de Sub-rede | `255.255.255.0` |
| 🚪 Gateway Padrão | `10.24.82.1` |
| 📡 DHCP Server | `10.24.40.190` |
| 🧠 DNS Primário | `10.24.40.190` |
| 🧠 DNS Secundário | `10.1.1.195` |
| 🧠 DNS Terciário | `10.1.1.242` |
| 🔗 IPv6 Local | `fe80::5218:72df:65d7:38e1%12` |
| 🕒 Lease DHCP Obtido | `26/05/2026 19:59:46` |
| ⏳ Lease DHCP Expira | `27/05/2026 03:59:47` |
| 📛 NetBIOS | Habilitado |

### 📝 Resumo
O computador recebe automaticamente seu endereço IP através do servidor DHCP da rede corporativa. O gateway `10.24.82.1` é responsável pela comunicação externa da máquina com outras redes e internet. Os servidores DNS fazem a tradução de nomes como `google.com` para endereços IP.

---

## 📁 Sub-Categoria: Adaptador Virtual (VirtualBox)

| Informação | Valor |
|---|---|
| 🖧 Nome do Adaptador | Ethernet 2 |
| 🏭 Descrição | VirtualBox Host-Only Ethernet Adapter |
| 🔢 Endereço MAC | `0A-00-27-00-00-08` |
| 📥 DHCP | Não habilitado |
| 🌍 IPv4 | `192.168.56.1` |
| 🎭 Máscara de Sub-rede | `255.255.255.0` |
| 🚪 Gateway Padrão | Não configurado |
| 🔗 IPv6 Local | `fe80::711a:95b2:d95f:882b%8` |
| 📛 NetBIOS | Habilitado |

### 📝 Resumo
Este adaptador pertence ao VirtualBox e é utilizado para comunicação entre máquinas virtuais e o computador físico. Não possui acesso direto à internet, pois não há gateway configurado.

---

# 📂 Categoria: Tabela de Rotas

## 📁 Sub-Categoria: Rotas Ativas

| Rede Destino | Máscara | Gateway | Interface | Métrica |
|---|---|---|---|---|
| `0.0.0.0` | `0.0.0.0` | `10.24.82.1` | `10.24.82.46` | 35 |
| `10.24.82.0` | `255.255.255.0` | No vínculo | `10.24.82.46` | 291 |
| `192.168.56.0` | `255.255.255.0` | No vínculo | `192.168.56.1` | 281 |
| `127.0.0.0` | `255.0.0.0` | Loopback | `127.0.0.1` | 331 |

### 📝 Resumo
A rota padrão (`0.0.0.0`) indica que todo tráfego externo é enviado para o gateway `10.24.82.1`. As demais rotas representam redes locais diretamente conectadas ao equipamento.

---

# 📂 Categoria: Servidores DNS

| Tipo | Endereço |
|---|---|
| 🧠 DNS Principal | `10.24.40.190` |
| 🧠 DNS Secundário | `10.1.1.195` |
| 🧠 DNS Terciário | `10.1.1.242` |

### 📝 Resumo
Os servidores DNS são responsáveis por converter nomes amigáveis, como `google.com`, em endereços IP utilizados na comunicação da rede.

---

# 📂 Categoria: Testes de Resolução DNS

## 📁 Sub-Categoria: Consulta DNS — dns.google

| Item | Resultado |
|---|---|
| 🌐 Nome Consultado | `dns.google` |
| 📍 Endereço IP Retornado | `8.8.8.8` |
| 🖥️ Servidor DNS Utilizado | `10.24.40.190` |

### 📝 Resumo
O teste confirma que o servidor DNS corporativo consegue resolver corretamente nomes externos da internet.

---

## 📁 Sub-Categoria: Consulta DNS — google.com

| Item | Resultado |
|---|---|
| 🌐 Nome Consultado | `google.com` |
| 🌍 IPv4 | `142.250.79.206` |
| 🌍 IPv6 | `2800:3f0:4001:837::200e` |
| 🖥️ Servidor DNS Utilizado | `10.24.40.190` |

### 📝 Resumo
O domínio `google.com` foi resolvido com sucesso tanto para IPv4 quanto para IPv6, demonstrando funcionamento adequado do serviço DNS.

---

# 📂 Categoria: Testes de Conectividade

## 📁 Sub-Categoria: Ping — DNS Google (8.8.8.8)

| Métrica | Resultado |
|---|---|
| 📦 Pacotes Enviados | 4 |
| 📥 Pacotes Recebidos | 4 |
| ❌ Perdas | 0% |
| ⚡ Latência Mínima | 3 ms |
| ⚡ Latência Máxima | 5 ms |
| ⚡ Latência Média | 4 ms |

### 📝 Resumo
O teste de conectividade com o servidor DNS público do Google apresentou resposta estável e sem perda de pacotes, indicando comunicação adequada com a internet.

---

## 📁 Sub-Categoria: Ping — google.com

| Métrica | Resultado |
|---|---|
| 📦 Pacotes Enviados | 4 |
| 📥 Pacotes Recebidos | 4 |
| ❌ Perdas | 0% |
| ⚡ Latência Média | 3 ms |

### 📝 Resumo
O equipamento possui acesso funcional à internet e consegue alcançar serviços externos com baixa latência e sem falhas de comunicação.

---

# 📂 Categoria: Conclusão Geral da Análise

| Item Avaliado | Status |
|---|---|
| 🌐 Conectividade de Rede | ✅ Operacional |
| 🧠 Resolução DNS | ✅ Funcionando |
| 📡 Comunicação com Gateway | ✅ Ativa |
| 🌍 Acesso à Internet | ✅ Disponível |
| 🖥️ Adaptador Físico | ✅ Operacional |
| 🧪 Adaptador Virtual | ✅ Operacional |
| 📶 Perda de Pacotes | ✅ Nenhuma Detectada |

### 📝 Resumo Executivo
A estação analisada apresenta funcionamento normal da infraestrutura de rede. Os serviços essenciais, incluindo DHCP, DNS, gateway e conectividade externa, estão operacionais. Os testes realizados demonstram baixa latência, ausência de perda de pacotes e resolução correta de nomes DNS.
