# Prompt-para-Analise-de-Feedbacks-Bancarios_DIO — Prompt de Engenharia para Análise de Feedbacks Bancários

![Status](https://img.shields.io/badge/Status-Concludido-2EA44F?style=flat-square)
![IA Generativa](https://img.shields.io/badge/IA_Generativa-LLM-764ABC?style=flat-square)
![Prompt Engineering](https://img.shields.io/badge/Prompt_Engineering-Deliverable-FF6F00?style=flat-square)
![CX](https://img.shields.io/badge/CX-Banking-0F9D58?style=flat-square)
![DIO](https://img.shields.io/badge/DIO-Entrega-9046F5?style=flat-square)

**Prompt de engenharia para análise de feedbacks de clientes bancários** — a entrega em si é o prompt: um documento pronto para uso que transforma um LLM em analista de dados e CX sênior de banco digital. Ele cobre o ciclo completo exigido de um prompt de produção: persona, contexto, schema de dados, instruções de análise, formato de saída estruturado e restrições de segurança. A estrutura segue o padrão role → contexto → dados → instruções → formato → restrições, com anti-alucinação (usar apenas dados fornecidos, não inventar números) e privacidade (nunca expor dados pessoais) embutidos nas restrições — não como pós-edição. Este README é o prompt completo, documentado.

---

## 🇧🇷 Português

### Sobre a entrega

Este repositório é a entrega do desafio de prompting para CX bancário da DIO. O README é o próprio prompt completo, documentado: copie o bloco abaixo, cole no seu LLM de preferência, anexe os feedbacks e receba a análise no formato especificado.

### O prompt

```text
Atue como analista de dados e experiência do cliente sênior em um banco digital.

Sua tarefa é analisar feedbacks de clientes bancários para identificar temas recorrentes, sentimento geral, problemas críticos, elogios e oportunidades de melhoria.

Contexto:
Estou trabalhando com feedbacks reais de clientes sobre os principais canais e produtos bancários (aplicativo, Pix, cartão de crédito, conta digital, empréstimos e atendimento via chat). A análise será usada pela equipe de Experiência do Cliente (CX) e pelos times de Produto e Atendimento para priorizar melhorias, reduzir churn e aumentar a satisfação.

Dados disponíveis:
Serão fornecidos feedbacks contendo: data do comentário, canal de atendimento, texto completo do feedback, produto/serviço citado e nota de satisfação (1 a 5).

Instruções de análise:

1. Classifique cada feedback por:
   - Tema principal (ex: usabilidade do app, velocidade do Pix, cobrança indevida, atendimento, etc.)
   - Sentimento (positivo, negativo, neutro ou misto)
   - Urgência/impacto (alto, médio ou baixo)
   - Produto/canal relacionado

2. Identifique os principais padrões, problemas recorrentes, elogios e oportunidades de melhoria.

3. Sempre aponte evidências diretas dos dados (use trechos curtos e representativos dos comentários, sem expor dados pessoais).

4. Sugira ações práticas, priorizadas e acionáveis para os times de Produto, Tecnologia e Atendimento.

Formato da resposta:

- Resumo Executivo (máximo 6-8 linhas): visão geral dos principais achados e impacto geral na satisfação.
- Tabela de Insights Principais: colunas → Tema | Frequência aproximada | Sentimento predominante | Evidência (exemplo) | Ação sugerida | Prioridade (Alta/Média/Baixa)
- Top 5 Prioridades: lista numerada com as 5 ações mais importantes, justificadas.
- Limitações observadas (se houver dados insuficientes em algum aspecto).

Restrições importantes:

- Use apenas os dados fornecidos. Não invente números, causas, estatísticas ou conclusões.
- Nunca exponha dados pessoais ou sensíveis (nomes, CPFs, contas, etc.).
- Seja objetivo e baseado em evidências.
- Use linguagem simples, direta, executiva e voltada para tomada de decisão.
- Caso a quantidade de feedbacks seja pequena, deixe claro que a análise tem limitação de representatividade.

Agora analise os feedbacks que vou fornecer abaixo e entregue a resposta exatamente neste formato.
```

### Anatomia do prompt

| Bloco | Conteúdo | Função |
|---|---|---|
| Persona | Analista de dados e CX sênior de banco digital | Fixa o tom, o vocabulário e o nível de senioridade das respostas |
| Contexto | App, Pix, cartão, conta, empréstimos, chat; uso pelos times de CX/Produto/Atendimento para priorizar melhorias, reduzir churn e aumentar satisfação | Restringe o domínio e define o consumidor da análise |
| Dados | Data, canal, texto, produto, nota 1–5 | Declara o schema de entrada esperado |
| Instruções | Classificação por tema/sentimento/urgência/produto; padrões recorrentes; evidências diretas; ações práticas priorizadas | Define o trabalho analítico em 4 blocos |
| Formato | Resumo Executivo, Tabela de Insights, Top 5 Prioridades, Limitações | Garante saída uniforme e executiva, pronta para apresentação |
| Restrições | Apenas dados fornecidos, sem números inventados, sem dados pessoais, linguagem executiva, limitação de representatividade declarada | Anti-alucinação e privacidade (LGPD) embutidas |

### Formato de saída

1. **Resumo Executivo** (6–8 linhas) — visão geral dos achados e impacto na satisfação.
2. **Tabela de Insights** — colunas: Tema \| Frequência \| Sentimento \| Evidência \| Ação \| Prioridade.
3. **Top 5 Prioridades** — lista numerada, justificada.
4. **Limitações** — quando os dados forem insuficientes.

### Por que essas restrições importam

Em CX bancário, duas falhas destroem a confiança na análise: números inventados (alucinação) e exposição de dados pessoais (violação LGPD). O prompt trata as duas na origem, como restrições de primeira classe: "use apenas os dados fornecidos" e "nunca exponha dados pessoais ou sensíveis". A exigência de evidências diretas (trechos curtos dos comentários) mantém cada insight rastreável até o dado bruto, e a regra de declarar limitação de representatividade em amostras pequenas evita que a equipe de CX superestime um padrão visto em 5 comentários.

---

## 🇺🇸 English

### About this deliverable

This repository is the DIO banking CX prompting challenge deliverable. The README is the prompt itself, fully documented: copy the block above (Portuguese section), paste it into your LLM of choice, attach the feedback data, and get the analysis in the specified format.

### Anatomy

| Block | Contents | Purpose |
|---|---|---|
| Persona | Senior data analyst & CX professional at a digital bank | Fixes tone, vocabulary, and seniority of the output |
| Context | App, Pix, card, account, loans, chat; consumed by CX/Product/Support teams to prioritize improvements, reduce churn, increase satisfaction | Constrains the domain and defines the analysis consumer |
| Data | Date, channel, text, product, 1–5 rating | Declares the expected input schema |
| Instructions | Classification by theme/sentiment/urgency/product; recurring patterns; direct evidence; prioritized practical actions | Defines the analytical work in 4 blocks |
| Output format | Executive Summary, Insights Table, Top 5 Priorities, Limitations | Ensures uniform, executive-ready output |
| Restrictions | Only provided data, no invented numbers, no personal data, executive language, representativeness caveat for small samples | Anti-hallucination and privacy baked in |

### Output format

1. **Executive Summary** (6–8 lines) — key findings and overall satisfaction impact.
2. **Insights Table** — columns: Theme \| Frequency \| Sentiment \| Evidence \| Action \| Priority.
3. **Top 5 Priorities** — numbered, justified list.
4. **Limitations** — flagged whenever data is insufficient.

### Why these restrictions matter

In banking CX, two failures destroy trust in an analysis: invented numbers (hallucination) and leaked personal data (a privacy/LGPD violation). The prompt handles both at the source, as first-class restrictions: "use only the provided data" and "never expose personal or sensitive data". The direct-evidence requirement (short quote snippets) keeps every insight traceable back to raw data, and the small-sample representativeness rule stops the CX team from over-trusting a pattern seen in 5 comments.

---

## Autor

**Kelvin Oliveira** — [GitHub](https://github.com/KelvinOliveiraCode) · [LinkedIn](https://www.linkedin.com/in/kelvin-oliveira-0282033b4/)

## Licença

Projeto educacional, desenvolvido para o desafio da DIO. Sem licença de software formal — os materiais servem como referência de estudo.
