# Tema 4 — Como medir a produtividade de desenvolvedores com IA

**Disciplina:** ENS4000 — Gerência de Configuração  
**Trabalho:** T1 · Grupo 1 — Produtividade  
**Pergunta que este tema responde:** Como comprovar, com indicadores confiáveis, que o uso de IA trouxe ganho real?  
**Tese defendida:** produtividade de software não pode ser inferida apenas do volume de código ou da sensação de velocidade; precisamos avaliar tarefa concluída, tempo total, qualidade, retrabalho e impacto na entrega.

> **Política de fontes:** somente referências indicadas pelo professor para o Grupo 1 — METR, Peng, Ziegler e DORA 2024/2025 — além da documentação oficial do DORA, usada apenas para definir os indicadores. Nenhum artigo designado a outro grupo foi utilizado.

## 1. Primeiro, o que quer dizer «ser produtivo»?

Na programação, gerar mais texto pode aumentar a **atividade** sem gerar mais **valor**. Um desenvolvedor pode entregar uma solução curta, correta e simples que substitui dezenas de linhas complexas. Outro pode gerar centenas de linhas que precisam ser removidas depois.

Para esta apresentação, usaremos uma **definição operacional proposta pelo grupo**, não uma fórmula universal: **produtividade é concluir trabalho de software útil e correto, com esforço e tempo adequados, sem transferir custos excessivos para testes, revisão, manutenção e produção.**

Isso distingue quatro perguntas:

| Pergunta | Exemplo de indicador | Risco de interpretar isoladamente |
|---|---|---|
| **Foi concluído?** | Requisitos e testes de aceitação satisfeitos | Uma solução pode cumprir testes incompletos |
| **Quanto custou?** | Tempo até conclusão, incluindo validação | Tarefas não equivalentes distorcem comparação |
| **Qual foi a qualidade?** | Defeitos, regressões e retrabalho | Bugs podem aparecer após a entrega |
| **Como flui a entrega?** | Lead time, frequência e estabilidade de deploy | Indicadores de equipe não medem um indivíduo isolado |

A satisfação do desenvolvedor merece ser coletada como **indicador adicional de experiência**, mas não deve substituir nenhuma dessas perguntas.

## 2. Como os estudos do Grupo 1 mediram coisas diferentes?

### METR (2025): duração de tarefas reais

O estudo atribuiu aleatoriamente **246 tarefas** realizadas por **16 desenvolvedores** às condições IA permitida e IA não permitida. Sua métrica central foi **tempo de execução**, e a estimativa foi de **19% mais tempo** com IA permitida.

**Ponto forte:** permite investigar o efeito causal naquele cenário de trabalho real.  
**Limite:** tempo de tarefa não é sinônimo de todos os aspectos da produtividade ou do sucesso de uma organização.

### Peng et al. (2023): tempo em tarefa padronizada

Desenvolvedores implementaram um servidor HTTP em JavaScript com e sem Copilot. A estimativa indicou conclusão **55,8% mais rápida** com Copilot.  
**Ponto forte:** tarefa definida e comparação controlada.  
**Limite:** tarefas padronizadas não representam necessariamente manutenção em um sistema grande.

### Ziegler et al. (2022): percepção + telemetria da ferramenta

O estudo relacionou respostas de usuários do Copilot com registros de sugestões exibidas, aceitas e mantidas. A **taxa de aceitação** foi o melhor indicador estudado para prever **produtividade percebida** (correlação com índice agregado **ρ = 0,24**).  
**Ponto forte:** conecta percepção a comportamento observável na ferramenta.  
**Limite:** não prova conclusão de tarefa mais rápida nem o valor entregue.

**Lição conjunta:** os três trabalhos usam medidas diferentes. Não devemos apresentar seus resultados como se fossem a mesma «taxa de produtividade com IA».

## 3. O DORA 2024 e 2025: a diferença entre escrever e entregar software

O DORA estuda desempenho de desenvolvimento e entrega de software. Ele aparece **expressamente na lista de complementos do Grupo 1**.

### DORA 2024 — ganhos locais podem coexistir com problemas na entrega

O relatório de 2024 observou **associações** entre maior uso de IA e ganhos em aspectos como produtividade individual, satisfação e fluxo de trabalho, mas também associações desfavoráveis com **throughput** e **estabilidade de entrega**.

