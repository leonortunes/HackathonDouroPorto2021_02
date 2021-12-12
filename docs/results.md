# Resultados

## Aquisição de dados

Um grande desafio em relação à necessidade de dados para irrigação de precisão é a falta de resolução ao nível do campo e dados de alta precisão. Os sensores in-situ existentes no mercado são geralmente despendiosos ou, pelo menos, não suficientemente de baixo custo para permitir uma ampla utilização. Os sensores de campo, em diversas situações, também poderão precisar ser instalados e removidos antes e depois da estação de crescimento, resultando em custos extras de mão-de-obra. No entanto, sensores in situ fornecem, geralmente, medições de alta qualidade, essas medições são de um único ponto e, portanto, muitas vezes têm limitações na captura da heterogeneidade espacial de um campo inteiro.

Existem redes de estações meteorológicas, mas estas são, geralmente, colocadas na paisagem natural afastadas dos terrenos agrícolas. 

Em primeiro lugar, o desenvolvimento contínuo de um sensor de humidade do solo é necessário para reduzir o custo enquanto se obtém um desempenho robusto. Em segundo lugar, mais medições in-situ com sensores de baixo custo podem ser combinadas para preencher a lacuna de dados crítica para situações essenciais e condições ambientais. Por exemplo, medições de LAI (Leaf Area Index) in-situ, em combinação com outras variáveis ambientais, como temperatura e humidade do ar, podem ser adquiridas com sensores de baixo custo; essas medições podem fornecer restrições significativas para melhorar as estimativas de ET para programação da irrigação.

