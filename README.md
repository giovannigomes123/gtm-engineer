# Cloud Humans — GTM Engineer Case

Sistema de outbound consultivo orientado por IA e automação, desenvolvido em n8n para apoiar pesquisa, qualificação e preparação de contas com foco em contexto, relevância e eficiência operacional.

O objetivo do projeto NÃO é automatizar spam ou criar cadências massivas, mas sim utilizar IA como copiloto para aumentar inteligência operacional no processo de GTM.

---

# Arquitetura Geral

O projeto foi dividido em 3 workflows principais:

1. Geração de Leads via LinkedIn
2. Qualificação Inteligente de Leads
3. Geração de Abordagem Consultiva

Cada workflow possui uma responsabilidade específica dentro da operação.

---

# Workflow 1 — LinkedIn Comments Lead Generator

Arquivo:

```bash
/workflows/linkedin-comments-lead-generator.json
```

Objetivo:
Capturar leads a partir de comentários em posts estratégicos no LinkedIn.

---

## Como funciona

O workflow:

* monitora perfis específicos diariamente
* identifica novos posts publicados
* extrai comentários utilizando Apify
* remove duplicados
* filtra dados inválidos
* registra os leads em Google Sheets

---

## Inputs

* Perfis monitorados
* Últimos posts publicados

---

## Outputs

* Nome do lead
* Headline
* URL do LinkedIn
* Comentário realizado
* Empresa
* Dados iniciais para enriquecimento

---

## Tecnologias utilizadas

* n8n
* Apify
* Google Sheets
* LinkedIn scraping

---

## Objetivo estratégico

Transformar engajamento público em sinal de intenção e gerar listas mais contextualizadas para prospecção consultiva.

---

# Workflow 2 — AI Qualificator Agent

Arquivo:

```bash
/workflows/ai-qualificator-agent.json
```

Objetivo:
Enriquecer e qualificar automaticamente os leads utilizando IA e critérios de ICP.

---

## Como funciona

O workflow:

* coleta dados completos do perfil LinkedIn
* identifica empresa atual
* enriquece informações da empresa
* analisa descrição, tamanho e sinais operacionais
* utiliza LLM para classificação inteligente

---

## Critérios analisados

O agente avalia:

* fit com ICP
* operação digital
* sinais de escala operacional
* potencial de uso de IA/CX
* presença de atendimento recorrente
* maturidade operacional
* relevância do stakeholder

---

## Outputs

* ICP: SIM/NÃO/INDEFINIDO
* Stakeholder: SIM/NÃO/INDEFINIDO
* Hipóteses operacionais
* Sinais identificados
* Dados enriquecidos da conta

---

## Tecnologias utilizadas

* n8n
* OpenAI GPT
* Apify
* Google Sheets
* LinkedIn scraping

---

## Objetivo estratégico

Priorizar qualidade sobre volume, reduzindo falsos positivos e aumentando relevância operacional das contas trabalhadas.

---

# Workflow 3 — DM LinkedIn Agent

Arquivo:

```bash
/workflows/dm-linkedin-agent.json
```

Objetivo:
Gerar abordagens consultivas personalizadas utilizando IA e sinais públicos das contas.

---

## Como funciona

O workflow:

* recebe apenas leads aprovados
* analisa informações da empresa
* levanta hipóteses operacionais
* identifica possíveis dores
* gera mensagens contextualizadas

---

## Estratégia utilizada

A automação NÃO gera pitch agressivo.

O foco é:

* iniciar conversa
* demonstrar contexto
* levantar hipótese relevante
* gerar curiosidade
* evitar sensação de spam

---

## Outputs

* Resumo executivo da conta
* Hipóteses operacionais
* Stakeholders sugeridos
* Mensagem inicial personalizada

---

## Tecnologias utilizadas

* n8n
* OpenAI GPT
* Google Sheets

---

## Objetivo estratégico

Escalar personalização sem perder contexto humano, utilizando IA como copiloto operacional do processo comercial.

---

# Fluxo Completo

```text
LinkedIn Engagement
        ↓
Lead Extraction
        ↓
AI Qualification
        ↓
ICP Prioritization
        ↓
Context Generation
        ↓
Personalized Outreach
```

---

# Stack Utilizada

* n8n
* OpenAI GPT
* Apify
* Google Sheets
* LinkedIn Data Enrichment

---

# Estrutura do Repositório

```bash
/workflows
/screenshots
/examples
/spreadsheets
README.md
```

---

# Princípios do Projeto

## IA como copiloto

A IA auxilia na geração de contexto, hipóteses e priorização, mas não substitui relacionamento humano.

---

## Escala sem spam

A automação foi desenhada para aumentar qualidade operacional e personalização, não volume massivo.

---

## Outbound consultivo

O sistema prioriza sinais públicos, contexto e hipóteses relevantes antes de qualquer abordagem.

---

# Materiais Complementares

## Workflows

* `/workflows`

## Prints

* `/screenshots`

## Outputs gerados

* `/examples`

## Planilhas

* `/spreadsheets`

---

# Considerações Finais

O objetivo deste projeto foi demonstrar como IA e automação podem aumentar eficiência operacional em uma estratégia moderna de GTM sem transformar outbound em um processo genérico e massivo.

A proposta combina:

* automação
* enriquecimento
* IA
* priorização
* personalização
* contexto operacional

com foco em geração de conversas mais relevantes e escaláveis.