No anúncio oficial do relatório, um **aumento de 25% na adoção de IA** apareceu associado a uma **queda estimada de 1,5% no throughput de entrega** e de **7,2% na estabilidade de entrega**. A divulgação também menciona melhorias em qualidade de documentação, código e velocidade de revisão.

**Cuidado metodológico:** são associações de pesquisa organizacional, **não** resultados de distribuição aleatória que provem que IA *causou* cada porcentagem. As porcentagens não podem ser diretamente comparadas ao +19% da METR porque medem variáveis diferentes.

### DORA 2025 — IA como amplificadora do sistema de trabalho

O relatório de 2025 caracteriza a IA como um **amplificador**: os ganhos dependem também da qualidade dos processos, testes, coordenação, infraestrutura e práticas organizacionais já presentes. A tese relevante para este tema é que **melhorar a escrita de código não garante melhorar o sistema inteiro de entrega**.

Não é necessário afirmar uma porcentagem específica do DORA 2025 para sustentar esse argumento.

## 4. Indicadores que podemos usar na prática

### Indicadores diretamente ligados à tarefa

| Indicador | Definição prática | Para que serve | Limitação |
|---|---|---|---|
| **Tempo total até a tarefa pronta** | Do começo do trabalho à conclusão dos critérios definidos | Verifica se a IA poupou tempo no processo completo | Depende de critérios e tarefas comparáveis |
| **Taxa de tarefas aprovadas** | Tarefas que cumprem requisitos/testes sobre tarefas avaliadas | Evita premiar soluções incompletas | Testes podem não cobrir tudo |
| **Retrabalho** | Tempo gasto ajustando ou corrigindo o resultado | Detecta economia aparente seguida de custo oculto | Nem todo refinamento é defeito |
| **Defeitos/regressões** | Problemas encontrados durante e após a entrega | Acompanha qualidade | Defeitos podem aparecer tardiamente |
| **Percepção do desenvolvedor** | Questionário curto antes/depois | Mede experiência e confiança | Não mede diretamente velocidade |

### Indicadores DORA de entrega (nível de equipe/sistema)

A documentação oficial atual reúne os indicadores de desempenho da entrega. Em apresentações e relatórios mais antigos aparecem **quatro métricas clássicas**; a documentação atual destaca **cinco indicadores**. Para evitar confusão, aqui estão os cinco e a função de cada um.

| Métrica DORA | O que mede em linguagem simples | O que observar ao adotar IA |
|---|---|---|
| **Change lead time** | Tempo da alteração de código até sua entrada em produção | O caminho completo ficou mais curto? |
| **Deployment frequency** | Frequência com que mudanças são colocadas em produção | A equipe consegue entregar com regularidade? |
| **Failed deployment recovery time** | Tempo para recuperar uma implantação malsucedida | A operação consegue se recuperar? |
| **Change fail rate** | Fração das implantações que geram falhas exigindo intervenção | A instabilidade aumentou? |
| **Deployment rework rate** | Proporção de implantações com retrabalho não planejado para tratar incidentes | O volume de correções emergenciais cresceu? |

**Não use DORA para criar um ranking individual de programadores.** Seu foco é o comportamento da entrega de uma equipe/sistema. Esses indicadores ajudam a verificar se um ganho no editor de código se converteu em resultado operacional.

Fonte complementar oficial do DORA para definição dos indicadores: <https://dora.dev/guides/dora-metrics/>.

## 5. Um protocolo simples para comparar com e sem IA

**Esta seção é uma proposta didática do grupo, construída com base nas questões que os estudos levantam. Não é um protocolo validado como padrão científico universal.**

