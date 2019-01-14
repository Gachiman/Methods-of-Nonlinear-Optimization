# 2.	Общий вид рекуррентных уравнений Беллмана


### Обозначения:
- ![](https://latex.codecogs.com/svg.latex?u_{k}) - управление
- ![](https://latex.codecogs.com/svg.latex?x_{k}) - состояние
- ![](https://latex.codecogs.com/svg.latex?f_{k}) - оператор динамической системы, позволяет по x(t) определить x(t1) для любого допустимого
момента времени t1 > t
- ![](https://latex.codecogs.com/svg.latex?Y_{k}) множество состояний, из которых (при использовании
допустимых управлений) можно ровно за k шагов попасть в одно из состояний
финального множества ![](https://latex.codecogs.com/svg.latex?X_{N}), ![](https://latex.codecogs.com/svg.latex?Y_{0})=![](https://latex.codecogs.com/svg.latex?X_{N})
- U - множество возможных значений управлений, зависящее от текущего момента времени и текущего состояния

Для решения задач динамического программирования используется
подход, разработанный в лаборатории Р. Беллмана в 50-х годах XX века

Обозначим через ![](https://latex.codecogs.com/svg.latex?S_{k}(x_{N-k})) функцию, описывающую зависимость оптимальных затрат 
от состояния ![](https://latex.codecogs.com/svg.latex?x_{N-k}) за k последних шагов, переводящих систему из состояния ![](https://latex.codecogs.com/svg.latex?x_{N-k}) в ![](https://latex.codecogs.com/svg.latex?x_{N}). Такие функции называют функциями Беллмана.

Функция оптимальных затрат ![](https://latex.codecogs.com/svg.latex?S_{1}(x_{N-k})) может
быть записана следующим образом:
- ![](https://latex.codecogs.com/svg.latex?S_{1}%28x_%7BN-k%7D%29%3Dmin%5Cleft%20%5C%7Bd_%7BN%7D%28x_%7BN-1%7D%2Cu_%7BN%7D%29%5Cright%20%5C%7D) (1.1)
Условия:
 - - ![](https://latex.codecogs.com/svg.latex?u_{N}\in&space;U_{N}(x_{N-1})) ;
  - - ![](https://latex.codecogs.com/svg.latex?f_{N}(x_{N-1},u_{N})\epsilon&space;x_{N})
  
второе ограничение необходимо для того, чтобы гарантировать
достижение заданного финального множества ![](https://latex.codecogs.com/svg.latex?x_{N})

Можно доказать, что функция оптимальных затрат ![](https://latex.codecogs.com/svg.latex?S_{k+1}(x_{N-k-1})) каждой следующей задачи 
рекуррентно выражается через предыдущую
- ![](https://latex.codecogs.com/svg.latex?S_{k}(x_{N-k})) , а именно, для ![](https://latex.codecogs.com/svg.latex?x_{N-k-1}\in&space;Y_{k+1}) :
![](https://latex.codecogs.com/svg.latex?S_%7Bk&plus;1%7D%28x_%7BN-k-1%7D%29%3Dmin%20%5Cleft%20%5C%7B%20d_%7BN-k%7D%28x_%7BN-k-1%7D%2Cu_%7BN-k%7D%29%20&plus;%20S_%7Bk%7D%28f_%7BN-k%7D%28x_%7BN-k-1%7D%2Cu_%7BN-k%7D%29%29%20%5Cright%20%5C%7D) (1.2)
Условия:
 - - ![](https://latex.codecogs.com/svg.latex?u_{N-k}\in&space;U_{N-k}(x_{N-k-1})) ;
 - - ![](https://latex.codecogs.com/svg.latex?f_{N-k}(x_{N-k-1},u_{N-k})\epsilon&space;Y_{k})

где в ограничениях последнее условие обеспечивает попадание точки  ![](https://latex.codecogs.com/svg.latex?x_{N-k}) в
область определения функции ![](https://latex.codecogs.com/svg.latex?S_{k}) .
Пусть ![](https://latex.codecogs.com/svg.latex?u_{N-k}^{*}(x_{N-k-1})) – значение управления, при котором достигается
минимум затрат в (1.2). Выражения ( 1)
![](https://latex.codecogs.com/svg.latex?u_{k}^{*}(x_{k-1}))  − определяют для каждого
момента времени оптимальные правила управления в виде функций от
текущего состояния динамического процесса, т.е. задают закон оптимального
управления в форме оптимального регулятора по состоянию.
Оптимальное начальное состояние ![](https://latex.codecogs.com/svg.latex?x_{0}^{*})  можно получить из решения
следующей задачи:
![](https://latex.codecogs.com/svg.latex?x_%7B0%7D%5E%7B*%7D%3Dargmin%5Cleft%20%5C%7B%20S_%7BN%7D%28x_%7B0%7D%3Ax_%7B0%7D%5Cin%20X_%7B0%7D%20%29%20%5Cright%20%5C%7D) (1.3)
Систему (1.1)-(1.3) называют рекуррентными уравнениями Беллмана.
Значения оптимального управления в явном виде можно последовательно
определить следующим образом: ![](https://latex.codecogs.com/svg.latex?u_{1}^{*}=u_{1}^{*}(x_{0}),&space;x_{1}^{*}=f_{1}(x_{0}^{*},u_{1}^{*}),..,u_{1}^{*}=u_{k}^{*}(x_{k-1}),&space;x_{k}^{*}=f_{k}(x_{k-1}^{*},u_{k}^{*})),
и так далее, включая ![](https://latex.codecogs.com/svg.latex?u_{N}^{*}) и ![](https://latex.codecogs.com/svg.latex?x_{N}^{*}) .

Заметим, что уравнения (1.1), (1.2) определяют следующее правило
построения управления: вне зависимости от того, каким образом управляемый
процесс на шаге k попал в состояние ![](https://latex.codecogs.com/svg.latex?x_{k}) , далее надо применять управление, оптимальное для этого состояния в завершающем (N − k)-шаговом процессе с
учетом оптимального продолжения, и в состоянии  ![](https://latex.codecogs.com/svg.latex?x_{k}) нужно применять
правило ![](https://latex.codecogs.com/svg.latex?u_{k&plus;1}^{*}(x_{k})) , определяющее первый «такт» такого управления. 
