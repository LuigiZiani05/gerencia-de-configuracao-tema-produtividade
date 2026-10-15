# Outros estudos, resultados opostos — e quem ganha com a IA

> **Autor:** Eduardo May · **Tema 1:** Produtividade – Gerência de Configuração (UCS)

## Ideia central

O estudo da METR (BECKER et al., 2025) é um experimento controlado bem desenhado, mas não é o único. Outros estudos com o mesmo tipo de método chegaram a resultados opostos. Isso não significa que algum deles esteja errado: cada um mediu uma situação diferente — outro perfil de desenvolvedor, outro tipo de tarefa, outra ferramenta e outra métrica.

Por isso, a pergunta *"a IA torna os desenvolvedores melhores?"* não tem uma resposta única. **Depende de quem usa, em que código, com que ferramenta e de como se mede.**

---

## 1. Outros estudos, resultados opostos: o que o METR não mostra

### 1.1 O método em comum: experimento com sorteio

Os três estudos comparados aqui são **ensaios controlados randomizados** (RCT, *randomized controlled trial*). A lógica é a mesma de um teste de medicamento: um sorteio decide quem (ou qual tarefa) usa IA e quem não usa. Como a divisão é aleatória, a diferença entre os grupos pode ser atribuída à IA, e não ao fato de um grupo ter programadores melhores. É um tipo de evidência mais confiável do que pesquisas de opinião ou estudos de caso divulgados por fornecedores.

O sorteio, porém, foi feito de formas diferentes:

- **METR:** sorteio por **tarefa** — o mesmo desenvolvedor fez tarefas com e sem IA.
- **Google:** sorteio por **pessoa** — todos fizeram a mesma tarefa, metade com IA.
- **Microsoft/Accenture:** sorteio de **quem recebia acesso** ao Copilot, no trabalho do dia a dia.

### 1.2 Os três estudos lado a lado

| | METR (BECKER et al., 2025) | Google (PARADIS et al., 2025) | Microsoft/Accenture (CUI et al., 2025) |
|---|---|---|---|
| **Participantes** | 16 desenvolvedores experientes de open source | 96 engenheiros do Google | 4.867 desenvolvedores em 3 empresas |
| **Contexto** | 246 tarefas reais em repositórios que eles mesmos mantinham | uma tarefa corporativa complexa, no ambiente interno do Google | trabalho real do dia a dia |
| **Ferramenta** | Cursor Pro com Claude 3.5/3.7 Sonnet | 3 recursos internos: autocompletar, *Smart Paste* e geração de código a partir de linguagem natural | GitHub Copilot (autocompletar) |
| **O que mediu** | tempo por tarefa | tempo na tarefa | pull requests concluídos por semana |
| **Resultado com IA** | **+19% de tempo** (intervalo de confiança: +2% a +39%) | **cerca de 21% menos tempo** (intervalo de confiança amplo) | **+26,08% de pull requests** (erro-padrão: 10,3%) |

Detalhes que importam:

- No METR, antes do experimento os desenvolvedores esperavam reduzir o tempo em 24%; depois, acreditavam ter reduzido em 20%. O tempo medido aumentou 19% (BECKER et al., 2025).
- No estudo da Microsoft/Accenture, além dos pull requests, os commits semanais subiram 13,55% e as compilações (*builds*) 38,38% (CUI et al., 2025).

### 1.3 Por que os resultados divergem

Os três estudos responderam a perguntas diferentes:

| Dimensão | METR | Google | Microsoft/Accenture |
|---|---|---|---|
| **Quem** | veteranos, com anos no próprio repositório | engenheiros de uma mesma empresa | população ampla, incluindo muitos recém-contratados |
| **Que código** | projetos grandes e maduros, conhecidos pelo desenvolvedor | uma tarefa montada para o experimento | código corporativo do dia a dia |
| **Que ferramenta** | editor com chat/agente (Cursor) | recursos internos do Google | autocompletar (Copilot) |
| **Que régua** | tempo | tempo | **quantidade** de pull requests |

O último ponto merece atenção: o estudo com resultado mais positivo nem mede tempo. Contar pull requests mede volume, não qualidade nem valor entregue — o mesmo problema discutido no modelo SPACE (FORSGREN et al., 2021) e na parte do grupo sobre como medir produtividade.

**Conclusão da seção:** os números não se contradizem; eles descrevem situações diferentes. Comparar "−19%" com "+26%" sem olhar quem, onde, com quê e como foi medido é comparar respostas a perguntas diferentes.

### 1.4 Limitações de cada estudo

Para não substituir um recorte enviesado por outro, vale registrar os limites dos três.