1. **Definir a tarefa antes de começar:** descrever o problema, os requisitos, os testes e o que conta como «pronto».
2. **Selecionar tarefas comparáveis:** tentar equilibrar linguagem, dificuldade, tamanho, familiaridade com o sistema e experiência. Quando viável, distribuir tarefas aleatoriamente entre condições com e sem IA.
3. **Cronometrar o processo inteiro:** compreender, solicitar à IA, esperar, programar, testar, revisar, corrigir e finalizar. Não encerrar o cronômetro na primeira resposta da ferramenta.
4. **Registrar qualidade:** testes, defeitos, revisão e retrabalho. As duas condições devem obedecer aos mesmos critérios.
5. **Registrar percepção separadamente:** perguntar «Você se sentiu mais rápido?» e comparar essa resposta com o tempo observado.
6. **Observar efeitos na entrega:** em períodos maiores, acompanhar os indicadores DORA da equipe e levar em conta alterações simultâneas de processos e ferramentas.
7. **Interpretar com cuidado:** observar tamanho de amostra, variabilidade, efeito de aprendizagem e outros fatores que dificultem atribuir a mudança somente à IA.

### Exemplo para explicar o método em sala (100% fictício)

| Etapa | Sem IA | Com IA |
|---|---:|---:|
| Entender + produzir primeira versão | 50 min | 25 min |
| Revisar + testar + corrigir | 30 min | 65 min |
| **Tempo até concluir** | **80 min** | **90 min** |
| Resultado | Aprovado | Aprovado |

**Leitura correta:** a primeira versão com IA foi produzida em menos tempo, mas a tarefa terminada demorou mais. **Estes minutos são exemplos inventados**, sem relação com medições da METR, Peng ou DORA.

## 6. Erros de avaliação que você deve evitar

- **Linhas de código:** quantidade maior pode ser duplicação, verbosidade ou complexidade extra. Apagar código desnecessário pode ser um ganho real.
- **Número de commits ou pull requests:** várias mudanças pequenas não valem automaticamente mais do que uma correção crítica.
- **Taxa de aceitação do Copilot:** no estudo de Ziegler ela foi útil para entender **percepção**, não para demonstrar valor entregue.
- **Tempo até a primeira sugestão:** não inclui revisão, integração, testes e correção.
- **Pesquisa de satisfação isolada:** mede opinião, não demonstra que o trabalho foi concluído antes.
- **Comparar tarefas incomparáveis:** uma pequena alteração de interface e um bug raro em sistema legado podem demandar esforços diferentes.
- **Confundir correlação com causa:** dados de adoção de IA e entrega variam também com processos e equipes. Não basta observar que dois indicadores mudaram juntos.

## 7. Conclusão do Tema 4

**O melhor critério é medir o trabalho completo.** Para uma comparação pequena, medir tempo até tarefa correta, testes, retrabalho e percepção já permite uma discussão mais confiável. Em empresas, observar o processo de entrega com indicadores DORA acrescenta uma visão de equipe e operação.

A principal lição dos estudos do Grupo 1 é que **a métrica escolhida muda a história**: o Copilot pode aumentar a aceitação de sugestões e a sensação de produtividade (Ziegler), acelerar uma tarefa padronizada (Peng) ou não acelerar manutenção real em repositórios maduros (METR); o DORA mostra que ganhos individuais não se traduzem automaticamente em resultados de entrega.

**Frase final para o slide:** «Não basta medir quanto código a IA escreve; devemos medir o que a equipe consegue entregar corretamente».

## 8. Referências — Grupo 1 + documentação da instituição já indicada

1. BECKER, J.; RUSH, N.; BARNES, E.; REIN, D. **Measuring the Impact of Early-2025 AI on Experienced Open-Source Developer Productivity**. METR, 2025. <https://arxiv.org/abs/2507.09089>.
2. PENG, S. et al. **The Impact of AI on Developer Productivity: Evidence from GitHub Copilot**. 2023. <https://arxiv.org/abs/2302.06590>.
3. ZIEGLER, A. et al. **Productivity Assessment of Neural Code Completion**. MAPS, 2022. <https://arxiv.org/abs/2205.06537>.
4. DORA. **Accelerate State of DevOps Report 2024**. <https://dora.dev/research/2024/dora-report/>.
5. DORA. **State of AI-assisted Software Development 2025**. <https://dora.dev/research/2025/dora-report/>.
6. GOOGLE CLOUD / DORA. **Anúncio do relatório DORA 2024** (fonte oficial dos percentuais citados). <https://cloud.google.com/blog/products/devops-sre/announcing-the-2024-dora-report>.
7. DORA. **Software Delivery Performance Metrics** (documentação oficial complementar para as definições). <https://dora.dev/guides/dora-metrics/>.