Além disso, os avanços recentes na electrónica (microcomputadores e microcontroladores) melhoraram a capacidade de integrar sensores de baixo custo e fornecer uma ampla
solução para monitorarizar o crescimento da cultura. Por fim, novas tecnologias, como redes 5G, Internet das Coisas (IoT), [dispositivos de comunicação de longo alcance (Low-Power Wide Area Networks, LPWAN, como o protocolo LoRaWAN)](https://www.mdpi.com/2079-9292/9/6/987) e edge computing (processamento no nó final), podem acelerar ainda mais o desenvolvimento de redes de sensores sem fios (WSN, Wireless Sensors Networks), o que pode tornar os sensores mais acecívesi e mais fácil de fornecer dados in-situ escalonáveis para irrigação de precisão.

## Modelação e análise

Uma questão fundamental sobre a irrigação de precisão é "o que é o stress hídrico da planta e como quantificá-lo?". Responder a esta questão requer que consideremos completamente o continuum solo-planta-atmosfera (SPAC, Soil-Plant-Atmosphere Continuum). Só depois desta pergunta estar respondida, é que poderão ser desenvolvidos métodos ideais em torno dos conceitos corretos.

### Quantificação do stress hídrico

‘Stress hídrico da planta’ é um conceito crítico para indicar o estado de falta de água nas plantas, com base no qual podemos criar regras de disparo de irrigação. Existem várias definições de "stress hídrico da planta", por exemplo, com base na [humidade do solo](https://hackathondouroporto2021-01.readthedocs.io/) e/ou nas condições da planta, incluindo temperatura da vegetação e/ou potencial hídrico folear e/ou fluxo de seiva.

Deste modo, poderemos obter o stress hídrico utizando conceitos baseados no solo, na planta e no clima. Métricas baseadas no solo têm em conta a água disponível na zona das raízes, relacionada com a absorção de água pelas raízes, para indicar o stress hídrico da planta. É importante notar que essas métricas baseadas no solo refletem apenas o abastecimento de água e não consideram as necessidades/gastos de água pela atmosférica. 

Nos métodos baseados na planta, o mais utilizado é o potencial hídrico foliar. O potencial hídrico da folha, uma medida mais rigorosa do stress hídrico da planta com base na hidráulica da planta, pode indicar o stress hídrico interno da planta diretamente, mas é relativamente complicado e trabalhoso para medir. As medições tradicionais do potencial da água na folha por meio de câmaras de pressão (câmara de Scholander) são confiáveis, mas requerem uma amostragem de folhas destrutiva, podem ser demoradas e trabalhosas, sendo, por esse motivo, bastante dispendiosas.

A nossa equipa, assim como outros autores, interpreta o 'stress hídrico da planta' como uma contribuição conjunta do teor de água do solo (ou seja, humidade do solo na zona da raiz) e necessidade de água atmosférica (ou seja, VPD - Vapour Pressure Deficit), mediada pela regulação fisiológica da planta. Tanto um valor baixo do teor de água no solo quanto um valor alto de VPD podem levar ao stress hídrico da planta, e diferentes plantas podem ter diferentes respostas fisiológicas e estratégias de uso de água. Deste modo, o stress hídrico da planta deve ser definido e quantificado holisticamente com base na interação entre o fornecimento de água ao solo, a solicitação de água pela atmosférica e os regulamentos fisiológicos da planta, ou seja, o conceito SPAC (Soil-Plant-Atmosphere Continuum), para programação de irrigação. Assim sendo, será importante conceber um sistema onde se possa obter dados que consubstanciem estas três definições baseadas na transpiração, hidráulica da planta e condutância estomática. 

## Apoio à tomada de decisão

A estrutura do modelo do sistema proposto neste trabalho é baseada na proposta de [Niklaus Lehmann et al. (2013)](https://www.sciencedirect.com/science/article/pii/S0308521X13000024). Consideramos esse modelo pois utiliza, em simultâneo, modelos de crescimento da planta e económico para uma boa estratégia de irrigação. O modelo proposto utiliza um algoritmo genético (Machine Learning) que a cada itereção gera um conjunto de variáveis de decisão para cada individuo. Essas variáveis de decisão 'alimentam' o modelo de simulação de crescimento da cultura que é utizado para fornecer o rendimento da colheita. Dados climatéricos, da planta (ex. fluxo de seiva) e do solo, da rede de sensores IoT (rede de sensores de baixo custo) são necessários como dados de entrada no modelo de simulação de crescimwnto da planta. O rendimento da colheita é depois passado para o modelo de decisão econónico onde é calculado o equivalente de certeza do produtor (agricultor), isto é, a vairável alvo. Esta última informação realimenta o algoritmo genético. Este processo é repetido até a variável equivalente de certez convergir para um valor máximo. O equivalente de certeza considera os níveis de lucro médio e os riscos de produção, ou seja, a variabilidade do lucro, e pode ser interpretado como a recompensa garantida que um tomador de decisão avesso ao risco vê como igualmente desejável como níveis de recompensa mais elevados, mas mais incertos.

![Modelo](https://i.imgur.com/iAblwdL.png)

Um bloco importante neste sistema é o modelo de simulação de crescimento da cultura. Para este modelo baseamo-nos no modelo proposto por [Cladio Stöckle (2003)](https://www.sciencedirect.com/science/article/pii/S1161030102001090). O modelo utiliza dados de diversas fontes que poderão, mais uma vez, vir de uma rede de sensores sem fios (IoT baseada em LoRaWAN). Nesta abordagem, proposta por [Cladio Stöckle (2003)](https://www.sciencedirect.com/science/article/pii/S1161030102001090) é utilizada a equação de [Penman-Monteith](https://www.fao.org/3/x0490E/x0490e06.htm#:~:text=In%201948%2C%20Penman%20combined%20the,temperature%2C%20humidity%20and%20wind%20speed) para o cáculo da evapotranspiração de referência. 

![Cresimento da Biomassa](https://i.imgur.com/viVI9J9.png)

O modelo utiliza um conjunto de equações numéricas para determinar o cresciemnto da biomassa. No entanto, e numa primeira abordagem pode-se utilizar técnicas Machine Learning para determinar o crescimento potencial da biomassa dependente da transpiração, a relação entre a transpiração atual e a potencial, e o índice de stress de água. De referir que este último já é calculado utilizando técnicas de machine learning no [desafio 1](https://hackathondouroporto2021-01.readthedocs.io/).

![Crescimento da Biomassa com Machine Learning](https://i.imgur.com/3ITafLB.png)



[![CC BY 4.0](https://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)
