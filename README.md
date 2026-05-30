# Engenharia-de-Endpoints

#Programas
🕵️‍♂️ X9-Endpoint v2.0 — O Sommelier de Link Suspeito

[![Python Version](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/)
[![Security Research](https://img.shields.io/badge/Focus-OSINT%20%24%20Infosec-red.svg)]()
[![Environment](https://img.shields.io/badge/Environment-Arch%20Linux-lightgood.svg)]()

O *X9-Endpoint* é um script em Python focado em engenharia reversa de URLs e inteligência de ameaças (OSINT). Ele foi desenvolvido para expor cadeias ocultas de redirecionamento HTTP, analisar técnicas de cloaking (disfarce de tráfego) e identificar payloads maliciosos ou comportamentos anômalos em links suspeitos diretamente pelo terminal.

---

## 🛠️ Estrutura dos Comandos e Arquitetura do Código

O script opera em quatro camadas consecutivas de análise tática:

1. *Bypass de Cloaking (User-Agent Spoofing):* Campanhas modernas de phishing frequentemente utilizam detecção de dispositivo. Se o acesso partir de uma ferramenta automatizada ou desktop, o servidor entrega uma página legítima. O script emula um navegador mobile (iPhone/iOS) para forçar o backend malicioso a exibir o comportamento real destinado à vítima.
2. *Rastreamento de Trilha (Redirect Chain):* Utilizando o histórico da biblioteca requests, o script documenta cada salto intermediário (Status 301/302), mapeando a rota exata do tráfego antes de chegar ao destino final.
3. *Análise de Infraestrutura:* Resolução dinâmica de IP e mapeamento de cabeçalhos (como o Server e proteções HSTS), expondo se o atacante está mascarado atrás de proxies reversos (ex: Cloudflare) ou utilizando servidores vulneráveis.
4. *Inspeção Baseada em Assinatura:* Varredura rápida no corpo do HTML retornado à procura de desvios invisíveis via código (como scripts em JavaScript ou tags Meta Refresh).

---

## 🚀 Como Executar

O script aceita passagem de argumentos direta ou modo interativo:

### Modo Direto (Argumento no terminal):

Python X9-Endpoint
