---
layout: posts
title: Queueing Theory 1. Queueing Theory
categories: 계량경영학
tag : [queueingTheory]
use_math: true
---

# 0. Queueing Theory란 무엇인가
![queue_basic](https://postfiles.pstatic.net/MjAxODA1MDRfMjY3/MDAxNTI1NDA3ODA5Mjgy.iODbor5N_XZxiFWkbtHgNqkdxdG3hQ4PhkCJDa_F2Zkg.ETBljtM9CH3HJtqsZ78cZ1zBCeYKTL3Pq9culRtkZdsg.JPEG.dreamistar7/queue_basic.JPG?type=w1)

&nbsp;&nbsp;&nbsp;Queueing Theory는 queue를 수학적으로 다루는 학문으로 고객이 queue에 도착하고, 대기하고, 서비스를 받고 떠나는 일련의 프로세스에 대한 수학적인, 확률적인 분석을 가능하게 한다. 서비스 분야에만 활용되는 것이 아닌 여러가지 분야에 활용이 가능하다. 예를 들어 제조공장에서의 원료를 고객, 기계를 server, 제조를 서비스로 본다면 제조 공장에 또한 queueing theory를 활용할 수 있다.  

&nbsp;&nbsp;&nbsp;Queueing Theory에는 몇 가지 주요 고려대상이 있다. 
1. 고객 도착 시간(interarrival time) 사이의 평균 간격, $$\lambda$$
2. 전체 system에서 고객이 머무르는 시간의 기대값, $$W$$
3. 서비스에 걸리는 시간의 기대값, $$W-W_q$$
4. 전체 system에 있는 고객 수의 기대값, $$L$$
5. \# of Server, $$s$$
6. 서비스를 받고 떠나는 고객의 평균 수, $$\mu$$  

&nbsp;&nbsp;&nbsp;Notation에서 좀더 깊게 살펴보자 

---

# 1. Notation 

1. $$N(t)$$ : time t에 queueing system에 있는 사람의 수
  * 확정된, 특정 시간대에 있는 사람의 수.  

2. $$P_n(t)$$ : time t에 queueing system에 n명의 사람이 있을 확률
  * 확정된, 특정 시간대에 n명의 사람이 있을 확률  

3. $$s$$ : server의 수  

4. $$\lambda$$ : 단위시간 당 도착하는 고객의 평균 수 = 단위시간 당 떠나는 고객의 평균 수 
  * 고객이 서비스 중간에 죽지 않는다면 input과 output은 동일하다.  

5. $$1/\lambda$$ : 평균적으로 고객이 도착하는 시간 
  * 쉽게 생각한다면 $$\lambda$$가 $$n/t$$이므로  

5. $$\mu$$ : 단위시간 당 떠나는 고객의 평균 수 
  * 이 $$\mu$$는 단위시간 당 서비스를 받는 고객의 평균 수와 동일하다. 서비스를 받으면 바로 떠나니까.  

7. $$1/\mu$$ : 평균적으로 고객이 서비스를 받는 시간 
  * $$\lambda$$와 동일하게 생각해주면 편하다.  

8.  $$L$$ : queueing system 안에 있는 고객 수의 기대값 : $$\sum_{n=0}^{\infty}{nP_n}$$
  * 기대값임에 유의하자  

9. $$L_q$$ : 서비스를 받고 있는 고객들을 제외한, 기다리고 있는 사람(in queue / queue length) : $$\sum_{n=0}^{\infty}{(n-s)P_n}$$
  * 서비스를 받고 있는 고객 : $$L-L_q$$  

10. $$W$$ : 한 고객이 시스템 안에서 머무르는 시간의 기대값  

11. $$W_q$$ : 한 고객이 queue안에서 기다리는 시간의 기대값
  * 서비스를 받는 시간의 기대값 : $$W-W_q$$  

12. $$\rho = \lambda/s\mu$$ : 시스템 이용률 


---

# 2. Little's Law 
&nbsp;&nbsp;&nbsp;Little's Law는 위의 notation들을 활용하여 특정 공식들을 정의한 것이다. 
1. $$ L = \lambda W$$
  * 전체 system에 있는 고객의 수 = 도착하는 고객의 평균 수 * 고객이 시스템 안에 머무르는 시간의 기대값 
  * 간단하게 생각했을 때, $$\lambda$$는 n/t이고 W는 t이다.  

2. $$ L_q = \lambda W_q$$
  * queue에 있는 고객의 수 = 도착하는 고객의 평균 수 * queue에서 고객이 기다리는 시간의 기대값
  * 간단하게 생각했을 때, 동일하다.  

3. $$ W = W_q + 1/\mu $$
  * 한 고객이 시스템 안에서 머무르는 시간 = 기다리는 시간 + 서비스 받는 시간 

&nbsp;&nbsp;&nbsp;이를 다르게 표현 할 수도 있는데, 주로 공정과정에 있어서 쓰는 Notation으로 바꿔서 표현 할 수 있다. 
1. Throughput(TH) : 단위 시간당 생산되는 제품의 수량 = $$\mu$$
2. Work in Process(WIP) : 전체 system에 있는 inventory = $$L$$
3. Raw Material Inventory(RMI) : 대기중인 material
4. Cycle Time(CT) : 전체 system에 걸리는 시간 = $$W$$

&nbsp;&nbsp;&nbsp;적고 보니 너무 당연한 이야기를 수식으로 나타낸 것 같다. 










