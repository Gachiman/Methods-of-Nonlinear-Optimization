# 18. Метод дихотомии

**Методы дихотомии** используются для нахождения безусловного минимума унимодальных функций Q(x). Они являются одними из самых простых методов последовательного поиска. Название связано с тем, что каждые два испытания в два раза (или примерно в два раза) сокращают область поиска.

**Унимодальная функция** - функция называется унимодальной, если она имеет единственный локальный минимум (максимум) на всей допустимой области. Для унимодальной функции **локальный минимум (максимум) является также и глобальным**.

### Алгоритм

0. Задать δ > 0 - точность решения.
1. Положить ![](<https://latex.codecogs.com/svg.latex?c=(a+b)/2>) и ![](<https://latex.codecogs.com/svg.latex?Q_{c}=Q(c)>).
2. Пока b − a > δ выполнять шаги 2.1 и 2.2:
    2.1. Вычислить: ![](<https://latex.codecogs.com/svg.latex?x=(a+c)/2>), ![](<https://latex.codecogs.com/svg.latex?Q_{x}=Q(x)>); ![](<https://latex.codecogs.com/svg.latex?y=(c+b)/2>), ![](<https://latex.codecogs.com/svg.latex?Q_{y}=Q(y)>)
    2.2. Если ![](https://latex.codecogs.com/svg.latex?Q_{x}<Q_{c}<Q_{y}), положить b := y, c := x, ![](https://latex.codecogs.com/svg.latex?Q_{c}:=Q_{x&space;}); иначе,
если ![](https://latex.codecogs.com/svg.latex?Q_{x}>Q_{c}\leq&space;Q_{y}), то положить a := x, b := y; иначе положить
a := x, c := y, ![](https://latex.codecogs.com/svg.latex?Q_{c}:=Q_{y&space;}).
1. Завершить выполнение метода с интервальной оценкой решения
![](https://latex.codecogs.com/svg.latex?x^{*}\in&space;[a,b],&space;b&space;-a&space;\leq&space;\delta)

![](../images/ticket18-1.png)

К недостаткам метода относится его работоспособность только для одноэкстремальных функций R(x) (т.е. таких, которые содержат один экстремум того типа, который мы ищем в задаче), так как в других случаях при сравнении двух критериев в соседних точках невозможно правильно выбрать следующий интервал, где находится минимум (максимум).
