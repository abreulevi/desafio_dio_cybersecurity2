# Análise Educacional de Ameaças: Ransomware e Keylogger

> ⚠️ **Aviso Legal:** Este repositório tem fins estritamente acadêmicos e educacionais. As análises e documentações aqui presentes visam o estudo de mecanismos de defesa e a compreensão tática de malwares para fortalecer a segurança da informação.

## 📌 Sobre o Projeto

Este projeto documenta o estudo teórico e prático sobre o funcionamento de duas das ameaças mais comuns e prejudiciais no cenário atual de cibersegurança: **Ransomwares** e **Keyloggers**. O objetivo principal é dissecar o comportamento desses malwares, entender como eles exploram vulnerabilidades (tanto sistêmicas quanto humanas) e detalhar as estratégias de defesa necessárias para mitigar esses riscos no mundo real.

---

## 🦠 Parte 1: Estudo sobre Ransomware

### O que é e como funciona?
O Ransomware é um tipo de malware de extorsão que sequestra os dados da vítima por meio de criptografia forte. O fluxo de ataque geralmente segue estas etapas:
1. **Infecção:** Geralmente ocorre via *phishing*, engenharia social ou exploração de vulnerabilidades em serviços expostos.
2. **Execução e Criptografia:** O script malicioso varre o sistema em busca de extensões de arquivos críticos (documentos, bancos de dados, imagens) e utiliza bibliotecas de criptografia (como AES ou RSA) para torná-los inacessíveis.
3. **Extorsão:** O malware gera uma nota de resgate (geralmente um arquivo `.txt` ou `.html`), exigindo pagamento (comumente em criptomoedas) em troca da chave de descriptografia.

### Reflexões e Impacto
A principal arma do Ransomware não é apenas a tecnologia de criptografia, mas o desespero do usuário ou da organização. A ameaça de perda permanente de dados paralisa operações inteiras. Do ponto de vista técnico, a facilidade de implementar bibliotecas de criptografia modernas em linguagens como Python torna o desenvolvimento dessas ameaças assustadoramente acessível.

---

## ⌨️ Parte 2: Estudo sobre Keylogger

### O que é e como funciona?
Um Keylogger é um malware de espionagem focado em interceptar e registrar as teclas pressionadas pelo usuário. O ciclo de vida da ameaça inclui:
1. **Hooking:** O script utiliza bibliotecas nativas ou de terceiros para se "pendurar" nos eventos de teclado do sistema operacional.
2. **Armazenamento:** As teclas capturadas são gravadas em um arquivo local, muitas vezes de forma oculta.
3. **Exfiltração:** Para ser útil ao atacante, o malware automatiza o envio periódico desses logs para um servidor externo ou via e-mail (ex: utilizando protocolos como SMTP).

### Reflexões e Impacto
O Keylogger é uma ameaça silenciosa. Seu maior perigo reside na captura de credenciais de acesso, dados bancários e informações confidenciais em tempo real, muitas vezes contornando proteções baseadas em armazenamento de cookies de sessão no navegador, já que a captura ocorre no momento da digitação. A furtividade é a chave do sucesso deste ataque.

---

## 🛡️ Reflexão sobre Defesa e Prevenção

Compreender o ataque é o primeiro passo para arquitetar a defesa. Durante este estudo, ficou claro que a proteção contra essas ameaças exige uma abordagem em múltiplas camadas (Defesa em Profundidade):

* **Ambientes de Sandboxing e Laboratórios Isolados:** A análise de malwares deve ser feita em ambientes altamente controlados. A montagem de laboratórios com máquinas virtuais configuradas sem vinculação a contas em nuvem (para evitar sincronização acidental de arquivos) é fundamental para estudar o comportamento dinâmico do malware sem risco de propagação.
* **Monitoramento de Rede e Tráfego:** A exfiltração de dados (no caso do Keylogger) exige comunicação com a internet. O uso de firewalls e o entendimento profundo das camadas de rede permitem detectar tráfego anômalo, como conexões SMTP não autorizadas ou túneis que tentam se esconder via proxies ou VPNs suspeitas.
* **Soluções EDR e Antivírus:** Ferramentas modernas de detecção de endpoint não analisam apenas assinaturas, mas o comportamento. Um script Python tentando criptografar o disco inteiro rapidamente levantaria um alerta de heurística.
* **Gestão de Backups Offline:** A única defesa definitiva contra um Ransomware bem-sucedido é possuir backups frequentes e mantidos fora da rede principal (air-gapped).
* **Conscientização (Security Awareness):** Como a maioria dessas ameaças entra através de interação do usuário (phishing, downloads maliciosos), o treinamento do fator humano continua sendo uma das barreiras mais eficientes.

## 🎓 Aprendizados Finais

Este desafio reforçou a perspectiva de que a segurança da informação é um jogo de gato e rato contínuo. Entender como automatizar a captura de dados ou a criptografia de arquivos demonstra o quanto atacantes podem causar danos com linhas simples de código. Como profissionais de segurança, nosso foco deve ser sempre antecipar esses vetores, garantir a visibilidade dos sistemas e aplicar controles rigorosos de acesso e monitoramento.
