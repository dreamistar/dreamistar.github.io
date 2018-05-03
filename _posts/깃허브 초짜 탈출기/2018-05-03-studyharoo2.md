---
layout: posts
title: 마크다운을 공부해보자_03. LaTex 적용하기 
categories: Github초짜탈출기
use_math: true
---

# 0. Latex란? 
#### 기본적으로 Github 블로그의 Post를 쓰는 방법은 마크다운을 활용한다. 
#### 이 마크다운에서 수식을 활용할 수 있게 해주는 것이 Latex인데, Jekyll에 있는 대부분의 포스트 들이 이를 포함하고 있지 않다. 
#### 따라서 따로 이를 추가해줘야 하는데, 이번에는 이를 설명하고자 한다. 

### http://benlansdell.github.io/computing/mathjax/ 
#### 여기를 참고하였고, 사실 여기를 보고 그대로 해도 상관은 없다. 
---
# 1. _include에 파일 추가하기 
#### 우선적으로 자신의 Github 폴더 안의 `_include`에 Latex 파일을 추가해야한다. 
```
_include 폴더라는 것은 무엇일까? 
Jekyll 공식 홈페이지 설명에 따르면(http://jekyllrb-ko.github.io/docs/structure/), 
_include 폴더는 재사용하기 위한 파일을 담는 폴더이다. 
필요에 따라 여기 있는 파일들을 post나 layout에 활용할 수 있다. 
```


#### 해당 파일의 이름은 'mathjax_support'로 일반적으로 하는 듯 하다. 

---
# 2. _layout/default 수정하기
#### `_include`에 파일만 추가한다고 해서 바로 적용은 되지 않는다. 
#### 그렇기 때문에 적용하는 단계를 거쳐야 하는데, 이 과정이 바로 그 단계다. 
#### 앞에서 필요에 따라 사용하기 위한 파일들을 모아 놓는 곳이 `_include`라 했는데, 
#### Latex를 우리는 post에 적용하기 위해 사용하므로, layout에 저장할 것이다. 
#### `_layout`이라는 폴더 안 `default` 파일 안 중간을 보면, 
``` 
<head>
  ~~~~~~
  ~~~~~~
</head>
```
#### 가 보일텐데, 이 곳에 다음과 같이 코드를 넣어준다. 
```
<head>
  ~~~~~
  ~~~~~
  {% if page.use_math %}
  {% include mathjax_support.html %}
  {% endif %}
</head>
```
#### 코드를 대충 뜯어보면, use_math가 true이면,
#### 우리가 추가했던 mathjax_support.html이라는 폴더를 적용시키겠다는 것이다. 

---
# 3. post를 쓸 때 use_math 추가하기 
#### 포스트를 쓸 때 다음과 같은 설정을 하게 된다. 
```
---
layout: posts
title: 하루패드를 공부해보자_02. LaTex 적용하기 
categories: Github초짜탈출기
use_math: true
---
```
#### 이는 해당 post의 항목들을 설정해주는 것인데, 
#### 이중에서 `use_math`가 바로 우리가 원하는 수식을 넣을 수 있게 해주는 부분이다. 
#### 수식의 경우 앞뒤로 $$을 넣어주면 된다. 예를 들어, 
```
$$
(x+1)^1 + sqrl(x)
$$
```
#### 는 다음과 같이 표현된다. 
$$
(x+1)^1 + sqrl(x)
$$