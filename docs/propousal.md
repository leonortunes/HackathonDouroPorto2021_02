# Proposta

A arquitectura desenvolvida integra dados meteorológicos, dados de caudalímetros, e a monitorização contínua do estado hídrico das plantas, de forma a, com recurso a modelos
previsionais, calcular automaticamente as dotações de rega óptimas. Esta plataforma poderá ser alimentada, no que diz respeito ao estado hídrico, tanto por medições feitas de
forma clássica, o que não é desejável devido às limitações já apontadas, como pelos modelos desenvolvidos no âmbito do Desafio 1, que serão integrados nesta plataforma.
Deverá também considerar as reservas de água existentes, e eventualmente, a utilização de águas provenientes da adega ou de armazenamento de águas pluviais.
Adicionalmente, a mesma poderá também receber como input dados relativos à produtividade e à qualidade, de forma a que possa também reajustar os modelos, com
recurso a machine learning, de forma a que, a médio e longo prazo, como os dados do acumular de diversas campanhas, a componente económica seja também tida em conta
na aferição das dotações de rega (i.e. se um défice hídrico severo a moderado, em determinada exploração, não se refletir em perdas de produção, as dotações de rega não
serão calculadas tendo como objectivo o conforto hídrico da planta).

Tipos de dados a considerar:
- dados meteorológicos provenientes da rede própria de EMAs
- dados meteorológicos disponibilizados pelo IPMA
- dados de humidade do solo de sondas próprias, dados de caudalímetros / temporizadores a ser obtidos junto dos associados
- históricos de dados de potencial hídrico
- históricos de dotações de rega a ser obtidos junto dos associados


[![CC BY 4.0](https://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)