**METR**
- Amostra pequena (16 pessoas) e intervalo de confiança largo (+2% a +39%).
- 56% dos participantes nunca tinham usado o Cursor antes do estudo (WILLISON, 2025).
- Ferramentas do início de 2025. A própria METR passou a tratar o resultado como histórico.
- **Tentativa de repetição (METR, 2026):** a METR iniciou um novo experimento em agosto de 2025, com mais desenvolvedores e ferramentas mais recentes, mas considerou os dados não confiáveis por três motivos:
  1. muitos desenvolvedores se recusaram a participar porque não queriam trabalhar sem IA — o que tende a **subestimar** o ganho;
  2. o pagamento caiu de US$ 150/h para US$ 50/h, alterando o perfil de quem aceitou participar;
  3. a medição de tempo deixou de ser confiável para quem usa vários agentes de IA ao mesmo tempo.
- Mesmo assim, os dados parciais apontam que os participantes do estudo original levaram cerca de 18% **menos** tempo com IA (intervalo de −38% a +9%), e os novos participantes cerca de 4% menos (intervalo de −15% a +9%) (CAPITAL & COMPUTE, 2026). A METR afirma que os desenvolvedores provavelmente ganham mais velocidade em 2026 do que em 2025, mas que seus dados são evidência muito fraca do tamanho desse aumento.
- O fato de o experimento ter falhado porque desenvolvedores não aceitam mais trabalhar sem IA é, por si só, um dado sobre a adoção dessas ferramentas.

**Google**
- Uma única tarefa, em ambiente de experimento, com ferramentas internas da própria empresa.
- Intervalo de confiança amplo. Os próprios autores alertam que o tamanho do efeito pode não valer para outros contextos, outras ferramentas ou outras épocas (PARADIS et al., 2025).

**Microsoft/Accenture**
- Mede quantidade (pull requests), não qualidade.
- Os experimentos foram conduzidos pelas próprias empresas, e parte dos autores é da Microsoft — dona do GitHub e do Copilot.
- Nos três experimentos, entre 30% e 40% dos desenvolvedores optaram por não adotar o Copilot (DX, 2024).

A METR, por outro lado, é uma organização de pesquisa sem fins lucrativos, sem produto de IA para vender.

---

## 2. Quem ganha e quem perde com IA

Cruzando os estudos, aparece um padrão: **a IA ajuda mais quem sabe menos e quando a tarefa é nova; ajuda menos — ou atrapalha — quem já domina o código.**

### 2.1 Tarefa nova e isolada: o cenário mais favorável

No experimento de Peng et al. (2023), 95 programadores tiveram que implementar um servidor HTTP em JavaScript. O grupo com GitHub Copilot terminou **55,8% mais rápido**.

É o cenário mais favorável para a IA: não existe código prévio, então ela não precisa entender convenções, histórico ou restrições de um projeto. Por outro lado, o experimento mede apenas o tempo para terminar — qualidade e manutenção do código ao longo do tempo ficaram fora da medição.

### 2.2 Experiência e tempo de casa

No estudo da Microsoft/Accenture (CUI et al., 2025):

| Grupo | Aumento de produção com Copilot | Fonte |
|---|---|---|
| Recém-contratados | +27% a +39% | MIT SLOAN (2024) |
| Com mais tempo de empresa | +8% a +13% | MIT SLOAN (2024) |
| Cargos júnior | +21% a +40% | DX (2024) |
| Cargos sênior | +7% a +16% | DX (2024) |

Os menos experientes também adotaram mais a ferramenta. Explicações possíveis:

- a IA supre conhecimento que o iniciante ainda não tem de cabeça (sintaxe, bibliotecas, convenções);
- desenvolvedores com mais tempo de casa tenderam a abandonar a ferramenta mais cedo (RDEL, 2024).

**Contraponto:** o padrão não é universal. No estudo do Google, nem a senioridade nem o uso prévio de IA alteraram significativamente o ganho; o que fez diferença foram as horas diárias dedicadas a programar — quem programa mais horas por dia foi mais rápido com IA (PARADIS et al., 2025).

### 2.3 Conhecer bem o código: quando a IA atrapalha

No METR, os participantes tinham em média cerca de 5 anos de experiência nos repositórios em que trabalharam (BECKER et al., 2025). Nesse cenário, o desenvolvedor conhece o código melhor do que a IA: convenções, requisitos de compatibilidade, decisões históricas.

O efeito é que o tempo economizado escrevendo código é gasto lendo, verificando, corrigindo e integrando o que a IA sugeriu. Participantes relataram, por exemplo, que a IA fazia alterações em partes não relacionadas do código ou escolhia o lugar errado para as mudanças.

Esse é o ponto de contato com a discussão sobre **sistemas legados** (parte do Luigi): código grande, antigo e cheio de contexto implícito é justamente o cenário em que o resultado do METR tende a se repetir.

### 2.4 Domínio da ferramenta

