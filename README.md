# 🚀 Gemini CLI: Super-Comandos de Engenharia & Auditoria

Este repositório contém uma coleção de **prompts estruturados (.toml)** de alta performance para o Gemini CLI. Eles transformam o assistente em um Arquiteto Sênior, Engenheiro de Segurança ou Auditor de Missão Crítica para projetos PHP (8.2+).

---

## 📍 Índice de Especialidades

*   [🧹 /ccoop - Clean Code OOP](#-clean-code-oop-ccoop)
*   [📜 /ccproc - Clean Code Procedural](#-clean-code-procedural-ccproc)
*   [🚀 /nasaoop - Padrão NASA OOP](#-padrão-nasa-oop-nasaoop)
*   [🛰️ /nasaproc - Padrão NASA Procedural](#-padrão-nasa-procedural-nasaproc)
*   [🛡️ /owasp - Auditoria AppSec (OWASP/SANS)](#-auditoria-appsec-owasp-owasp)
*   [💎 /solid - Purismo Arquitetural SOLID](#-solid-purismo-arquitetural-solid)
*   [🔌 /wpsec - WordPress Security Expert](#-wpsec-wordpress-security-expert)

---

## 🛠️ Guia de Uso Geral

Você pode interagir com estes comandos de duas formas principais:

### 1. Modo Arquiteto (Criação do Zero)
Forneça uma instrução em texto para gerar código seguindo os padrões do comando.
```bash
gemini /solid "Crie um sistema de processamento de pagamentos com suporte a Stripe e PayPal"
```

### 2. Modo Auditor (Refatoração e Auditoria)
Referencie arquivos ou diretórios usando o símbolo `@`. O Gemini fará uma auditoria e aguardará autorização para refatorar.
```bash
# Para um arquivo específico
gemini /owasp @src/Controller/LoginController.php

# Para uma pasta inteira
gemini /wpsec @wp-content/plugins/meu-plugin/
```

---

## 🧹 Clean Code OOP (`/ccoop`)
**Especialidade:** Arquiteto de Software Sênior especialista em PHP moderno e estética de código orientado a objetos.

### 💻 Como usar:
```bash
gemini /ccoop "Crie uma classe para gerenciar pedidos de um e-commerce"
# OU
gemini /ccoop @src/Domain/OrderManager.php
```

**🔍 Elementos Abordados:**
*   **Fundamentos Universais:**
    *   **DRY:** Evita duplicação extraindo lógica para métodos ou classes.
    *   **KISS:** Prefere soluções simples e legíveis a complexidade desnecessária.
    *   **YAGNI:** Implementa apenas o que é estritamente necessário hoje.
    *   **SoC:** Separa claramente as responsabilidades do código.
    *   **Código Morto:** Remove qualquer código não utilizado e otimiza os `imports`.
*   **Nomenclatura e Legibilidade:**
    *   Exige nomes significativos para variáveis, funções e classes que revelem sua intenção.
    *   Promove código "autoexplicativo", onde comentários explicam o "porquê" (regras de negócio), nunca o "o quê".
*   **Design de Métodos e Funções:**
    *   Devem ser curtos e focados em uma única responsabilidade.
    *   Devem ter o mínimo de argumentos possível para facilitar a leitura.
    *   Devem usar abstração para esconder complexidade e revelar a intenção.
*   **Design de Classes (OOP Strict):**
    *   **SRP:** Classes devem ter uma única responsabilidade e uma única razão para mudar.
    *   **Alta Coesão:** As variáveis de instância de uma classe devem ser usadas pela maioria de seus métodos.
    *   **Baixo Acoplamento e Encapsulamento:** Esconde detalhes de implementação e expõe apenas o necessário.
    *   **Lei de Demeter:** Garante que um objeto conheça o mínimo sobre a estrutura interna de seus colaboradores.
*   **Fluxo e Erros:**
    *   Utiliza **Exceções** em vez de retornar códigos de erro genéricos ou `false`.

---

## 📜 Clean Code Procedural (`/ccproc`)
**Especialidade:** Especialista em organizar fluxos de execução lineares e scripts isolados com funções puras.

### 💻 Como usar:
```bash
gemini /ccproc "Crie um script para processar um CSV de usuários e importar para o banco"
# OU
gemini /ccproc @scripts/import-users.php
```

**🔍 Elementos Abordados:**
*   **Fundamentos Universais:**
    *   **DRY:** Evita duplicação extraindo blocos lógicos para funções menores.
    *   **KISS:** Mantém o fluxo de execução simples e legível.
    *   **YAGNI:** Implementa apenas o que é necessário, sem adições "para o futuro".
    *   **SoC:** Garante que cada script ou função tenha uma responsabilidade única e clara.
*   **Legibilidade e Nomenclatura:**
    *   Exige nomes significativos para variáveis e funções que revelem sua intenção.
    *   Promove código "autoexplicativo", onde comentários explicam o "porquê", nunca o "o quê".
*   **Design de Funções e Abstração:**
    *   Funções devem ser pequenas e estritamente focadas em uma única tarefa.
    *   Uso de poucos argumentos para facilitar o consumo das funções.
    *   Extrai lógicas de baixo nível para funções auxiliares, revelando a intenção do fluxo principal.
*   **Acoplamento e Isolamento:**
    *   Proíbe o uso de variáveis globais (`global $var`).
    *   Minimiza dependências passando-as como argumentos de função.
*   **Fluxo e Erros:**
    *   Usa **"Early Returns"** (cláusulas de guarda) para evitar aninhamento de `if`s.
    *   Utiliza **Exceções** em vez de retornar `false` ou códigos de erro genéricos.

---

## 🚀 Padrão NASA OOP (`/nasaoop`)
**Especialidade:** Engenheiro de Missão Crítica focado em previsibilidade total e software que não pode falhar (OOP).

### 💻 Como usar:
```bash
gemini /nasaoop "Crie o módulo de controle de trajetória do satélite"
# OU
gemini /nasaoop @src/Core/FlightControl.php
```

**🔍 Elementos Abordados:**
*   **Nomenclatura Autoexplicativa:**
    *   O propósito de classes, métodos e variáveis deve ser imediatamente claro em seus nomes.
    *   Nomes genéricos como `$data`, `process()`, ou `$result` são estritamente proibidos.
*   **Simplicidade e Previsibilidade:**
    *   Cada classe e método deve ter um comportamento previsível, linear e sem efeitos colaterais.
    *   Prefere código óbvio e até redundante a código "esperto" ou super-compactado.
*   **Programação Defensiva (Fail Securely):**
    *   Valida **TODOS** os argumentos no início de cada método usando `Guard Clauses`.
    *   Trata todos os casos de erro explicitamente, sem ignorar exceções (`catch` vazio é proibido).
*   **Verificabilidade e Rastreabilidade:**
    *   Evita lógica condicional complexa e aninhada.
    *   Cada decisão no código deve ser simples e testável de forma isolada.
*   **Minimalismo (YAGNI):**
    *   Implementa apenas o que é estritamente necessário para o requisito atual.
    *   Remove agressivamente todo código morto e evita abstrações prematuras.

---

## 🛰️ Padrão NASA Procedural (`/nasaproc`)
**Especialidade:** O rigor aeroespacial aplicado a scripts funcionais e fluxos lineares estritos.

### 💻 Como usar:
```bash
gemini /nasaproc "Script de telemetria para sensores de temperatura"
# OU
gemini /nasaproc @telemetry/processor.php
```

**🔍 Elementos Abordados:**
*   **Nomenclatura Autoexplicativa:**
    *   O propósito de funções e variáveis deve ser imediatamente claro em seus nomes.
*   **Simplicidade Extrema e Previsibilidade:**
    *   Cada função deve ter comportamento linear e previsível, sem efeitos colaterais.
    *   Prefere código óbvio a atalhos "espertos" que exijam esforço cognitivo.
*   **Programação Defensiva:**
    *   Valida **TODOS** os argumentos de entrada no topo de cada função (`Early Returns`).
    *   Trata todos os erros, sem ignorar falhas silenciosamente.
*   **Verificabilidade e Isolamento:**
    *   Evita aninhamento profundo (`Ifs` aninhados).
    *   Proíbe o uso de variáveis globais, passando dependências como parâmetros.
*   **Minimalismo:**
    *   Implementa apenas o requisito, sem código não utilizado ou desnecessário.

---

## 🛡️ Auditoria AppSec OWASP (`/owasp`)
**Especialidade:** Engenheiro de AppSec (Application Security) focado em detectar vulnerabilidades (Red Team).

### 💻 Como usar:
```bash
gemini /owasp @src/Auth/Authenticator.php
# OU
gemini /owasp @src/API/Endpoints/
```

**🔍 Elementos Abordados (OWASP Top 10 + SANS/CWE):**
*   **A01: Quebra de Controle de Acesso:**
    *   IDOR (Insecure Direct Object Reference), falhas de restrição de rota e *Forced Browsing*.
*   **A03: Injection:**
    *   SQL Injection (SQLi), Command Injection, LDAP Injection.
*   **A08: Falhas de Integridade de Software e Dados:**
    *   Desserialização Insegura de objetos (`unserialize`).
*   **Cross-Site Scripting (XSS):**
    *   Falhas de *Output Encoding* (`esc_html`, `esc_attr`).
*   **Cross-Site Request Forgery (CSRF):**
    *   Ações de mudança de estado sem validação de token (Nonce).
*   **Outras Vulnerabilidades Críticas:**
    *   SSRF (Server-Side Request Forgery), Path Traversal (LFI/RFI) e falhas de configuração de segurança.

---

## 💎 Purismo SOLID (`/solid`)
**Especialidade:** Purista em Design de Sistemas PHP 8.2+, focado em arquitetura desacoplada e evolutiva.

### 💻 Como usar:
```bash
gemini /solid "Crie uma arquitetura para envio de notificações via E-mail, SMS e Push"
# OU
gemini /solid @src/Services/NotificationService.php
```

**🔍 Elementos Abordados:**
*   **[S] Single Responsibility Principle:**
    *   A classe atende a apenas um "Ator"?
    *   Separa estritamente Regras de Negócio de Detalhes de Infraestrutura (BD, HTTP).
*   **[O] Open/Closed Principle:**
    *   Substitui `if/elseif` ou `switch` por polimorfismo (padrões Strategy, Factory).
*   **[L] Liskov Substitution Principle:**
    *   Proíbe o uso de `instanceof` para desviar comportamento.
    *   Subclasses devem preservar as invariantes e o contrato das classes pai.
*   **[I] Interface Segregation Principle:**
    *   Evita "Header Interfaces" (interfaces genéricas e gordas).
    *   Classes não devem depender de métodos que não utilizam.
*   **[D] Dependency Inversion Principle:**
    *   Proíbe o uso de `new` para instanciar dependências voláteis (APIs, BDs) em lógicas de negócio.
    *   Dependências devem ser injetadas via construtor, baseadas em abstrações (Interfaces).

---

## 🔌 WordPress Security Expert (`/wpsec`)
**Especialidade:** Auditor de Segurança WP Sênior, mestre nas APIs nativas do WordPress Core.

### 💻 Como usar:
```bash
gemini /wpsec "Crie um plugin para formulário de contato customizado"
# OU
gemini /wpsec @wp-content/plugins/my-custom-plugin/
```

**🔍 Elementos Abordados:**
*   **Validação e Sanitização de Entradas:**
    *   Uso obrigatório de `sanitize_text_field()`, `absint()`, `wp_kses_post()` em dados de `$_GET` e `$_POST`.
*   **Escapamento de Saídas (Late Escaping):**
    *   Verificação de `esc_html()`, `esc_attr()`, `esc_url()` no momento exato do `echo`.
*   **Proteção contra CSRF (Nonces):**
    *   Validação de intenção com `wp_verify_nonce()` em formulários e `check_ajax_referer()` em AJAX.
*   **Autorização e Controle de Acesso:**
    *   Verificação de permissões com `current_user_can()` antes de ações sensíveis.
    *   Existência da constante de proteção `if (!defined('ABSPATH')) exit;`.
*   **Segurança de Banco de Dados (SQLi):**
    *   Uso obrigatório de `$wpdb->prepare()` para todas as queries.
*   **Segurança do Sistema de Arquivos:**
    *   Validação de uploads e uso de constantes seguras como `plugin_dir_path()`.

---

> **Nota Técnica:** Todos os comandos de auditoria operam em um fluxo de **duas etapas**: primeiro o relatório técnico detalhado, depois a refatoração apenas após sua autorização explícita.
