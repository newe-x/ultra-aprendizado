# 🧪 Labs Avançados de Redes com Foco em Segurança

Uma coletânea de laboratórios práticos com foco em ataques e defesas em ambientes de rede. Cada lab possui objetivo, ferramentas necessárias, tarefas práticas e perguntas orientadoras.

---

## 🔹 Lab 1 – ARP Poisoning + Sniffing de Credenciais

- **🎯 Objetivo:** Realizar ataque de ARP Spoofing e capturar tráfego entre cliente e gateway.  
- **🛠 Ferramentas:** `ettercap`, `arpspoof`, `wireshark`  
- **📚 Módulo:** Segurança de redes locais / MitM

### ✅ Tarefas
- [ ] Configurar três máquinas: atacante, vítima e gateway.
- [ ] Realizar ARP poisoning na rede local.
- [ ] Capturar e analisar tráfego para extrair dados de autenticação.

### ❓ Perguntas
- Qual o comportamento da tabela ARP da vítima após o ataque?
- Foi possível capturar senhas em texto claro? Por quê?

---

## 🔹 Lab 2 – VLAN Hopping (Switch Spoofing + Double Tagging)

- **🎯 Objetivo:** Simular ataque para escapar da segmentação por VLAN.  
- **🛠 Ferramentas:** `scapy`, `vconfig`, `GNS3` ou `EVE-NG`  
- **📚 Módulo:** Segmentação de redes e VLANs

### ✅ Tarefas
- [ ] Configurar duas VLANs distintas em um switch virtual.
- [ ] Simular ataque com switch spoofing.
- [ ] Enviar pacotes com dupla marcação (double tagging).

### ❓ Perguntas
- O que é necessário para que um atacante acesse outra VLAN?
- Como prevenir esse tipo de ataque em switches reais?

---

## 🔹 Lab 3 – Pivoting com SSH e Port Forwarding

- **🎯 Objetivo:** Usar uma máquina comprometida como pivot para acessar outras redes.  
- **🛠 Ferramentas:** `ssh`, `proxychains`, `socat`, `nmap`  
- **📚 Módulo:** Movimento lateral e exploração interna

### ✅ Tarefas
- [ ] Comprometer uma máquina na DMZ.
- [ ] Utilizar port forwarding para atingir rede interna.
- [ ] Redirecionar ataques com proxychains.

### ❓ Perguntas
- Quais portas devem estar abertas para permitir forwarding reverso?
- Como o proxychains ajuda em ataques multi-hop?

---

## 🔹 Lab 4 – Interceptação HTTPS com Certificado Falso

- **🎯 Objetivo:** Interceptar tráfego HTTPS via proxy com CA falsa.  
- **🛠 Ferramentas:** `mitmproxy`, `burp`, `openssl`  
- **📚 Módulo:** Ataques MitM e HTTPS

### ✅ Tarefas
- [ ] Configurar um proxy HTTPS com CA maliciosa.
- [ ] Importar o certificado no navegador da vítima.
- [ ] Interceptar logins de sites HTTPS.

### ❓ Perguntas
- O que torna possível esse ataque?
- Como a pinagem de certificado impede isso?

---

## 🔹 Lab 5 – Manipulação de Rotas com OSPF

- **🎯 Objetivo:** Configurar OSPF e injetar rotas falsas.  
- **🛠 Ferramentas:** `quagga`, `FRRouting`, `GNS3` ou `EVE-NG`  
- **📚 Módulo:** Roteamento e manipulação de tráfego

### ✅ Tarefas
- [ ] Simular uma rede com roteadores OSPF.
- [ ] Injetar rotas maliciosas para redirecionamento.

### ❓ Perguntas
- Como proteger OSPF contra esse tipo de manipulação?
- Que tipo de autenticação OSPF suporta?

---

## 🔹 Lab 6 – DNS Spoofing + Fake Webserver

- **🎯 Objetivo:** Redirecionar vítimas a servidores falsos via DNS spoofing.  
- **🛠 Ferramentas:** `dnsspoof`, `dnsmasq`, `python3 -m http.server`  
- **📚 Módulo:** DNS e engenharia social

### ✅ Tarefas
- [ ] Capturar requisições DNS e responder com IPs falsos.
- [ ] Servir páginas falsas para capturar credenciais.

### ❓ Perguntas
- Qual o impacto se um DNS malicioso for confiável para o cliente?
- Como o DNSSEC poderia ajudar aqui?

---

## 🔹 Lab 7 – Captura de Tráfego em Rede Wi-Fi com WPA2

- **🎯 Objetivo:** Capturar o handshake WPA2 e quebrar a senha.  
- **🛠 Ferramentas:** `airmon-ng`, `airodump-ng`, `aircrack-ng`  
- **📚 Módulo:** Segurança em redes sem fio

### ✅ Tarefas
- [ ] Colocar interface de rede em modo monitor.
- [ ] Capturar handshake WPA2.
- [ ] Tentar quebrar senha com uma wordlist.

### ❓ Perguntas
- Por que o handshake é necessário para o ataque WPA2?
- Como se proteger de ataques de dicionário?

---

## 🔹 Lab 8 – DoS com Exploração TCP

- **🎯 Objetivo:** Criar ataque DoS com manipulação de conexões TCP.  
- **🛠 Ferramentas:** `hping3`, `scapy`, `iptables`  
- **📚 Módulo:** Mitigação de negação de serviço

### ✅ Tarefas
- [ ] Criar um servidor TCP simples.
- [ ] Lançar ataque SYN flood ou FIN flood.
- [ ] Monitorar impacto em recursos.

### ❓ Perguntas
- Qual a diferença entre um ataque SYN flood e UDP flood?
- Como mitigar ataques DoS com iptables ou fail2ban?

---

## 🔹 Lab 9 – VPN Site-to-Site com OpenVPN + Sniffing

- **🎯 Objetivo:** Configurar VPN e interceptar tráfego fora do túnel.  
- **🛠 Ferramentas:** `openvpn`, `tcpdump`, `iptables`  
- **📚 Módulo:** Criptografia de ponta-a-ponta

### ✅ Tarefas
- [ ] Criar VPN entre duas redes.
- [ ] Capturar tráfego antes e depois do túnel.

### ❓ Perguntas
- Onde o tráfego está criptografado?
- Qual a diferença entre tun e tap?

---

## 🔹 Lab 10 – Simulação de C2 + Exfiltração via DNS ou HTTP

- **🎯 Objetivo:** Criar canal de C2 simulado usando DNS tunneling ou HTTP POST.  
- **🛠 Ferramentas:** `dnscat2`, `http.server`, `tcpdump`  
- **📚 Módulo:** Persistência e canais encobertos

### ✅ Tarefas
- [ ] Configurar máquina atacante para receber dados exfiltrados.
- [ ] Utilizar DNS ou HTTP para exfiltração.

### ❓ Perguntas
- Por que DNS é uma forma útil de exfiltração?
- Como detectar e bloquear C2s em uma rede corporativa?
