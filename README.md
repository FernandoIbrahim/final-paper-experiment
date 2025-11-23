# Plano de Experimento – Scoping e Planejamento
## 1. Identificação básica
### 1.1 Título do experimento
Sustentabilidade no Desenvolvimento de Software: Uma Comparação entre Duplicação de Código e Reutilização por Abstração

### 1.2 ID / código
 ES-SUST-2025-01

### 1.3 Versão do documento e histórico de revisão
1.0 - Versão inicial do plano de experimento.

### 1.4 Datas (criação, última atualização)
- Criado em: 23 de novembro de 2025
- Última atualização: 23 de novembro de 2025

### 1.5 Autores (nome, área, contato)
Fernando Ibrahim — fernandofibrahim@gmail.com

### 1.6 Responsável principal (PI / dono do experimento)
Fernando Ibrahim — responsável pelo desenho conceitual, hipóteses, execução e síntese dos resultados.

### 1.7 Projeto / produto / iniciativa relacionada
Este experimento está relacionado à iniciativa de pesquisa acadêmica sobre boas práticas de design de software, incluindo decisões arquiteturais que impactam manutenibilidade, custo cognitivo e sustentabilidade de longo prazo.

## 2. Contexto e problema

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

## 3. Objetivos e questões (Goal / Question / Metric)

### 3.1 Objetivo geral (Goal template)
O objetivo geral deste estudo, seguindo o template GQM, é analisar padrões de duplicação de código e reutilização por abstrações em sistemas de software orientados a objetos de código aberto, com o propósito de avaliar seu impacto na manutenibilidade, no histórico de mudanças e na longevidade do software, com respeito a indicadores estruturais como acoplamento, complexidade e ocorrência de clones, sob a perspectiva de pesquisadores e engenheiros de software interessados em boas práticas de design, no contexto de projetos OSS de médio e grande porte mantidos colaborativamente em repositórios públicos.

### 3.2 Objetivos específicos
- O1 – Caracterizar o cenário atual
Identificar e descrever o perfil de duplicação de código e de reutilização por abstrações em um conjunto de projetos OSS orientados a objetos (por exemplo, volume de clones, uso de classes abstratas, interfaces, hierarquias de herança e módulos reutilizáveis).
- O2 – Relacionar estrutura e manutenibilidade
Investigar a correlação entre níveis de duplicação/abstração e métricas estruturais de manutenibilidade, como acoplamento, complexidade de classes e coesão, buscando evidências de quais padrões tornam o código mais ou menos fácil de manter.
- O3 – Conectar padrões estruturais ao histórico de mudanças
Analisar como a presença de duplicação de código e de abstrações compartilhadas se reflete no histórico de mudanças dos projetos (frequência de modificações, arquivos frequentemente alterados em conjunto, hotspots de manutenção).
- O4 – Explorar impacto na longevidade do software
Avaliar em que medida diferentes combinações de duplicação e abstração parecem influenciar a longevidade e a evolução contínua dos projetos (por exemplo, sobrevivência de módulos, evolução de componentes centrais, acúmulo de débito técnico).
- O5 – Derivar recomendações práticas
Sintetizar, a partir dos resultados empíricos, recomendações para apoiar desenvolvedores e arquitetos na decisão entre manter duplicações locais ou introduzir novas abstrações, considerando manutenibilidade, histórico de mudanças e sustentabilidade de longo prazo.


### 3.3 Questões de pesquisa / de negócio

**O1 – Caracterizar o cenário atual**

Identificar e descrever o perfil de duplicação de código e de reutilização por abstrações em um conjunto de projetos OSS orientados a objetos.

Questões associadas:

- **Q1.1:** Qual é o nível de duplicação de código (proporção de clones, quantidade de grupos de clones) nos projetos analisados?  
- **Q1.2:** Quais mecanismos de abstração são mais utilizados (classes abstratas, interfaces, hierarquias de herança, módulos utilitários reutilizados) nesses projetos?  
- **Q1.3:** Como esses padrões de duplicação e abstração variam entre projetos de diferentes tamanhos, domínios e níveis de maturidade?


**O2 – Relacionar estrutura e manutenibilidade**

Investigar a correlação entre níveis de duplicação/abstração e métricas estruturais de manutenibilidade.

Questões associadas:

- **Q2.1:** Projetos com maior duplicação de código apresentam maior acoplamento entre módulos do que projetos com menos duplicação?  
- **Q2.2:** A presença de abstrações compartilhadas está associada a menor complexidade média de classes e métodos (por exemplo, menor WMC, menor complexidade ciclomática)?  
- **Q2.3:** Quais combinações de métricas estruturais (duplicação, abstração, acoplamento, coesão) estão mais fortemente associadas a melhores indicadores de manutenibilidade?

---

**O3 – Conectar padrões estruturais ao histórico de mudanças**

Analisar como duplicação e abstrações se refletem no histórico de mudanças dos projetos.

Questões associadas:

- **Q3.1:** Trechos de código duplicado tendem a aparecer com maior frequência em commits de correção ou evolução do que trechos não duplicados?  
- **Q3.2:** Arquivos que contêm abstrações centrais (classes base, interfaces, módulos compartilhados) aparecem com que frequência em commits que envolvem múltiplos módulos ao mesmo tempo?  
- **Q3.3:** Existem evidências de que clones de código estão associados a “hotspots” de manutenção, isto é, áreas do sistema com alta taxa de mudanças ao longo do tempo?

---

**O4 – Explorar impacto na longevidade do software**

Avaliar em que medida padrões de duplicação/abstração parecem influenciar longevidade e evolução contínua dos projetos.

Questões associadas:

- **Q4.1:** Projetos com menores níveis de duplicação de código e/ou com abstrações mais consolidadas apresentam maior longevidade em termos de tempo de atividade e continuidade de commits?  
- **Q4.2:** Módulos centrais que adotam abstrações bem definidas permanecem mais tempo estáveis (com menos reescritas completas) do que módulos com alto nível de duplicação?  
- **Q4.3:** Há indícios de que a redução de duplicação e de acoplamento ao longo da história do projeto esteja associada à sua capacidade de continuar evoluindo sem grandes reescritas (rewrites) ou abandonos?

---

**O5 – Derivar recomendações práticas**

Sintetizar recomendações para apoiar decisões entre manter duplicações locais ou introduzir abstrações.

Questões associadas:

- **Q5.1:** Em quais cenários observados (tipo de módulo, frequência de mudança, criticidade) a duplicação controlada se mostrou um compromisso mais vantajoso do que a criação de novas abstrações?  
- **Q5.2:** Existem limiares quantitativos (por exemplo, nível de duplicação, grau de acoplamento, número de ocorrências de um clone) a partir dos quais a refatoração em direção a uma abstração compartilhada passa a ser claramente recomendada?  
- **Q5.3:** Que diretrizes práticas podem ser propostas para que desenvolvedores e arquitetos decidam quando aceitar duplicação local e quando investir na criação ou melhoria de abstrações compartilhadas?

