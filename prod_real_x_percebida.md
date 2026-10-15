# Tema 3 — Produtividade real vs. produtividade percebida ao programar com IA

**Disciplina:** ENS4000 — Gerência de Configuração  
**Trabalho:** T1 · Grupo 1 — Produtividade  
**Pergunta que este tema responde:** A sensação de ser mais produtivo com IA é prova de que se produz mais?  
**Tese defendida:** a IA pode melhorar a experiência de programar e acelerar algumas etapas, mas a sensação de velocidade não prova que uma tarefa completa tenha sido concluída mais depressa.

> **Política de fontes:** este texto usa EXCLUSIVAMENTE referências designadas pelo professor para o Grupo 1. Não foram usados artigos indicados aos Grupos 2, 3, 4 ou 5. As interpretações e exemplos criados para fins didáticos estão marcados como tal.

## 1. O que significam os dois tipos de produtividade?

### Produtividade percebida

É a avaliação que o próprio desenvolvedor faz do seu rendimento: «A ferramenta me ajudou?», «Estou escrevendo código mais rápido?», «Estou menos travado?», «Sinto que realizei mais?». É um dado válido sobre a experiência do usuário, mas é **subjetivo**. Pode variar conforme facilidade de uso, conforto, confiança, frequência de sugestões úteis e satisfação com o trabalho.

### Produtividade observada (ou medida)

É o desempenho registrado por alguma medida verificável e explicitada antes da comparação. No estudo da METR, foi o **tempo de execução de tarefas reais definidas previamente**. Em uma avaliação mais ampla, também é possível considerar conclusão dos requisitos, testes, defeitos, correções e entregas. Não há uma métrica única capaz de representar todos esses aspectos.

**Distinção essencial:** receber uma sugestão de código em segundos é acelerar *uma etapa*. Terminar uma funcionalidade correta exige compreender o problema, implementar, revisar, testar e corrigir.

**Exemplo inventado, apenas para explicar:** sem IA, 30 minutos para escrever código + 20 para revisar/testar = **50 minutos**. Com IA, 10 minutos para gerar código + 50 para conferir/ajustar = **60 minutos**. A escrita melhorou; o tempo total piorou. Esse exemplo **não é resultado de pesquisa**.

## 2. Evidência central: METR (Becker et al., 2025)

**Artigo-âncora do Grupo 1:** *Measuring the Impact of Early-2025 AI on Experienced Open-Source Developer Productivity*.

### Método: o que foi feito?

- **16 desenvolvedores experientes**, que já trabalhavam em grandes projetos de código aberto.
- **246 tarefas reais** (correções, funcionalidades e refatorações) em repositórios maduros.
- Os participantes tinham, em média, **cinco anos de experiência naqueles repositórios**.
- As tarefas foram distribuídas aleatoriamente entre duas condições: **IA permitida** e **IA não permitida**. Quando permitida, os desenvolvedores podiam escolher ferramentas; predominaram Cursor Pro e Claude 3.5/3.7 Sonnet.
- Período estudado: ferramentas disponíveis entre **fevereiro e junho de 2025**.
- Os pesquisadores compararam o tempo de conclusão das tarefas e coletaram previsões e avaliações subjetivas dos participantes.

**Por que a atribuição aleatória importa?** Ela reduz a chance de que todas as tarefas fáceis fiquem no grupo com IA e todas as difíceis no grupo sem IA. Isso ajuda a estimar o *efeito causal de permitir IA naquele cenário*, embora o resultado continue limitado à população e ao contexto estudados.

### Resultado: três números que devem ser entendidos separadamente

| Pergunta | Resultado | Tipo de evidência |
|---|---:|---|
| Antes do trabalho, quanto achavam que a IA reduziria o tempo? | **24% menos tempo** | Previsão subjetiva |
| Depois do trabalho, quanto acreditavam ter economizado? | **20% menos tempo** | Avaliação subjetiva retrospectiva |
| O que ocorreu ao comparar os tempos reais? | **19% mais tempo com IA permitida** | Resultado estimado do experimento |

A comparação não significa que «19% dos programadores pioraram». Significa que, **na estimativa média de efeito sobre o tempo de execução das tarefas estudadas**, permitir IA foi associado causalmente a um tempo **19% maior**. Tampouco «menos 24» e «mais 19» devem ser somados como se fossem partes de um mesmo cálculo: um é previsão; o outro é efeito medido.

**Exemplo matemático inventado:** se uma tarefa equivalente levaria 100 minutos sem IA, um aumento de 19% corresponde a 119 minutos com IA. É apenas uma maneira de interpretar a porcentagem, **não um tempo médio publicado pela METR**.

### Por que isso pode ter ocorrido?

O artigo analisou o contexto do experimento e gravações de tela. Entre as **explicações discutidas** estão:

- Os participantes já conheciam muito bem seus repositórios; a IA tinha menos vantagem em localizar e compreender informações que eles já dominavam.
- Repositórios grandes e maduros apresentam requisitos implícitos, padrões internos e expectativas de integração difíceis de reconstruir apenas com prompts.
- Formular pedidos, esperar respostas, avaliar sugestões e corrigir código gera custos adicionais.
- Uma sugestão aparentemente próxima do correto pode demandar mais inspeção e retrabalho do que escrever o código diretamente.

