---
layout: posts
title: Queueing Theory 0. Stochastic Process
categories: 계량경영학
tag : [queueingTheory, StochasticProcess]
use_math: true
---

# 1. 확률변수 
&nbsp;&nbsp;&nbsp;이름은 확률'변수'이지만, 확률변수는 정확히 이야기하면 함수이다. 일정한 확률로 표본공간 내 Event가 일어날 때 이에 대응하는 실수들에 대한 함수가 바로 확률변수이다. 즉, 확률변수는 Event의 표본 공간을 정의역으로 가지며, 실수를 공역으로 가지는 함수이다.  

&nbsp;&nbsp;&nbsp;해당 표본공간에서 일어나는 Event들을 잘 이해하기 위해 확률변수를 활용하게 된다. 확률변수는 일반적으로 대문자 X로 나타내며 그 구체적인 값에 대해서는 x로 나타낸다.  

&nbsp;&nbsp;&nbsp;예를 들어 주사위를 던지는 것을 생각해보자.  
&nbsp;&nbsp;&nbsp;이때 나올 수 있는 모든 주사위 눈이 나올 Event는 1, 2, 3, 4, 5, 6 이다. 또한 각 Event의 확률은 1/6으로 동일하다. 각 Event들에 주사위 눈과 동일하게 확률변수를 부여한다면, 다음과 같이 쓸 수 있다.  


$$
X(1) = x_1 = 1, P(x_1) = 1/6
$$


$$
X(2) = x_2 = 2, P(x_2) = 1/6
$$


$$
....
$$


$$
X(6) = x_6 = 6, P(x_6) = 1/6
$$


&nbsp;&nbsp;&nbsp;이는 곧 확률변수 X가 동일한 $$1/6$$의 확률로 $x_n$이라는 특정한 값을 가진다는 이야기다.  


  확률변수에는 2가지 종류가 있다. 
  1. 이산확률변수
    * 위의 주사위 예시처럼 확률변수값이 연속적이지 않고 분리되어 있는 경우
    * 셀 수 있는 경우 
  2. 연속확률변수
    * 위의 주사위 예시와는 다르게 확률변수값이 연속적인 경우 
    * 셀 수 없는 경우

&nbsp;&nbsp;&nbsp;확률변수에서 중요한 것은 결국 표본공간 내 다소 추상적인 Sample 내지 Event를 구체적인 실수로 표현한다는 것이다. 따라서 Event의 특성을 고려하여 실수로 표현하는 것이 중요하다.  


&nbsp;&nbsp;&nbsp;연속확률변수의 예로는 하루동안의 온도가 있다. 하루 동안 온도는 지속적으로 변하지만, 연속적이고 또 특정 온도에서의 확률을 구하는 것, 즉 $X(x_t)$ 가 의미가 없다. 일정기간, ${x_t < X < x_(t+1)}$ 이 의미가 있다. 

---

# 2. 누적분포함수(CDF)
&nbsp;&nbsp;&nbsp;CDF(Cumulative Distribution Function), 즉 누적분포함수는 다음과 같이 정의된다. 

$$
F_x(x) = P(X <= x)
$$

&nbsp;&nbsp;&nbsp;이는 결국 확률변수 X가 $-infty$ 부터 x까지의 값을 가질 확률들을 모두 더한 값으로, 모든 결과를 누적한 값이다.  
&nbsp;&nbsp;&nbsp;누적분포함수는 다음과 같은 성질을 가진다. 
  1. $$0 <= F_x(x) <= 1$$
  2. $$F_x(\infty) = 1$$
  3. $$F_x(-\infty) = 0 $$
  4. $$F_x(x_1) <= F_x(x_2) \ \ \ for \ \ \ x_1 < x_2 $$

&nbsp;&nbsp;&nbsp;확률을 어느정도 공부한 사람은 눈치챌 수 있겠지만, 확률밀도함수(Probability Density Function, pdf)를 흔히 $$f_x(x)$$ 로 나타내는 것과 연관되어 있는데, CDF를 미분한 함수가 바로 pdf이다. 따라서 연속함수 일때 다음을 만족한다. 

$$
P(a < X < b) = F_x(b) - F_x(a) = \int_a^b f_x(x)dx
$$

---

# 3. Stochastic Process

&nbsp;&nbsp;&nbsp;Stochastic Process(Random Process)는 위의 확률변수에 시간의 개념이 들어간 것이다. 시간이라는 차원이 들어가게되어 지금까지는 확률변수가 X로 하나밖에 없었다면, Stochastic Process에서는 시간 t마다 $X_t$ 라는 확률변수들이 따로 하나씩 주어지게 되는 것이다.  

&nbsp;&nbsp;&nbsp;좀 더 이해를 돕기 위해 예를 들자면, 흔히 많은 만화 세계관에서 이야기 하는 평행우주를 생각하면 편하다. 평행우주이론은 여러 우주가 존재하고, 내가 살고 있는 우주는 특정 우주이며, 다른 우주에는 다른 내가 존재하고 나와 다른 우주의 나는 완전히 다른 삶을 살고 있다는 것이다. 마블, DC 세계관이나 덴마를 본 사람이라면 쉽게 이해가 가능하다. ~~(그러니 우리는 덴마를 봐야한다)~~  

&nbsp;&nbsp;&nbsp;특정 시간을 하나의 우주로 생각하면 편하다. 각 우주마다, 즉 시간마다 다른 확률변수들이 존재하는 것이다. 위의 온도를 다시 예로 든다면, 오후 1시의 온도 확률변수와 새벽 1시의 온도 확률변수는 다를 수밖에 없다. 주사위의 예 또한 시간이 많이 지나 점차 모서리가 마모된 주사위라면, 동일한 확률을 가질 수 없다.  

&nbsp;&nbsp;&nbsp;특정 시간대의 랜덤프로세스는 다음과 같이 쓴다. $$X_i = X(t_i,s) = X(t_i)$$ 이는 시간 $$t_i$$ 때의 확률변수를 나타낸 것이다. 
  



