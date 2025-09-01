# Projeto de Score de Performance de Email Marketing

## 1. Objetivo do Projeto

Este projeto foi criado para **padronizar a análise de performance** das nossas campanhas de email marketing. O objetivo é traduzir múltiplas métricas em um **único score de performance (PPE - Pontuação de Performance de Email)**, permitindo:

-   **Comparação objetiva** entre diferentes campanhas.
-   **Análise rápida** do sucesso de um envio ("foi bom ou ruim?").
-   **Tomada de decisões baseada em dados** para otimizar nossa estratégia de comunicação.
-   **Avaliar o engajamento** em todas as fases da jornada do nosso estudante, desde a captação até a rematrícula.

## 2. O Modelo de Score: Foco em Relacionamento com Bônus de Ação

Após análise da nossa estratégia de comunicação, que inclui muitos emails informativos sem um "Call to Action" (CTA) direto, o modelo foi desenhado para valorizar primariamente o **relacionamento com o público** e a **saúde da nossa lista**. Cliques são tratados como um "bônus de engajamento", que agregam valor mas não são essenciais para uma boa pontuação.

### A Fórmula Final

O score de cada campanha é calculado usando a seguinte fórmula ponderada:

Score = (Open Rate * 0.40) - (Bounce Rate * 0.35) - (Unsubscribe Rate * 0.15) + (CTR * 0.10) + (CTOR * 0.05)


### Detalhamento dos Pesos

| Métrica                      | Peso   | Justificativa Estratégica                                                                                                                              |
| :--------------------------- | :----- | :----------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Taxa de Abertura**         | **+40%** | **Métrica Principal.** Mede o sucesso do nosso assunto e remetente em capturar a atenção. É a base do nosso engajamento.                                 |
| **Taxa de Rejeição (Bounce)**| **-35%** | **Guardião da Reputação.** Penaliza severamente listas de emails desatualizadas ou de má qualidade, que prejudicam nossa capacidade de entrega a longo prazo. |
| **Taxa de Cancelamento**     | **-15%** | **Termômetro da Relevância.** Mede a perda de audiência e indica se nosso conteúdo está alinhado com as expectativas do público.                         |
| **Taxa de Clique (CTR)**     | **+10%** | **Bônus de Ação.** Recompensa campanhas que motivam o usuário a dar o próximo passo. É um indicador de engajamento ativo.                                |
| **Taxa de Clique por Abertura (CTOR)**| **+5%** | **Bônus de Qualidade do Conteúdo.** Valoriza emails cujo conteúdo foi tão persuasivo que convenceu o leitor a clicar.                                    |

---

## 3. Detalhamento das Métricas e Seus Cálculos

Para garantir total transparência, aqui está o detalhamento de cada métrica utilizada no score.

### 3.1. Taxa de Abertura (Open Rate)
-   **O que mede?** O interesse inicial do público no nosso email.
-   **Como é calculada?** `(Aberturas Únicas / Emails Entregues) * 100`
-   **Por que é importante?** Indica a eficácia do nosso nome de remetente, linha de assunto e a relevância do tema para o público segmentado.

### 3.2. Taxa de Rejeição (Bounce Rate)
-   **O que mede?** A porcentagem de emails que não puderam ser entregues.
-   **Como é calculada?** `(Total de Emails Rejeitados / Total de Emails Enviados) * 100`
-   **Por que é importante?** É a métrica mais crítica para a saúde da nossa lista e reputação como remetente. Taxas altas podem fazer com que nossos emails sejam bloqueados ou caiam na caixa de spam.

### 3.3. Taxa de Cancelamento de Inscrição (Unsubscribe Rate)
-   **O que mede?** A porcentagem de destinatários que optaram por não receber mais nossas comunicações.
-   **Como é calculada?** `(Total de Cancelamentos / Emails Entregues) * 100`
-   **Por que é importante?** É um feedback direto de que nosso conteúdo ou frequência não estão adequados para aquele usuário.

### 3.4. Taxa de Clique (CTR - Click-Through Rate)
-   **O que mede?** A porcentagem de destinatários que clicaram em algum link do email.
-   **Como é calculada?** `(Cliques Únicos / Emails Entregues) * 100`
-   **Por que é importante?** Mede a eficácia da campanha em gerar uma ação, sendo fundamental para emails com CTA.

### 3.5. Taxa de Clique por Abertura (CTOR - Click-to-Open Rate)
-   **O que mede?** A eficácia do conteúdo do email em gerar um clique *entre as pessoas que o abriram*.
-   **Como é calculada?** `(Cliques Únicos / Aberturas Únicas) * 100`
-   **Por que é importante?** Ajuda a diagnosticar problemas. Uma campanha com muitas aberturas mas baixo CTOR teve um bom assunto, mas um conteúdo fraco.

---

## 4. Como Interpretar a Pontuação Final

O score gerado pela fórmula pode ser classificado em faixas de performance para facilitar a análise.

| Pontuação (Score) | Nível de Efetividade | Análise e Ação Recomendada                                                                                                                          |
| :---------------- | :------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Acima de 18**   | ✅ **Excelente**     | Campanha de alta performance. Cumpriu os objetivos de engajamento e manteve a saúde da lista impecável. **Ação:** Analisar para replicar o sucesso.      |
| **12 a 17.9**     | 👍 **Bom / Efetivo** | Resultado sólido. A campanha funcionou bem, com bom alcance e sem prejudicar a reputação. **Ação:** Manter as boas práticas.                             |
| **5 a 11.9**      | 🟡 **Na Média**      | Desempenho aceitável, mas com claro espaço para melhorias. Pode ter tido uma abertura mediana ou bounces um pouco elevados. **Ação:** Otimizar pontos fracos. |
| **1 a 4.9**       | ⚠️ **Precisa de Atenção**| Resultado fraco. O engajamento foi baixo ou as métricas negativas foram preocupantes. **Ação:** Investigar a causa (segmentação, conteúdo, saúde da lista). |
| **Abaixo de 1**   | ❌ **Crítico**        | Campanha ineficaz e potencialmente prejudicial. Bounces e cancelamentos altos podem ter gerado um score baixo ou negativo. **Ação:** Ação imediata! Pausar e corrigir a estratégia. |

---

## 5. Notas Técnicas e Solução de Problemas

### Lidando com o Erro `#DIV/0!` no Cálculo do CTOR
-   **Causa:** Este erro ocorre quando uma campanha tem **zero aberturas**, e a fórmula do CTOR tenta dividir o número de cliques por zero.
-   **Solução na Planilha:** Para evitar que o erro apareça, use a função `SEERRO` (em português) ou `IFERROR` (em inglês).
    -   Exemplo: `=SEERRO((Cliques / Aberturas); 0)`
-   **Análise Estratégica:** Uma campanha com zero aberturas é um problema grave. Investigue a entregabilidade (spam, bounces), a segmentação e a linha de assunto.
