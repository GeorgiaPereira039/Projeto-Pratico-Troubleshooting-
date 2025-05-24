# [Projeto Prático de Troubleshooting](https://georgiapereira039.github.io/Projeto-Pratico-Troubleshooting-/)
Projeto de troubleshooting e análise comparativa entre redes domésticas GPON e XPON, com foco em latência, CGNAT, QoS e impacto em aplicações internacionais.

---

## **⚠ Atenção!** 
O objetivo do projeto é apenas investigar a causa raiz usando técnicas de troubleshooting e as soluções aplicadas são provisórias, não devem ser usadas como solução definitiva pois o uso de VPN e DNS podem causar falsa sensação de segurança, privacidade e introduzir novos riscos. 
Para a segurança do usuário o recomendado sempre será entrar em contato direto com o seu provedor. Para mais detalhes consulte as [Considerações finais](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#%EF%B8%8F-considera%C3%A7%C3%B5es-finais).

---
## ⚙️ Etapas do Projeto

- [Objetivo do Projeto](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-objetivo-do-projeto)  
- [Mapeamento das Redes](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-mapeamento-das-redes)  
- [ Introdução ao CGNAT (Carrier-Grade NAT)](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-introdu%C3%A7%C3%A3o-ao-cgnat-carrier-grade-nat)
- [O que é Traffic Shaping?](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-o-que-%C3%A9-traffic-shaping)  
   - [Mecanismos e Algoritmos mais utilizados](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-mecanismos-e-algoritmos-mais-utilizados)
- [Protocolos PPP e PPPoE](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-protocolos-ppp-e-pppoe)
- [Autenticação](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-autentica%C3%A7%C3%A3o)  
   - [Autenticação WPA2/Misto](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-o-que-%C3%A9-a-autentica%C3%A7%C3%A3o-wpa2misto)  
   - [WEP](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-wep-wired-equivalent-privacy)
   - [WPA](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-wpa-wi-fi-protected-access)
   - [WPA2](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#%EF%B8%8F-wpa2-wi-fi-protected-access-2)
   - [WPA3](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#wpa3-wi-fi-protected-access-3)  
- [IEEE 802.11w](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-ieee-80211w---prote%C3%A7%C3%A3o-de-gerenciamento-de-quadros-pmf)  
- [SHA256](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-sha-256---secure-hash-algorithm-256-bits)
- [Conjunto de Cifras de Criptografia WPA2](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-conjunto-de-cifras-de-criptografia-wpa2)
   - [TKIP](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-tkip-temporal-key-integrity-protocol)  
   - [AES-CCMP](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-aes-ccmp-advanced-encryption-standard---ccmp)  
- [QoS](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-qos---quality-of-service)
    - [Modelos de QoS](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#modelos-de-qos) 
    - [QoS em diferentes camadas](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#qos-em-diferentes-camadas)  
- [Conclusão Técnica](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-conclus%C3%A3o-t%C3%A9cnica)
- [Configurações Básicas](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-configura%C3%A7%C3%B5es-b%C3%A1sicas)  
- [Medidas de Mitigação Aplicadas](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#medidas-de-mitiga%C3%A7%C3%A3o-aplicadas)  
- [Conceitos Aplicados e Adquiridos](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#conceitos-aplicados-e-adquiridos)  
- [Ferramentas Utilizadas](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#ferramentas-utilizadas)
- [Conclusão](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#-conclus%C3%A3o-1)
- [Considerações finais](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#%EF%B8%8F-considera%C3%A7%C3%B5es-finais)
- [Sobre](https://github.com/GeorgiaPereira039/Projeto-Pratico-Troubleshooting-/blob/main/README.md#sobre)  

---

## 👩🏻‍💻 Objetivo do Projeto

Este projeto nasceu de uma situação real de instabilidade em conexões com servidores internacionais em jogos e aplicativos (como *Love Nikki*, *Genshin Impact* e *Pokémon TCGP*). A proposta foi diagnosticar a causa comparando redes GPON e XPON, com foco em aplicação prática sobre:

- Latência e perda de pacotes
- CGNAT e Traffic Shaping
- QoS, PPPoE e protocolos de segurança

---
### 🔌 Mapeamento das Redes

Ao lidarmos com erros ou instabilidades na internet, é fundamental **criar um processo** que permita coletar o máximo de informações possíveis sobre o problema. Isso evita perda de foco e economia de tempo com testes desnecessários. Assim o primeiro passo foi analisar o comportamento dos roteadores e o painel da rede.

Segue o comparativo que considerei importante anotar sobre cada rede:

| Categoria | Roteador A | Roteador B |
| --- | --- | --- |
| Tecnologia | GPON ONT | XPON ONU |
| Modelo | Não especificado | Não especificado |
| Autenticação | WPA/WPA2-PSK | WPA2 MISTO |
| Criptografia | AES | AES |
| Firmware | Não especificado | Não especificado |
| IP atribuído | 100.79.x.x | 100.64.x.x |
| Protocolo de autenticação | PPP | PPPoE |
| Servidores DNS | 8.8.8.8 / 177.52.247.217 / 0.0.0.0 | Não especificado |
| QoS (Qualidade de Serviço) | WMM habilitado | Desabilitado |
| Port Forwarding | Desabilitado | Não especificado |
| Modo Bridge | Não especificado | Ativado (Bridge Ethernet - transparent bridging) |
| NAPT | Não especificado | Habilitado |
| Status Power | Acesa | Acesa |
| Status PON | Acesa | Acesa |
| Status LOS | Apagada | Apagada |
| Status Internet | Piscando (1s) | Não especificado |
| Status LAN 1-4 | Apagadas | Apagadas |
| Status Phone | Apagada | Não especificado |
| Status Wi-Fi | Piscando (2s) | Normal - Transmissão em curso |
| Status WPS | Apagada | Não especificado |
| Status USB | Apagada | Não especificado |
| Suporte a 4G | Não | Ativo (LED aceso) |

---

Durante o mapeamento das redes, identifiquei alguns pontos que despertaram minha atenção, em especial na **rede B**, já que era a que apresentava problemas e necessidade de ajustes. A rede A, por outro lado, foi considerado estável, não exigindo alterações.

### 🌐 IP WAN:

De acordo com a RFC 6598, os IPs analisados em ambas as redes estão dentro da faixa `100.64.0.0 - 100.127.255.255`, o que pode indicar o uso de CGNAT ou mesmo Traffic Shaping. Para confirmar, consultei o site [Meu IP](https://meuip.com.br/) e identifiquei que se tratava de um IP dinâmico, diferente do IP WAN atribuído ao roteador.
Isso reforça a hipótese de que essas redes não possuem um IP público exclusivo, indicando o uso de CGNAT pelo provedor de internet.

---

### **📖 Introdução ao CGNAT (Carrier-Grade NAT)?**

Em meados da década de 1980, nasceu o IPv4 com a intenção de dar um endereço a cada dispositivo. Esse protocolo utiliza endereços de 32 bits, o que equivale a 2³², um pouco mais de **4 bilhões de IPs únicos**.

O que ninguém contava era com o avanço e a popularização da rede digital.

Como resultado, em 2011 houve o **esgotamento dos endereços IPv4**. Diante desse problema, surgiu o CGNAT, não como uma solução definitiva, mas como uma forma de contornar a escassez.

---

### 📖 O que é CGNAT?

O **Carrier-Grade NAT** (CGNAT) ou **Large-Scale NAT (LSN)** é uma técnica de **tradução de endereços de rede em larga escala**, e atua **exclusivamente na Camada de Rede (Camada 3)** do **modelo OSI. I**mplementada por provedores de serviços de internet (ISPs) com o objetivo de **mitigar a escassez de endereços IPv4 públicos**.

Com o CGNAT, **múltiplos clientes compartilham um único endereço IPv4 público**. Para isso, o provedor atribui aos clientes **endereços IPv4 privados intermediários**, normalmente dentro da faixa **100.64.0.0/10**, conforme definido na **RFC 6598**.

### **Funcionamento do CGNAT**

1. O cliente recebe um **endereço IP privado intermediário**, distinto dos endereços privados tradicionais (RFC 1918), como `192.168.0.0/16` ou `10.0.0.0/8`.
2. O roteador do cliente realiza a **primeira tradução NAT (Network Address Translation)**, convertendo os endereços da rede local (LAN) para o IP privado intermediário.
3. O provedor realiza a **segunda tradução NAT**, convertendo o IP privado intermediário em um **IP público compartilhado**.
4. Todo o tráfego de múltiplos clientes passa a sair para a internet utilizando **o mesmo endereço IP público**, diferenciando as conexões através de **portas de origem** (source ports).

---

**💢 Problemas e Limitações do CGNAT:**

| **Problema** | **Descrição** |
| --- | --- |
| **Dificuldade em conexões P2P** | Protocolos que requerem comunicação direta entre clientes (ex.: torrents, jogos online) são impactados pela impossibilidade de configuração de redirecionamento de portas (port forwarding). |
| **Serviços que dependem de IP público** | Aplicações como servidores web, VPNs, VoIP e sistemas de monitoramento remoto se tornam inviáveis ou extremamente limitadas. |
| **Compartilhamento de IP** | Múltiplos usuários compartilham o mesmo IP público, o que dificulta a **identificação e rastreamento** de atividades específicas, impactando investigações forenses e políticas de segurança. |
| **Complexidade de gerenciamento** | O provedor deve manter controles rigorosos de alocação de portas e conexões ativas, o que aumenta a complexidade e os custos operacionais. |
| **Impossibilidade de abrir portas** | Usuários comuns não podem realizar configurações típicas de NAT, como DMZ ou port forwarding, sem solicitar um IP público dedicado. |

<aside>

### ⚠️ E lembra do esgotamento do IPv4?

Nasceu o **IPv6**, com a intenção de “salvar” a internet. Ainda estamos no processo de adaptação e transição, mas com **endereços de 128 bits** e cerca de **340 undecilhões** de combinações possíveis, é impossível que fiquemos sem IPs, né? 🙂

</aside>

### **Faixas de Endereços Relevantes**

| **Faixa** | **Descrição** |
| --- | --- |
| `100.64.0.0/10` | Faixa reservada para endereços intermediários utilizados exclusivamente por CGNAT. |
| `192.168.0.0/16`, `10.0.0.0/8`, `172.16.0.0/12` | Endereços privados tradicionais definidos na RFC 1918, utilizados em redes locais. |

### **RFCs Importantes**

- **RFC 1918** — Endereços IPv4 privados.
- **RFC 6598** — Designação da faixa `100.64.0.0/10` para CGNAT.
- **RFC 2663** — Terminologia e considerações gerais sobre NAT.

---

🗨 Concluímos que o CGNAT é uma solução **temporária** e **necessária** para lidar com a escassez de endereços IPv4, permitindo que provedores continuem oferecendo serviços sem interrupções. Entretanto, impõe **restrições significativas** ao usuário final e aumenta a complexidade das redes.

A transição para o IPv6 representa a **solução definitiva**, promovendo uma internet mais **abundante e eficiente** no uso de endereços.

---

### 📖 **O que é Traffic Shaping?**

**Traffic Shaping** (Modelagem de Tráfego) é uma técnica de **controle e gerenciamento de tráfego de rede** que regula a quantidade e a taxa de envio de pacotes. Seu principal objetivo é **controlar o fluxo de tráfego**, assegurando que a rede funcione de maneira eficiente, com previsibilidade e qualidade.

Essa técnica consiste em **atrasar, limitar ou reordenar** pacotes de dados para que estes se ajustem a um perfil desejado de tráfego, frequentemente descrito por parâmetros como **largura de banda, atraso e jitter**.

### **Objetivos principais**
Entre os principais objetivos do Traffic Shaping, destacam-se:

1. **Garantir Qualidade de Serviço (QoS):** assegurar que aplicações sensíveis à latência (como VoIP e videoconferência) mantenham qualidade.
2. **Evitar congestionamento:** impedindo que fluxos específicos sobrecarreguem a rede.
3. **Cumprimento de políticas:** impor limites de uso conforme contratos de SLA (Service Level Agreement).
4. **Previsibilidade:** manter a rede operando conforme parâmetros definidos.

---

### **Funcionamento**

O traffic shaping atua na camada de rede ou enlace, sendo implementado através de mecanismos que:

- **Atrasam pacotes** que excedem um limite pré-definido de taxa de transmissão.
- **Regulam rajadas de tráfego**, convertendo fluxos irregulares em fluxos mais uniformes.
- **Classificam e priorizam pacotes** conforme regras de políticas de tráfego.

Pacotes podem ser **enfileirados** (buffering) até que possam ser transmitidos segundo a taxa permitida. Esse processo introduz **atraso controlado** e pode suavizar flutuações indesejadas no tráfego.

---

### **Mecanismos e Algoritmos mais utilizados**

### **Token Bucket**

- **Conceito:** Um “balde” virtual armazena tokens que representam permissão para transmitir pacotes.
- **Funcionamento:**
    - Tokens são gerados a uma taxa constante.
    - Para transmitir um pacote, um token deve ser consumido.
    - Se não houver tokens suficientes, o pacote é armazenado até que tokens estejam disponíveis.
- **Propriedade:** permite a existência de rajadas de tráfego, respeitando limites médios.

---

### **Leaky Bucket**

- **Conceito:** Modela o tráfego como um balde com um pequeno furo.
- **Funcionamento:**
    - Os pacotes são inseridos no balde.
    - O vazamento ocorre a uma taxa constante, regulando a saída.
- **Propriedade:** suaviza picos e garante uma taxa de transmissão constante.

---

### **Weighted Fair Queuing (WFQ)**

- Algoritmo de agendamento que **atribui pesos** diferentes a fluxos distintos.
- Garante que fluxos mais importantes recebam **mais recursos**, mantendo a equidade relativa.

---

### **Aplicações típicas**

- **Provedores de serviços de Internet (ISPs):** limitar a largura de banda contratada pelos clientes.
- **Backbones de rede:** assegurar estabilidade e evitar congestionamentos em links críticos.
- **Empresas:** garantir que serviços críticos operem com prioridade e que atividades não essenciais não degradem a rede.
- **Infraestruturas em nuvem:** otimizar recursos compartilhados entre múltiplos clientes.
- **Ambientes acadêmicos e data centers:** balancear tráfego e assegurar disponibilidade.

---

### ✅ **Benefícios**

- **Melhoria da eficiência** do uso da largura de banda.
- **Prevenção de congestionamentos**.
- **Priorização de tráfego crítico**.
- **Cumprimento de SLAs**.

---

### 💢 **Desvantagens**

- **Introdução de latência** adicional devido ao enfileiramento.
- **Complexidade** na configuração e manutenção das políticas.
- Possibilidade de **subutilização da banda** se mal configurado.
- Pode ser percebido negativamente quando usado como ferramenta de **throttling**.

---

### **Protocolos e padrões associados**

- **DiffServ (Differentiated Services):** arquitetura para marcar pacotes IP com diferentes níveis de prioridade.
- **MPLS (Multiprotocol Label Switching):** pode ser utilizado com traffic shaping para otimizar o encaminhamento de pacotes conforme políticas de tráfego.
- **IEEE 802.1Q/p:** padrões de VLAN e prioridade de tráfego em redes Ethernet.

---

### 🗨 **Conclusão**

O Traffic Shaping configura-se como uma técnica essencial para o gerenciamento eficiente de redes modernas, permitindo a otimização da largura de banda, a garantia de qualidade para aplicações críticas e a prevenção de congestionamentos. Sua aplicação adequada melhora a eficiência e previsibilidade do tráfego, enquanto uma configuração inadequada pode resultar em degradação de desempenho e insatisfação do usuário.
Analisando o cenário prático, observa-se que o problema mais plausível é o uso de CGNAT, evidenciado pela presença do IP na faixa 100.x.x.x, típica desse tipo de NAT.

Durante a análise, também foi identificada a presença dos protocolos PPPoE e PPP, indicando a utilização de métodos de autenticação e encapsulamento típicos em conexões de banda larga.

---
### 📖 Protocolos PPP e PPPoE

### **PPP (Point-to-Point Protocol)**

O **PPP** é um **protocolo de enlace** de dados (Camada 2 - Modelo OSI) usado para estabelecer **conexões diretas** entre dois nós de rede. Ele foi projetado para transportar diversos protocolos de rede, como IP, IPX ou AppleTalk, sobre links físicos como:

- Linhas telefônicas (modem)
- Links seriais
- Conexões ponto-a-ponto

### **Características técnicas do PPP**

- **Encapsulamento:** Define um quadro próprio com:
    - **Flag** de início/fim
    - **Endereço**
    - **Controle**
    - **Protocolo** (identifica o protocolo encapsulado, ex: IPv4, IPv6)
    - **Campo de informação** (os dados)
    - **FCS** (Frame Check Sequence, para detecção de erros)
- **Autenticação:** Suporta mecanismos como:
    - **PAP (Password Authentication Protocol)**
    - **CHAP (Challenge Handshake Authentication Protocol)**
- **Negociação:** Antes da conexão ser estabelecida, ocorre a negociação de parâmetros com o **LCP (Link Control Protocol)**.
- **Multicamadas:** Depois do LCP, protocolos como o **NCP (Network Control Protocol)** são usados para configurar e habilitar protocolos de rede específicos, como o IP.

---

### **PPPoE (Point-to-Point Protocol over Ethernet)**

O **PPPoE** surgiu para permitir que as operadoras de banda larga (como DSL) usassem o **PPP** sobre a infraestrutura existente de **Ethernet**. Ou seja, ele encapsula quadros PPP dentro de quadros Ethernet.

Assim, combina:

- A **capacidade de autenticação e gerenciamento** do PPP
- Com a **eficiência da Ethernet**, que é baseada em **broadcast** e não precisa ser ponto a ponto

### **Funcionamento do PPPoE:**

1️⃣ **Fase de descoberta (PPPoE Discovery):**

- Cliente envia pacotes **PADI** (PPPoE Active Discovery Initiation) procurando servidores.
- Servidor responde com **PADO** (PPPoE Active Discovery Offer).
- Cliente escolhe um servidor e envia **PADR** (Request).
- Servidor confirma com **PADS** (Session-confirmation).
    
    ➡️ Assim, estabelece-se a **sessão PPPoE**.
    

2️⃣ **Fase de sessão:**

- PPP é encapsulado em quadros Ethernet.
- O cliente se autentica via **PAP ou CHAP**.
- Provedor aloca um **endereço IP dinâmico** via **PPP NCP**.

---

### ✅ **Vantagens do PPPoE:**

- Compatível com sistemas legados baseados em PPP
- Suporte à **autenticação centralizada** (Radius, TACACS+)
- Controle de **tempo de conexão** e **contabilidade**
- Distribuição dinâmica de **endereços IP**

**Vamos seguir para o próximo ponto que chamou minha atenção na Rede B: a autenticação.**

Após a primeira análise e o estudo dos termos citados, decidi investigar a aba **WLAN > Segurança**. A primeira coisa que notei foi o tipo de autenticação configurado como **WPA2/Misto**. Isso me levou a pesquisar mais a fundo sobre o que significa cada modo e como atuam nas diferentes **camadas da rede**.

---
### **📖 Autenticação**

A autenticação de redes Wi-Fi é um dos pontos mais cruciais na segurança de uma rede sem fio. Por padrão, muitas redes domésticas vêm configuradas como **WPA2/Misto**. Foi o caso da Rede B, e contava com 3 modos, WEP, WPA2 e o ****WPA2/Misto**.** Mas… será que essa é realmente a melhor opção? 🤔 Vamos entender o que é isso e por que pode ser um risco

### 🔐 **O que é a Autenticação WPA2/Misto?**

Esse modo permite conexões simultâneas usando tanto **WPA (ou WPA2)** quanto **WPA3** ou até mesmo **WEP**, dependendo do dispositivo que tenta se conectar. Ele é um modo **“híbrido”** ou **“compatível”** com dispositivos antigos.

O objetivo é garantir **compatibilidade** com dispositivos legados (antigos), mas isso sacrifica a segurança, pois permite conexões através de protocolos **mais vulneráveis**.

### 🔓 **WEP (Wired Equivalent Privacy)**

O WEP foi a primeira solução de proteção para redes sem fio, surgida no final dos anos 90. Seu objetivo era proporcionar segurança através da criptografia baseada em chaves compartilhadas. Essas chaves são estáticas, de 64 ou 128 bits em hexadecimal. Assim, qualquer dispositivo que se comunicasse na rede autenticada com WEP teria os dados criptografados de maneira uniforme, dificultando acessos não autorizados.

Porém, com o avanço das técnicas de ataque, o WEP rapidamente se tornou obsoleto e vulnerável.

💢 **Problemas principais:**

- Chave de criptografia curta e fácil de quebrar.
- Vulnerável a ataques de captura de pacotes: é possível descobrir a senha em poucos minutos usando ferramentas como **aircrack-ng**.
- Não implementa proteção eficaz contra repetição de pacotes (replay attacks).
- Não possui verificação robusta de integridade.

> ###📌 Curiosidade:
> Considerado **inseguro e obsoleto** desde 2004, mas ainda é mantido em modo "misto" para compatibilidade com dispositivos muito antigos.

---

### 🔐 **WPA (Wi-Fi Protected Access)**

Em 2003, surge o WPA para substituir o WEP. Ele manteve algumas bases do protocolo anterior, mas trouxe melhorias importantes.

Diferentemente do WEP, o WPA introduziu o **TKIP (Temporal Key Integrity Protocol)** um protocolo que altera dinamicamente as chaves de criptografia, dificultando a interceptação por atacantes.

Além disso, trouxe mecanismos para garantir a integridade dos pacotes transmitidos, evitando que fossem modificados sem detecção.

💢 **Problemas principais:**

- Embora o TKIP fosse uma melhoria, ele ainda utiliza o fraco algoritmo **RC4**, que possui várias vulnerabilidades conhecidas.
- Suscetível a ataques como o **Michael vulnerability** e **replay attacks**.
- Foi uma solução provisória, até a chegada do WPA2.
- Já considerado **obsoleto**.

> ### 📌 Curiosidade:
>
> O termo “chave WPA” normalmente se refere à senha necessária para se conectar à rede.

### 🛡️ **WPA2 (Wi-Fi Protected Access 2)**

Em 2004, foi lançado o WPA2, uma evolução significativa do WPA. Baseado no **RSN (Robust Security Network)**, o WPA2 opera em dois modos:

- **Modo Pessoal (WPA2-PSK):** mais usado em redes domésticas, depende de uma senha compartilhada.
- **Modo Empresarial (WPA2-EAP):** voltado para ambientes corporativos, com autenticação mais robusta (por exemplo, via RADIUS).

A principal melhoria foi a substituição do TKIP pelo **CCMP (Counter Mode with Cipher Block Chaining Message Authentication Code Protocol)**, baseado no **AES (Advanced Encryption Standard)**, que oferece criptografia e verificação de integridade mais fortes.

💢 **Problemas principais:**

- **Dependência de senha forte:** se a senha for fraca, pode ser quebrada com ataques de dicionário ou força bruta.
- **Vulnerável ao ataque KRACK (Key Reinstallation Attack):** descoberto em 2017, esse ataque explora falhas na reinstalação de chaves durante o handshake, permitindo interceptação de dados.

> ### 📌 Curiosidade:
> O ataque **KRACK** afeta todas as redes protegidas por WPA2 e reforçou a necessidade de migração para protocolos mais modernos e seguros.

---

### **👩🏻‍💻 WPA3 (Wi-Fi Protected Access 3)?**

O **WPA3** é a terceira geração do protocolo, lançado em 2018, com foco na segurança frente às vulnerabilidades conhecidas do WPA2.

**Principais melhorias:**

- **SAE (Simultaneous Authentication of Equals):** substitui o handshake do WPA2 por um protocolo mais seguro contra ataques de força bruta e dicionário. Exige que cada tentativa de senha envolva uma troca criptográfica completa, tornando os ataques muito mais difíceis.
- **Criptografia mais forte:** chaves maiores, com criptografia de até **256 bits**, usando suites de segurança robustas.
- **Forward Secrecy:** garante que, mesmo que uma chave de sessão seja comprometida, sessões anteriores permanecerão protegidas.
- **Proteção reforçada para redes públicas:** com **Opportunistic Wireless Encryption (OWE)**, que fornece criptografia automática mesmo em redes abertas, sem necessidade de senha.
- **Modo Easy Connect:** simplifica a conexão de dispositivos IoT, que muitas vezes têm interfaces limitadas, por meio de QR Codes ou NFC.

💢 **Problemas principais:**

- **Compatibilidade:** muitos dispositivos antigos não suportam WPA3, forçando administradores a manterem modos "misto" (WPA2/WPA3), o que pode reintroduzir riscos.
- **Implementações imaturas:** algumas implementações iniciais do WPA3 apresentaram vulnerabilidades como o **Dragonblood**, que explorava falhas na especificação SAE.
- **Adoção lenta:** embora seja o futuro da segurança Wi-Fi, sua adoção ainda está em andamento.

### **Tabela Comparativa: WEP vs WPA vs WPA2 vs WPA3**

| **Protocolo** | **Ano de Lançamento** | **Algoritmo de Criptografia** | **Principais Recursos** | **Vulnerabilidades** | **Situação Atual** |
| --- | --- | --- | --- | --- | --- |
| **WEP** | 1997 | RC4 com chave estática de 64/128 bits | Primeira tentativa de proteger redes Wi-Fi | Extremamente vulnerável a ataques de captura e cracking (Aircrack-ng) | **Obsoleto e inseguro** |
| **WPA** | 2003 | TKIP sobre RC4 (chave dinâmica) | Introdução de chave dinâmica, proteção contra alteração de pacotes | Michael vulnerability, replay attacks, fraqueza do RC4 | **Obsoleto, mas ainda presente em dispositivos antigos** |
| **WPA2** | 2004 | AES com CCMP | Forte criptografia, autenticação de integridade, modos PSK e EAP | KRACK Attack, força da segurança depende de senha forte | **Ainda amplamente usado, mas com recomendações de migração para WPA3** |
| **WPA3** | 2018 | SAE (Simultaneous Authentication of Equals), AES-256 | Proteção contra ataques de dicionário offline, Forward Secrecy, melhorias no handshake | Problemas iniciais de implementação, falhas como Dragonblood | **Padrão atual recomendado** |

🗨 Agora que entendemos os tipos mais comuns de autenticação, sabemos que a melhor opção **atualmente** é habilitar o **WPA2** ou, preferencialmente, o **WPA3**.

Entretanto, além disso, existem **três opções adicionais** de configuração que podem ser habilitadas:

1. **IEEE 802.11w** — proteção para o gerenciamento de quadros, evitando ataques de desautenticação.
2. **SHA256** — usado em algumas configurações para autenticação mais segura, por exemplo, no WPA2-Enterprise.
3. **Conjunto de cifras WPA2** — seleção dos algoritmos criptográficos utilizados, geralmente recomendando o uso de **AES** ao invés de **TKIP**.

---

### 📖 **IEEE 802.11w - Proteção de Gerenciamento de Quadros (PMF)**

O **IEEE 802.11w** é uma **emenda ao padrão IEEE 802.11**, publicada em **2009**, que introduz a **proteção de quadros de gerenciamento** em redes Wi-Fi.

Enquanto os protocolos de segurança anteriores (como WPA/WPA2) focavam na proteção de **dados transmitidos**, o 802.11w tem como objetivo **proteger os quadros de gerenciamento**, prevenindo ataques que exploram a ausência de autenticação e criptografia nesses quadros.

---

### **Contexto: quadros de gerenciamento em redes Wi-Fi**

O padrão IEEE 802.11 define três tipos principais de quadros:

1️⃣ **Quadros de gerenciamento:** responsáveis por estabelecer e manter conexões. Exemplos:

- Beacon
- Probe Request/Response
- Authentication
- Association/Disassociation
- Deauthentication

2️⃣ **Quadros de controle:** coordenam o acesso ao meio. Ex.: ACK, RTS/CTS.

3️⃣ **Quadros de dados:** transportam os dados propriamente ditos.

---

🗨 Antes do 802.11w, apenas os **quadros de dados** eram protegidos via criptografia (WEP, WPA, WPA2).
Os **quadros de gerenciamento eram transmitidos em texto claro**, vulneráveis a diversos ataques.

---

### **Problemas antes do 802.11w:**

- **Ataques de desautenticação e desassociação:**

Atacantes podiam enviar **quadros falsos de "deauth" ou "disassoc"**, forçando clientes a se desconectar da rede Wi-Fi (Denial of Service - DoS).

- **Evil Twin e Man-in-the-Middle:**

Facilitava a criação de pontos de acesso maliciosos, enganando clientes para capturar tráfego.

---

### **O que o IEEE 802.11w muda?**

A emenda introduziu o conceito de **PMF — Protected Management Frames** (ou **Proteção de Quadros de Gerenciamento**), exigindo que determinados quadros sejam **autenticados e, opcionalmente, criptografados**.

---

### ⚙️ **Principais quadros protegidos:**

- Disassociation
- Deauthentication
- Robust Action Frames (quadros de ação robustos)
- Quality of Service (QoS)
- Transição do Conjunto de Serviços Básicos (BSS)
- Medição de rádio

Esses quadros passam a ser autenticados com base nas chaves derivadas do protocolo de segurança (ex.: WPA2-PSK ou WPA2-Enterprise).

---

### **Como funciona a proteção?**

1️⃣ Durante a negociação da segurança da conexão (4-Way Handshake), o Access Point (AP) e o cliente determinam se **PMF** será:

- **Optional:** pode ser usado, mas não é obrigatório.
- **Required:** obrigatoriamente utilizado, clientes sem suporte não conseguem se conectar.

2️⃣ A partir desse momento, os quadros de gerenciamento críticos são **criptograficamente protegidos**.

3️⃣ Quadros protegidos são marcados com o bit **"Protected"** no campo **Frame Control**.

---

### 🗨  **Integração com WPA2 e WPA3**

- O **IEEE 802.11w** é **obrigatório** no **WPA3**.
- No **WPA2**, a proteção de PMF é **opcional**, mas fortemente recomendada.
- Desde 2020, a certificação Wi-Fi Alliance exige PMF (802.11w) como obrigatório em novos dispositivos.

A implementação completa do 802.11w é chamada de **Robust Security Network Associations (RSNA)**.

---

### ✅ **Benefícios técnicos do IEEE 802.11w:**

✔ Previne **ataques de desautenticação e desassociação**.

✔ Mitiga **DoS attacks** via quadros de gerenciamento forjados.

✔ Aumenta a **confiança** na integridade da conexão Wi-Fi.

✔ Reforça a segurança em ambientes **corporativos** e **públicos**.

---

### 💢 **Limitações:**

⚠️ Nem todos os dispositivos antigos suportam PMF, causando possíveis **incompatibilidades**.

⚠️ Apenas protege quadros de gerenciamento específicos, **não protege quadros de beacon**.

⚠️ Não impede todos os tipos de ataques contra redes Wi-Fi, mas **eleva significativamente o nível de segurança**.

---

🗨  Concluindo o **IEEE 802.11w** representa uma evolução fundamental na segurança das redes Wi-Fi, corrigindo uma vulnerabilidade crítica que, por muitos anos, permitiu ataques triviais e de baixo custo.

Na rede analisada em questão os modos para **IEEE 802.11w** são:

**Modos:**

- `Nenhum`: proteção desligada.
- `Capaz`: dispositivos que suportam usam, os que não suportam ainda conseguem conectar.
- `Obrigatório`: só conecta se o dispositivo suportar 802.11w.

---

### 📖 **SHA-256 - Secure Hash Algorithm 256 bits**

**SHA-256** (Secure Hash Algorithm 256 bits) é uma **função hash criptográfica** desenvolvida pela **NSA (National Security Agency)** e publicada pelo **NIST (National Institute of Standards and Technology)** como parte da família **SHA-2**.

Seu principal objetivo é gerar um **resumo fixo de 256 bits (32 bytes)** a partir de uma entrada de tamanho arbitrário, garantindo integridade e resistência a diversas formas de ataques.

---

### **Estrutura e características principais**

| **Aspecto** | **Descrição** |
| --- | --- |
| **Nome** | SHA-256 |
| **Família** | SHA-2 |
| **Comprimento do hash** | 256 bits (32 bytes) |
| **Tamanho do bloco** | 512 bits |
| **Estrutura** | Função de compressão baseada em Merkle-Damgård |
| **Função de compressão** | Baseada no design de Davies-Meyer |
| **Ano de publicação** | 2001 (SHA-2 oficializado pelo NIST) |

---

### **Como o SHA-256 funciona?**

### **Passos principais:**

1️⃣ **Pré-processamento**

- **Padding (Preenchimento):** adiciona bits para que o comprimento total seja múltiplo de 512 bits.
- **Anexação do comprimento:** adiciona o comprimento original da mensagem (antes do padding), codificado em 64 bits.

2️⃣ **Inicialização:**

- Define **8 valores hash iniciais** (H0 a H7), específicos do SHA-256.

3️⃣ **Processamento:**

- Divide a mensagem em blocos de **512 bits**.
- Para cada bloco, executa **64 rodadas** de operações, usando:
    - **Funções lógicas:** AND, OR, XOR, NOT.
    - **Operações aritméticas:** adição modular (mod 2³²).
    - **Operações de rotação e deslocamento.**

4️⃣ **Atualização:**

- Após cada bloco, os valores de hash são atualizados com base nas operações realizadas.

5️⃣ **Resultado:**

- A concatenação final dos 8 valores de 32 bits resulta no **digest de 256 bits**.

---

### **Propriedades de segurança**

✔️ **Determinística:** mesma entrada, mesmo hash.

✔️ **Resistente à colisão:** computacionalmente inviável encontrar duas entradas diferentes com o mesmo hash.

✔️ **Resistente à pré-imagem:** difícil encontrar uma entrada que gere um hash específico.

✔️ **Resistente à segunda pré-imagem:** difícil encontrar uma segunda entrada com o mesmo hash de uma entrada conhecida.

✔️ **Avalanche effect:** pequenas mudanças na entrada causam grandes mudanças no hash.

---

### **Aplicações comuns do SHA-256**

- **Integridade de dados:** verificação se os dados foram alterados.

- **Armazenamento de senhas:** hashes salvos em vez de senhas em texto claro.

- **Certificados digitais:** assinaturas e validação de identidade.

- **Criptomoedas:** Bitcoin, por exemplo, usa SHA-256 no processo de mineração e validação de blocos.

- **Protocolos de segurança:** TLS, SSH, IPsec

---

### ✅ **Vantagens**

✔️ **Alta segurança**, resistente a ataques conhecidos.

✔️ **Amplamente padronizado**, interoperável e bem testado.

✔️ **Suporte robusto** em bibliotecas e hardware modernos.

---

### 💢 **Desvantagens**

❌ **Mais lento** do que funções hash mais antigas (MD5, SHA-1).

❌ Não é otimizado para todas as aplicações (ex.: autenticação rápida de senhas pode usar funções mais especializadas, como bcrypt ou Argon2).

---

### **🗨 Status atual**

O SHA-256 continua sendo um dos algoritmos mais recomendados para integridade e segurança de dados.
Embora existam alternativas mais rápidas ou modernas, o SHA-256 mantém-se como um padrão seguro e confiável, fundamental na infraestrutura de segurança cibernética global.

Na rede analisada, a opção conta com dois modos:

- Habilitar
- Desabilitar

Por segurança, sabemos qual deverá ser mantido ativado.

---

### 📖 Conjunto de cifras de criptografia WPA2.

Mantendo o foco na rede B, vamos comentar rapidamente sobre as cifras de criptografia que aparecem no painel do roteador: TKIP e AES.

No contexto do **WPA2**, duas cifras principais aparecem:

- **TKIP (Temporal Key Integrity Protocol)**
- **AES-CCMP (Advanced Encryption Standard - Counter Mode with Cipher Block Chaining Message Authentication Code Protocol)**

Esses algoritmos são utilizados para **criptografia de dados**, garantindo a **confidencialidade** e **integridade** das informações transmitidas na rede Wi-Fi.

## **TKIP (Temporal Key Integrity Protocol)**

### **💻 Resumo:**

- Criado como uma solução **transitória** para substituir o WEP, considerado fraco e vulnerável..
- Introduzido com o **WPA** original.
- Suportado pelo WPA2 por questões de **retrocompatibilidade**, mas **não recomendado**.

### ⚙️ **Funcionamento técnico:**

| **Elemento** | **Descrição** |
| --- | --- |
| **Chave Base** | A **Pairwise Temporal Key (PTK)**, gerada no handshake, baseia-se na PMK. |
| **Per-Packet Key Mixing** | Cada pacote usa uma **chave única** derivada da PTK + IV (Initialization Vector). |
| **RC4** | TKIP continua usando o fluxo de cifras **RC4**, a mesma usada no WEP, mas com melhorias no gerenciamento de chave. |
| **MIC (Michael)** | Um código de integridade adicionado para proteger contra **ataques de injeção**. |

---

### 💢 **Vulnerabilidades:**

- **RC4** já é considerado **inseguro**.
- O **MIC (Michael)** é considerado fraco e pode ser contornado por atacantes.
- Não protege contra ataques mais modernos, como **replay attacks** sofisticados.

**Por isso TKIP está obsoleto e não recomendado!**

---

### **AES-CCMP (Advanced Encryption Standard - CCMP)**

### **💻 Resumo:**

- Introduzido com o **WPA2** como substituto robusto do TKIP.
- Baseado no algoritmo de bloco **AES**.
- CCMP: **Counter Mode with CBC-MAC Protocol**, combina **criptografia** e **integridade**.

### ⚙️ **Funcionamento técnico:**

| **Elemento** | **Descrição** |
| --- | --- |
| **Chave Base** | A **PTK**, gerada durante o handshake. |
| **Counter Mode** | Utilizado para criptografar os dados, semelhante ao CTR (Counter Mode). |
| **CBC-MAC** | Função de integridade: protege contra **modificações nos pacotes**. |
| **Tamanho de Chave** | **128 bits** para a chave AES (WPA2). |
| **Nonce (Número único)** | Para evitar **reutilização de chaves** e **replay attacks**. |

### ✅ **Vantagens:**

✔️ Segurança moderna, baseada no robusto algoritmo em AES.

✔️ Protege contra vários tipos de ataque, incluindo **replay** e **injection**.

✔️ Considerado **padrão obrigatório** no WPA2.

---

### **Comparativo entre TKIP e AES-CCMP**

| **Característica** | **TKIP** | **AES-CCMP** |
| --- | --- | --- |
| **Introdução** | WPA (2003) | WPA2 (2004) |
| **Algoritmo** | RC4 (fluxo) | AES (bloco) |
| **Integridade** | MIC (Michael) | CBC-MAC integrado |
| **Segurança** | Obsoleto e inseguro | Seguro e recomendado |
| **Eficiência** | Baixa, devido à complexidade de key-mixing e ao uso de RC4 | Alta, eficiente em hardware moderno |
| **Requisitos** | Compatível com hardware legado | Requer hardware compatível com AES |

🗨  Concluímos então que a recomendação é:

✔️ **Desativar TKIP** sempre que possível.

✔️ Usar apenas WPA2 com AES-CCMP ou WPA3 (que substitui CCMP por GCMP).

✔️ Evite opções como "**TKIP + AES**", pois podem permitir ataques **downgrade attacks**, forçando a rede a usar TKIP.

---

### 📖 **QoS - Quality of Service**

**QoS (Quality of Service)** significa 'Qualidade de Serviço', um conjunto de técnicas e mecanismos usados em redes para garantir **desempenho**, **prioridade** e **disponibilidade** adequados para determinados fluxos de dados."

Objetivo: **Assegurar que aplicações críticas recebam o nível de serviço necessário**, mesmo em ambientes de congestionamento ou limitações de banda.

---

## **Por que o QoS é importante?**

🎮 **Jogos online**, 📞 **VoIP**, 🎥 **vídeos em tempo real**.

Essas aplicações precisam de **baixa latência**, **pouca perda de pacotes** e **alta disponibilidade**.

Sem QoS, todas as aplicações competem igualmente por recursos, o que pode causar:

❌ Atrasos (latência alta)

❌ Perda de pacotes

❌ Jitter elevado (variação do atraso)

**Exemplo clássico:**

✔ Uma chamada de vídeo precisa de prioridade maior que o download de um arquivo!

---

## **Como funciona o QoS?**

O QoS atua **classificando**, **priorizando** e, se necessário, **limitando** tráfego em uma rede, com base em políticas definidas.

### **Etapas principais:**

| **Etapa** | **Descrição** |
| --- | --- |
| **Classificação** | Identifica e separa os pacotes com base em critérios: endereço IP, porta, protocolo, etc. |
| **Marcação** | Adiciona tags aos pacotes para indicar prioridade, como **DSCP**, **CoS** ou **ToS**. |
| **Fila (Queuing)** | Define como os pacotes serão enfileirados e qual será transmitido primeiro. |
| **Policiamento** | Garante que o tráfego não exceda a banda alocada, descartando excessos se necessário. |
| **Modelagem** | Ajusta a velocidade ou ritmo da transmissão para manter o tráfego dentro dos limites aceitáveis. |

## **Protocolos e Padrões relacionados ao QoS**

| **Protocolo / Padrão** | **Função** |
| --- | --- |
| **DiffServ (DSCP)** | Marca pacotes com diferentes classes de serviço (**6 bits no cabeçalho IP**). |
| **IntServ (RSVP)** | Garante reserva de banda, mas é complexo e pouco usado atualmente. |
| **802.1p** | Marcação de prioridade em redes Ethernet, via **VLAN Tagging (802.1Q)**. |
| **MPLS** | Engenharia de tráfego e QoS em redes **WAN** e **provedores**. |
| **ToS (Type of Service)** | Campo antigo no cabeçalho IPv4 para indicar prioridade; Precursor do **DSCP**. |

---

## **Parâmetros principais de QoS**

| **Parâmetro** | **Descrição** |
| --- | --- |
| **Largura de Banda** | Capacidade máxima de transmissão da rede. |
| **Latência** | Tempo que um pacote leva para ir de origem ao destino. |
| **Jitter** | Variação na latência entre pacotes consecutivos. |
| **Perda de Pacotes** | Percentual de pacotes que são descartados ou perdidos. |
| **Disponibilidade** | Tempo em que o serviço está funcional e estável. |

---

## **Técnicas comuns de QoS**

| **Técnica** | **Descrição** |
| --- | --- |
| **Prioritização** | Dá maior prioridade a tráfego crítico, como voz e vídeo. |
| **Shaping** | Controla a taxa de envio, evitando picos de tráfego. |
| **Policing** | Limita o tráfego e descarta excessos, conforme política. |
| **Scheduling (Agendamento)** | Define a ordem de envio dos pacotes. Exemplos: FIFO, WFQ. |
| **RED (Random Early Detection)** | Técnica de prevenção de congestionamento, descartando pacotes antes que a fila encha. |

---

## **Modelos de QoS**

### 🔸 **Best Effort**

- Sem QoS. Todos os pacotes são tratados igualmente.

- Simples, mas pode gerar congestionamento.

---

### 🔸 **Integrated Services (IntServ)**

- QoS **baseada em reserva explícita**.

- Usa RSVP para reservar recursos fim a fim.

- Escalabilidade limitada em grandes redes.

---

### 🔸 **Differentiated Services (DiffServ)**

- QoS **baseada em classes**.

- Pacotes são marcados com **DSCP**.

- Mais escalável que IntServ.

- Amplamente usado em redes **corporativas** e **provedores**.

---

## **Aplicações que dependem de QoS**

✔️ **VoIP (voz sobre IP)**

✔️ **Vídeo Conferência**

✔️ **Streaming de vídeo**

✔️ **Jogos online**

✔️ **Serviços críticos de missão** (financeiros, médicos, etc.)

---

## **QoS em diferentes camadas**

| **Camada** | **QoS aplicado?** |
| --- | --- |
| **Camada 1 (Física)** | Não, mas pode afetar (ex.: interferência). |
| **Camada 2 (Enlace)** | Sim, via **802.1p** e **CoS**. |
| **Camada 3 (Rede)** | Sim, via **DSCP** e **ToS**. |
| **Camada 4 (Transporte)** | Indiretamente, dependendo do protocolo (ex.: TCP implementa controle de congestionamento, que pode afetar a QoS.). |
| **Camada 7 (Aplicação)** | Pode definir prioridades (ex.: SIP em VoIP). |

---

## **Benefícios e Desafios do QoS**

### ✅ **Benefícios:**

✔️ Melhora a experiência do usuário.

✔️ Garante desempenho em aplicações críticas.

✔️ Evita sobrecarga em momentos de pico.

---

### 💢 **Desafios:**

❌ Configuração complexa.

❌ Difícil de manter políticas consistentes em ambientes heterogêneos.

❌ Necessidade de equipamentos compatíveis.

---

## **Futuro do QoS**

- Integração com **SDN (Software Defined Networking)**.

- Tendência de maior uso de **IA** e **automação** para ajustes dinâmicos de políticas de QoS.

- Adaptação para **5G** e **IoT**, que exigem QoS ainda mais sofisticado!

---
## ✍🏻 Conclusão Técnica

Após mapeamento e coleta detalhada de dados sobre as duas redes envolvidas, foi possível identificar pontos de melhoria e executar testes para diagnosticar o real problema relacionado à conectividade e desempenho.

Este relatório descreve as ações realizadas, os resultados obtidos e as medidas recomendadas.

---

### **Topologia da Rede**

Durante o mapeamento, foi confirmada uma topologia P2P (ponto-a-ponto) no formato estrela, sendo um equipamento principal (provedor) e ramificações para os equipamentos locais (redes A e B).
Essa topologia foi determinante para compreender a distribuição de sinal e as diferenças de desempenho entre as redes analisadas.

---

##  **💻 Configurações Básicas**

### **Rede A**

- Detecção de CGNAT: Confirmada.

- Scan de portas: A varredura ativa da rede A não foi realizada devido à presença de mecanismos restritivos, como a ausência de Port Forwarding e a configuração de CGNAT, que impedem conexões externas diretas ao roteador. Embora seja possível realizar varreduras passivas ou utilizar técnicas alternativas, optei por não prosseguir, visto que a rede apresentava estabilidade, sem evidências de falhas relacionadas ao escopo deste diagnóstico. Assim, a priorização foi direcionada à rede B, que apresentava maior instabilidade e impacto na experiência do usuário.

➡️ Esta rede foi mantida conforme encontrada, sem alterações.

---

### **Rede B**

- Segurança Wi-Fi: WPA2 ativado, com autenticação SHA-256.

- Criptografia: Ajustada para garantir uso exclusivo de WPA2 com AES.

- Protocolo: IEEE 802.11w ativado em modo “capaz”.

- QoS: Habilitado para priorização de pacotes.

- Frequências: 2.4 GHz e 5 GHz separadas e testadas individualmente.

- Detecção de CGNAT: Confirmada.

- Scan de portas: Uso do Nmap, para escaneamento de portas e identificação de serviços vulneráveis ou expostos.

⚠ Foi detectada a porta 8291 aberta na rede B, associada ao serviço Winbox do Mikrotik. Embora não tenha sido possível obter acesso administrativo, recomenda-se contato com o provedor para avaliar a necessidade de manter esta porta aberta ou proceder com o bloqueio.

---

### 3. Testes de Conectividade e Latência

| Rede | Banda | Down / Up | Latência (Down / Up / Idle) | Perda | App | Funcionou? | Carregamento | Resultado |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| A (ONT) | 2.4G | 27.6 / 19.6 Mbps | 203ms / 86ms / 57ms | 1.3% | Love Nikki | ✅ | 25s | Rápido |
| A (ONT) | 5G | 283 / 268 Mbps | 29ms / 18ms / 16ms | 5.8% | Love Nikki | ✅ | 25s | Ótimo |
| B (ONU) | 2.4G | 38.3 / 36.3 Mbps | 405ms / 537ms / 9ms | 1% | Love Nikki | ❌ | 80s | Lento |
| B (ONU) | 5G | 286 / 288 Mbps | 22ms / 25ms / 10ms | 0% | Love Nikki | ❌ | 70s | Lento |

⚠️ Mesmo com boa velocidade na rede B, observou-se latência elevada e carregamento de aplicativos lento, sugerindo impacto de CGNAT ou possíveis práticas de Traffic Shaping pela operadora.

---

## **Medidas de Mitigação Aplicadas**

### **VPN (ProtonVPN)**

- Melhora significativa do tempo de resposta.

- Carregamento de aplicativos caiu de 80s para ~25s.

- Navegação e uso de apps normalizados.

### **Alteração de DNS Público**

- Configurado Quad9: 9.9.9.9 e 149.112.112.112.

- Redução da latência e melhora na resposta.

- Indica possível problema de roteamento na operadora.

---

## **Conceitos Aplicados e Adquiridos**

| **Conceito** | **Significado** |
| --- | --- |
| **CGNAT** | Método de compartilhamento de IPs que dificulta conexões P2P |
| **Traffic Shaping** | Prática de limitar ou priorizar certos tipos de tráfego |
| **QoS** | Quality of Service: prioriza pacotes essenciais (como jogos e chamadas) |
| **IEEE 802.11w** | Proteção contra *Deauth Attacks* |
| **WPA2 + AES** | Padrão de criptografia seguro para redes Wi-Fi |
| **PPPoE** | Protocolo de autenticação individual via rede |
| **DNS Público** | Alternativa que melhora a resposta e evita rotas ineficientes da operadora |
| **VPN** | Criou um túnel criptografado, driblando CGNAT e rotas subótimas. |
| **Nmap** |  Identificou portas abertas/fechadas e ajudou na análise de acessibilidade através do CGNAT.  |
| **Traceroute** | Análise do roteamento → identificou saltos internacionais e latência elevada, reforçando impacto do CGNAT. |
| **Modelo OSI** | Auxiliou na análise das camadas impactadas pelo CGNAT e pelo uso de VPN. |

---

## **📊 Ferramentas Utilizadas**

- **PingTools**
- **ProtonVPN**
- **Nmap**
- **ChatGPT**
- **Livro:** TCP/IP em 24 Horas
- **Sites de referência:**
    - [Meu IP](https://meuip.com.br/)
    - [**SpeedTest**](http://speedtest.net/)
    - [Configurar a proteção de quadros de gerenciamento 802.11w no WLC](https://www.cisco.com/c/pt_br/support/docs/wireless-mobility/wireless-lan-wlan/212576-configure-802-11w-management-frame-prote.html)
    - [O que é Traffic Shaping?](https://tecnoblog.net/responde/o-que-e-traffic-shaping/)
    - [WEP vs WPA](https://www.kaspersky.com.br/resource-center/definitions/wep-vs-wpa)
    - [O que é Qualidade de Serviço (QoS) em Redes?](https://www.fortinet.com/resources/cyberglossary/qos-quality-of-service#:~:text=Quality%20of%20service%20(QoS)%20is,prioritizing%20specific%20high%2Dperformance%20applications.)

---

## ✅ **Conclusão**

O problema estava relacionado ao CGNAT e ao roteamento ineficiente da operadora, que comprometia a sincronização com servidores estrangeiros de jogos. A solução imediata foi o uso de VPN, que otimizou a rota e restaurou a estabilidade.

Apesar do **QoS habilitado na rede B**, não foi suficiente para compensar o impacto do CGNAT e do roteamento subótimo.

Este projeto demonstrou que, mesmo com recursos domésticos e conhecimento técnico, é possível identificar gargalos e aplicar correções, minimizando a dependência da operadora.

**Diagnóstico**:

- Presença de CGNAT em ambas as redes.
- Impacto de práticas de Traffic Shaping.
- QoS habilitado, mas insuficiente frente às condições de roteamento.

**Soluções aplicadas**:

- VPN → melhora significativa.
- Alteração para DNS público → redução de latência.
- Solicitação formal de remoção do CGNAT junto à operadora.
- Reconfiguração do roteador realizada.

---

## ⚠️ **Considerações Finais**

Este projeto demonstrou como técnicas de troubleshooting podem ser aplicadas para diagnosticar problemas complexos de conectividade, mesmo em ambientes com CGNAT e rotas ineficientes. Entretanto, é fundamental destacar que as soluções aplicadas como o uso de VPNs e DNS públicos  são **paliativas** e não eliminam a necessidade de uma ação estrutural junto à operadora.

Embora a VPN possa contornar rotas ruins e CGNAT temporariamente, ela **não substitui** uma infraestrutura de rede bem configurada e pode introduzir novos riscos, como:

- **Falsa sensação de segurança:** Nem todas as VPNs garantem privacidade efetiva; muitas armazenam logs ou são vulneráveis.
- **Perda de desempenho:** O tráfego criptografado pode causar lentidão ou bloqueios adicionais.
- **Novos vetores de ataque:** Alterar DNS ou usar VPN pode expor o usuário a servidores maliciosos ou vulnerabilidades específicas.

Assim, a **recomendação final** sempre será:

**procurar suporte técnico especializado ou o provedor de internet** para verificar a possibilidade de ajustes definitivos, como:

- Atribuição de um IP público fixo.
- Reconfiguração de roteadores.
- Implementação de políticas adequadas de QoS.

Este projeto buscou não apenas resolver o problema emergencial, mas também servir como um exemplo de investigação estruturada e consciente, respeitando os limites técnicos e éticos da atuação.

Recomenda-se:  

- **Adotar o IPv6** sempre que possível, evitando as limitações do CGNAT.  
- Manter o conhecimento técnico **sempre atualizado**, principalmente em relação a segurança em redes Wi-Fi.  
- Realizar **testes constantes** na infraestrutura local para antecipar falhas e gargalos.  
- Compartilhar o conhecimento, assim como feito neste projeto!
  
---

## 🔐**Sobre**

Este projeto foi desenvolvido por **Georgia Pereira**, estudante de **Ciências da Computação** com foco em **Cibersegurança** e **Infraestrutura de Redes**.

O objetivo é aplicar, consolidar e compartilhar conhecimentos técnicos sobre **troubleshooting em redes domésticas**, abordando conceitos fundamentais como **CGNAT, QoS, SHA-256, Traffic Shaping**, entre outros.

O conteúdo está estruturado de forma didática e técnica para servir de referência tanto para estudos pessoais quanto para outros profissionais da área.

*Por questões de segurança e privacidade, optou-se por não incluir capturas de tela ou vídeos neste relatório. Como os testes não foram realizados em ambiente controlado (laboratório), qualquer demonstração prática poderia expor informações sensíveis da minha infraestrutura pessoal, comprometendo minha integridade e segurança.*