- 56% dos participantes do METR nunca tinham usado o Cursor. O único participante com mais de 50 horas de uso prévio da ferramenta foi mais rápido com IA (WILLISON, 2025).
- Para Willison (2025), o estudo mostra principalmente que a curva de aprendizado do desenvolvimento assistido por IA é maior do que se imagina.
- **Contra-argumento:** um dos autores do estudo respondeu que mais de 90% dos participantes já tinham experiência razoável com LLMs (WILLISON, 2025). Uma análise publicada no LessWrong aponta ainda que os participantes não melhoraram ao longo das primeiras 30 a 50 horas de uso e que 14 dos 16 se avaliaram, ao final, como usuários médios ou acima da média do Cursor (LESSWRONG, 2025).

**Conclusão:** o caso do participante com mais de 50 horas é um indício de que o domínio da ferramenta importa, mas é um único caso — não é prova.

### 2.5 Síntese

| Situação | Efeito observado | Fonte |
|---|---|---|
| Tarefa nova, sem código existente | 55,8% mais rápido | Peng et al. (2023) |
| Recém-contratados | +27% a +39% de produção | Cui et al. (2025) |
| Tarefa corporativa padronizada | cerca de 21% menos tempo | Paradis et al. (2025) |
| Desenvolvedores com mais tempo de empresa | +8% a +13% de produção | Cui et al. (2025) |
| Veteranos no próprio código, ferramenta pouco conhecida | +19% de tempo | Becker et al. (2025) |

Uma analogia útil é o GPS: para quem não conhece a cidade, ele resolve; para quem mora lá há dez anos, às vezes sugere um caminho pior e o motorista perde tempo discordando dele.

---

## 3. Posição

A evidência disponível não sustenta nem "a IA deixa todo desenvolvedor mais produtivo" nem "a IA deixa desenvolvedores experientes mais lentos". O que ela sustenta é:

1. **O ganho depende do contexto.** É maior em tarefas novas e para quem tem menos experiência ou menos tempo de empresa; é menor, ou negativo, para veteranos trabalhando em código que conhecem bem.
2. **A métrica muda a resposta.** Tempo por tarefa e quantidade de pull requests medem coisas diferentes, e nenhuma delas mede qualidade sozinha.
3. **Os números envelhecem rápido.** O resultado do METR de 2025 já é tratado como histórico pela própria METR, e a tentativa de atualizá-lo em 2026 não produziu um número confiável.

Em uma frase: **depende de quem usa, em que código, com que ferramenta e de como se mede.**

---

## Referências

BECKER, J.; RUSH, N.; BARNES, E.; REIN, D. **Measuring the Impact of Early-2025 AI on Experienced Open-Source Developer Productivity.** METR, 2025. Disponível em: https://arxiv.org/abs/2507.09089

METR. **We are Changing our Developer Productivity Experiment Design.** 24 fev. 2026. Disponível em: https://arxiv.org/abs/2507.09089

PARADIS, E. et al. **How much does AI impact development speed? An enterprise-based randomized controlled trial.** ICSE-SEIP, 2025. Disponível em: https://arxiv.org/abs/2410.12944

CUI, Z. K.; DEMIRER, M.; JAFFE, S.; MUSOLFF, L.; PENG, S.; SALZ, T. **The Effects of Generative AI on High-Skilled Work: Evidence from Three Field Experiments with Software Developers.** Management Science, 2025. DOI: https://doi.org/10.1287/mnsc.2025.00535

PENG, S.; KALLIAMVAKOU, E.; CIHON, P.; DEMIRER, M. **The Impact of AI on Developer Productivity: Evidence from GitHub Copilot.** 2023. Disponível em: https://arxiv.org/abs/2302.06590

FORSGREN, N.; STOREY, M.-A.; MADDILA, C.; ZIMMERMANN, T.; HOUCK, B.; BUTLER, J. **The SPACE of Developer Productivity.** ACM Queue, v. 19, n. 1, 2021. Disponível em: https://queue.acm.org/detail.cfm?id=3454124

WILLISON, S. **AI open source productivity.** 12 jul. 2025. Disponível em: https://simonwillison.net/2025/Jul/12/ai-open-source-productivity/

MIT SLOAN. **How generative AI affects highly skilled workers.** Ideas Made to Matter, 2024. Disponível em: https://mitsloan.mit.edu/ideas-made-to-matter/how-generative-ai-affects-highly-skilled-workers

DX. **Copilot's impact on productivity: Results from three experiments.** 2024. Disponível em: https://newsletter.getdx.com/p/copilot-impact-on-productivity

RDEL. **#59: How does Copilot impact the day-to-day software engineering experience?** 2024. Disponível em: https://rdel.substack.com/p/rdel-59-how-does-copilot-impact-the

LESSWRONG. **On METR's AI Coding RCT.** 2025. Disponível em: https://www.lesswrong.com/posts/m2QeMwD7mGKH6vDe2/on-metr-s-ai-coding-rct

CAPITAL & COMPUTE. **AI Programming in 2026: Tools, Techniques, Evidence.** 2026. Disponível em: https://capitalandcompute.net/blog/state-of-ai-programming-2026/