**Cuidado científico:** a METR investigou possíveis fatores, mas não demonstrou que apenas um deles explique todo o aumento de tempo. Também não provou que IA atrapalha todos os desenvolvedores, todas as tarefas ou os modelos posteriores a 2025.

## 3. Contraponto importante: Peng et al. (2023)

Em *The Impact of AI on Developer Productivity: Evidence from GitHub Copilot*, pesquisadores conduziram experimento controlado no qual desenvolvedores deveriam implementar um **servidor HTTP em JavaScript**. A condição com GitHub Copilot concluiu a tarefa **55,8% mais rápido**, na estimativa do estudo.

| Comparação | Peng et al. (2023) | METR (2025) |
|---|---|---|
| Tipo de tarefa | Servidor HTTP delimitado | Correções e mudanças reais em projetos maduros |
| Contexto | Experimento padronizado | Trabalho no próprio repositório de código aberto |
| Assistente avaliado | GitHub Copilot | Principalmente Cursor Pro e Claude 3.5/3.7 |
| Resultado de tempo | **55,8% mais rápido** | **19% mais demorado** |

**Essas porcentagens não são contraditórias por definição.** Elas descrevem populações, tarefas, ferramentas e momentos diferentes. Não faz sentido calcular a média entre 55,8% e -19% para afirmar «o efeito da IA» em geral.

**O que falar:** quando a tarefa é pequena, bem definida e com pouco contexto externo, a geração automática pode poupar bastante tempo; quando a tarefa exige compreender regras de um projeto grande, validar a integração pode consumir esse ganho. Essa frase é uma **interpretação comparativa plausível**, não uma regra universal provada pela comparação dos dois estudos.

## 4. Ziegler et al. (2022): o que faz um desenvolvedor *sentir* produtividade?

O artigo *Productivity Assessment of Neural Code Completion*, também indicado pelo professor ao Grupo 1, investigou usuários de **GitHub Copilot** e comparou **respostas de questionários** com **dados de uso da ferramenta**.

Os pesquisadores examinaram indicadores como:

- **Taxa de aceitação:** sugestões aceitas / sugestões exibidas.
- **Persistência do código:** se trechos aceitos permanecem no código após um período.
- **Volume de código sugerido e aceito:** quantidade de sugestões e caracteres.
- **Produtividade autodeclarada:** como o usuário avaliava a própria experiência.

**Achado central:** entre as medidas examinadas, a **taxa de aceitação das sugestões** foi a que melhor se relacionou com a **percepção de produtividade**. No estudo, a correlação relatada com a medida agregada de produtividade percebida foi **ρ = 0,24** (estatisticamente detectável, mas de magnitude limitada).

### Como interpretar sem errar

**Pode afirmar:** quem aceita sugestões com maior frequência *tendia*, nesse conjunto de dados, a relatar maior produtividade percebida.  
**Não pode afirmar:** aceitar mais sugestões prova que o programa ficou melhor, que a entrega terminou antes ou que a IA causou ganho de produtividade real.

Isso ajuda a explicar por que uma ferramenta pode «parecer útil»: ela participa visivelmente da escrita do código. Contudo, a aceitação de uma sugestão é uma ação do desenvolvedor, **não o resultado final da entrega**.

O artigo não é o mesmo experimento da METR. Em Ziegler, a questão principal era identificar indicadores correlacionados à **experiência percebida**; na METR, a questão foi medir **tempo de tarefa** com atribuição aleatória.

## 5. Conclusão do Tema 3

1. Percepção **não é falsa nem inútil**: informa conforto, satisfação e utilidade percebida.
2. Percepção **não é comprovação de velocidade**: o resultado precisa ser medido.
3. A METR demonstra uma divergência concreta entre previsão, avaliação posterior e tempo observado.
4. Peng demonstra que **ganhos reais podem ocorrer** em outros tipos de tarefa.
5. Ziegler mostra por que **usar e aceitar sugestões** pode estar ligado à sensação de produtividade, sem medir diretamente o resultado final.

**Frase de fechamento para o slide:** «A pergunta não é apenas se a IA ajudou a escrever código, mas se ajudou a concluir a tarefa corretamente, em menos tempo».

## 6. Referências — todas indicadas para o Grupo 1

1. BECKER, J.; RUSH, N.; BARNES, E.; REIN, D. **Measuring the Impact of Early-2025 AI on Experienced Open-Source Developer Productivity**. METR, 2025. Artigo-âncora. <https://arxiv.org/abs/2507.09089>.
2. PENG, S.; KALLIAMVAKOU, E.; CIHON, P.; DEMIRER, M. **The Impact of AI on Developer Productivity: Evidence from GitHub Copilot**. 2023. <https://arxiv.org/abs/2302.06590>.
3. ZIEGLER, A. et al. **Productivity Assessment of Neural Code Completion**. MAPS, 2022. <https://arxiv.org/abs/2205.06537> · <https://doi.org/10.1145/3520312.3534864>.
4. METR. **Página explicativa do experimento com desenvolvedores experientes**. 2025. <https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/>.