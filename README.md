# Atividade 1 de Laboratório Integrado I-A
## Robô em um labirinto
### Introdução ao problema
Deseja-se construir o controlador de um robô capaz de acompanhar um muro. A figura 1 ilustra o
problema, enquanto a figura 2 ilustra uma solução desenvolvida.

![Captura de tela 2024-03-31 123044](https://github.com/dutavaress/lab-robo/assets/108780767/1c591eb0-1973-4de0-919d-7182b5977799)

Na parte a) da fig. 1, o mundo do robô é uma matriz de células, na qual cada componente é livre
(células brancas) ou ocupado por um muro (células escuras). 

O robô, mostrado como um triângulo,é colocado em qualquer célula livre, respeitando uma das direções paralelas ao gradeado da matriz
(horizontal ou vertical), com sua frente voltada para qualquer um dos 4 sentidos possíveis (Norte,
Sul, Leste ou Oeste).

O robô possui 2 sensores binários: head (sensor situado na frente do robô, que
retorna 1 quando a célula situada à frente do robô está ocupada por um muro – caso contrário,
retorna 0) e left (sensor situado na lateral esquerda do robô, que retorna 1 quando a célula do lado
esquerdo do robô é ocupada por um muro - caso contrário, retorna 0).

Em relação à movimentação, o robô é capaz de fazer apenas 2 tipos de movimento: avançar para
uma célula livre à sua frente ou rotacionar 90o para a esquerda, mantendo-se na mesma célula em
que se encontra. Cada movimento consome 1 pulso de clock.

### Explicação do código feito

Este módulo de Verilog tem como objetivo descrever as movimentações e comportamentos de um robô, no qual utiliza informações sobre sua orientação ('head') e a presença de obstáculos à esquerda ('left'). Dessa forma, o robô pode girar ou avançar.

O comportamento do robô é controlado por uma máquina de estados finitos com três estados: 

1.procurandoMuro

2.rotacionando

3.acompanhandoMuro

O estado inicial é 'procurandoMuro'. Ele permanecerá nesse estado até que encontre um obstáculo à sua frente ou à sua esquerda. Caso haja a sua frente, ele mudará para o estado 'rotacionando', onde ele girará até que não haja obstáculos a sua frente ou a sua esquerda, para evitar colisões.

Caso encontre um obstáculo a esquerda, ele mudará para o estado 'acompanhandoMuro', onde seguirá o muro à sua esquerda, sempre ajustando sua direção a fim de acompanhá-lo. Caso não haja o muro à esquerda, ele retornará ao seu estado inicial 'procurandoMuro'.

As saídas 'avancar' e 'girar' são atualizadas em cada pulso de clock e são determinadas com base no estado atual e nas entradas.

Em conclusão, ressalta-se que o comportamento do robô foi definido com base em um ambiente específico, sendo necessário adaptações em caso de alteração do espaço testado.
