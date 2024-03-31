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

