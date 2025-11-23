# Plano de Experimento – Scoping e Planejamento

### 1.1 Título do experimento
Sustentabilidade no Desenvolvimento de Software: Uma Comparação entre Duplicação de Código e Reutilização por Abstração

## 1.2 ID / código
 ES-SUST-2025-01

### 1.3 Versão do documento e histórico de revisão
1.0 - Versão inicial do plano de experimento.

### 1.4 Datas (criação, última atualização)
Criado em: 23 de novembro de 2025
Última atualização: 23 de novembro de 2025

### 1.5 Autores (nome, área, contato)
Fernando Ibrahim — fernandofibrahim@gmail.com

### 1.6 Responsável principal (PI / dono do experimento)
Fernando Ibrahim — responsável pelo desenho conceitual, hipóteses, execução e síntese dos resultados.

### 1.7 Projeto / produto / iniciativa relacionada
Este experimento está relacionado à iniciativa de pesquisa acadêmica sobre boas práticas de design de software, incluindo decisões arquiteturais que impactam manutenibilidade, custo cognitivo e sustentabilidade de longo prazo.



### 2.1 Descrição do problema / oportunidade
Este estudo investiga um dilema recorrente no desenvolvimento de software orientado a objetos: o que é mais sustentável no longo prazo, duplicar código ou reutilizá-lo por meio de abstrações? De um lado, existe a crença consolidada de que duplicação de código é sempre um “mau cheiro”, associada a inconsistências, aumento de bugs e retrabalho. De outro, abstrações são frequentemente tratadas como a solução ideal, pois promovem reaproveitamento e redução aparente de redundância. Na prática, porém, muitos esforços de abstração introduzidos apenas para eliminar duplicações acabam gerando acoplamento excessivo, interfaces genéricas demais, hierarquias profundas de classes e estruturas difíceis de evoluir. Isso é especialmente crítico em contextos ágeis, em que diferentes módulos, serviços e camadas evoluem em ritmos distintos. Em contrapartida, pequenas duplicações locais, bem delimitadas em classes ou contextos específicos, podem tornar o sistema mais previsível, legível e independente. A oportunidade deste trabalho é justamente analisar, com base em evidências e reflexão teórica, em quais cenários a duplicação controlada pode ser mais sustentável do que abstrações generalizadas, e quando o investimento em abstrações realmente se justifica, considerando a manutenibilidade, o custo cognitivo e a evolução contínua de sistemas orientados a objetos.


### 2.2 Contexto organizacional e técnico

O estudo se insere no contexto de desenvolvimento de software orientado a objetos em projetos de código aberto (OSS), mantidos em repositórios públicos como GitHub ou GitLab, nos quais código, histórico de commits, discussões técnicas e decisões de design são transparentes e construídos por comunidades distribuídas de mantenedores e contribuidores. Esses projetos costumam usar frameworks orientados a objetos, padrões de projeto, automação de build, testes, integração contínua e fluxos de contribuição baseados em pull requests e revisão de código, registrando em issues e documentos o racional por trás de refatorações, novas abstrações ou duplicações locais. Esse ambiente oferece um “laboratório natural” para observar como desenvolvedores, na prática, negociam o trade-off entre duplicação e reutilização e como essas decisões influenciam a sustentabilidade técnica e a evolução histórica dos sistemas ao longo do tempo.

### 2.3 Trabalhos e evidências prévias (internos e externos)
- Acoplamento e dificuldade de evolução [Ratzinger et al.](https://ar5iv.labs.arxiv.org/html/2502.04073)
- Duplicação de código e manutenibilidade [Eman Abdullah AlOmar.](https://ar5iv.labs.arxiv.org/html/2502.04073)
- CK Metrics: [Chidamber & Kemerer, 1994](https://ieeexplore.ieee.org/document/1191795)


### 2.4 Referencial teórico e empírico essencial
Teoria de métricas de software orientadas a objetos: parte do princípio de que é possível medir propriedades estruturais do código (como acoplamento, coesão, complexidade e herança) e relacioná-las a atributos de qualidade como manutenibilidade e propensão a defeitos, seguindo a linha de CK Metrics e modelos posteriores.

Conceitos de modularidade, acoplamento e coesão: a partir de Parnas e da engenharia de software clássica, o experimento se apoia na ideia de que módulos fracamente acoplados e altamente coesos são mais fáceis de entender, testar e modificar, servindo como base para avaliar o impacto de abstrações e duplicações na evolução do sistema.

Princípios de design OO (DRY, SRP, encapsulamento): princípios como Don’t Repeat Yourself e Responsabilidade Única estruturam a discussão sobre o papel da duplicação e da abstração. Abstrações bem definidas e encapsuladas tendem a concentrar conhecimento em pontos únicos, enquanto violações de DRY e classes com múltiplas responsabilidades indicam problemas de design e maior risco de dívida técnica.

Duplicação de código e code clones: a literatura de code clones fornece o embasamento teórico para tratar duplicação como fenômeno mensurável e recorrente em sistemas OO, permitindo discutir quando a eliminação de clones por abstração melhora a manutenibilidade e quando a duplicação local pode ser um compromisso aceitável ou até desejável.

Sustentabilidade técnica e dívida técnica em OSS: o conceito de sustentabilidade técnica integra manutenibilidade, simplicidade, clareza e custo de evolução ao longo do tempo. Estudos sobre dívida técnica em projetos OSS mostram como decisões de design (incluindo abstrações excessivas ou duplicação descontrolada) se acumulam e impactam a evolução histórica do sistema, servindo como base empírica para formular e testar as hipóteses deste experimento.
