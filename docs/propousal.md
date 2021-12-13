# Proposta

Com vista ao desenvolvimento de um sistema melhorado de apoio à decisão para a irrigação de precisão, será necessário ter em conta a disponibilidade e escalabilidade dos dados e a quantificação do stress hídrico da planta. Tendo em conta este desafios e oportunidades, o sistema de suporte à decisão de irrigação de precisão proposto inclui três componentes: 1) aquisição de dados; 2) modelação e análise; e 3) apoio à tomada de decisão. Esse sistema deverá ser escalável, econonómico, fiável e de fácil utilização pelos produtores.

![Sistema Proposto](https://i.imgur.com/wrRUtmw.png)

A arquitectura proposta integra dados meteorológicos, dados da planta e dados do solo, obtendo um modelo de simulação de crescimento da planta (esse modelo conta com o valores do estado hídrico das plantas, obtido no [desafio 1](https://hackathondouroporto2021-01.readthedocs.io/)), de forma a, com recurso a modelos
previsionais, calcular automaticamente as dotações de rega óptimas. A arquitectura considera as reservas de água existentes, e eventualmente, a utilização de águas provenientes da adega ou de armazenamento de águas pluviais (estes cenários são considerados no módulo `Estratégia de Irrigação`). Da arquitectura faz parte um `Modelo Económico`que recebe diversos inputs relativos à produtividade e qualidade (`rendimento da colheita`), assim como, os gastos associados à rega. O sistema proposto recorre a um módulo de `Machine Learning` (algoritmo genético), de forma a que, a médio e longo prazo, como os dados do acumular de diversas campanhas, a componente económica é tida em conta
na aferição das dotações de rega (i.e. se um défice hídrico severo a moderado, em determinada exploração, não se refletir em perdas de produção, as dotações de rega não
serão calculadas tendo como objectivo o conforto hídrico da planta).


&nbsp;

*** 

&nbsp;

[![CC BY 4.0](https://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)

This work is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/)
