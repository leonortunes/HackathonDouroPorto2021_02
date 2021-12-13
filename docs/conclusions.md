# Conclusões

Foi apresentada uma arquitectura de um sistema de apoio à decisão para o controlo de rega. Essa arquitectura permite a introdução de modelos desenvolvidos no [desafio 1](https://hackathondouroporto2021-01.readthedocs.io/) e todo o processo de controlo de rega terá uma ligação ao módulo `Rega`da aplicação desenvolvida no [desafio 3](https://hackathondouroporto2021-03.readthedocs.io/). Deste modo, este desafio incorpora na sua arquitectura os resultados dos desafios 1 e 3. 

A arquitectura foi, também, desenvolvida tendo em conta a possibilidade de se recorrer a sensores sem fios e de baixo custo (IoT, com transmissão sem fios via LoRaWAN[^1]) como, sensores de clima (temperatura, humidade do ar, pressão atmosférica, velocidade e direção do vento, entre outros), do solo (ex. sensores de baixo custo para o teor de água no solo) e da planta (ex. sensores de baixo custo para o fluxo de seiva), considerando, na sua amplitude, o conceito SPAC (soil-plant-atmosphere continuum).


[^1]: [Valente, A.; Silva, S.; Duarte, D.; Cabral Pinto, F.; Soares, S. Low-Cost LoRaWAN Node for Agro-Intelligence IoT. Electronics 2020, 9, 987. https://doi.org/10.3390/electronics9060987](https://www.mdpi.com/2079-9292/9/6/987)

&nbsp;

*** 

&nbsp;

[![CC BY 4.0](https://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)

This work is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/)
