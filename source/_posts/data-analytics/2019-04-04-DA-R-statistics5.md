---
layout: post
title:  "[통계학#5] 통계적 추론 - 점추정과 구간추정"
date: 2019-04-04 23:50:59
author: Roseline Song
categories: Data-Analytics
tags: R 통계학 강의
cover: "/assets/DataAnalysis.gif"
---

※ K-Mooc 통계학 / 전공 데이터 애널리틱스 강의를 듣고 정리한 내용입니다.

<br>
<br>

### 통계적 추론 (Statistical Inferences)

통계적 추론, 추론 통계는 **샘플을 통해 모집단의 특성을 추론하는 것**을 말한다. 통계적 추론은 '추정'과 '가설 검정'의 과정으로 나뉘고 '추정'은 다시 '점 추정' 또는 '구간 추정'으로 나뉜다. 

- 통계적 추론 = 추정 + 가설검정 

- 추정 = 점추정,  구간 추정

<br>
<br>

<hr>

<br>

### 점 추정 

표본으로 얻은 정보를 이용해 모수를 특정한 하나의 값으로 추정하는 방법이다. 

모수는 $$θ$$ 라고 하고, 점 추정치는 $$\hat{θ}$$ 라고 한다. $$\hat{θ}$$은 $$X_i$$부터 $$X_n$$까지 표본들의 함수로 구성되어 있다. 이 $$X_i$$, ..., $$X_n$$는 평균, 분산 등의 통계량을 뜻한다.  따라서, 이 표본들에 따라서 $$\hat{θ}$$ 값은 달라진다. 

※ 통계량 : 모수 추정을 위해 표본을 이용해 만든 함수. IQR, 평균, 분산 등 

<br>
<br>

**불편 추정치(unbiased estimator)**

$$E(\hat{θ}) = θ$$를 만족하면 $$\hat{θ}$$은 $$θ$$에 대한 불편추정치라고 한다. 불편이라고 하는 것은 '치우치지 않음'을 뜻하는 unbiased을 직역한 것이다. $$\hat{θ}$$의 기댓값이 $$θ$$라는 것은 표본으로 통계를 내서 추론했을 때 모집단과 일치한다는 뜻이다. 즉, 모집단에서 벗어나 어느 한쪽으로 치우쳐진 게 아니므로 '불편(unbiased)'라고 한다.

<br>
<br>

**점 추정치 X의 성질**

- $$\bar{X}$$는 $$μ$$에 대한 불편추정치다. 

$$E(\bar{X}) = μ$$  

-  표본 분산 

$$Var(\bar{X}) = σ^2/n$$

- 표준 편차 (σ를 아는 경우)

$$s.d(\bar{X}) = σ/\sqrt{n}$$ 

- **표준 오차 σ를 모르는 경우**

$$s.e(\bar{X}) = s/\sqrt{n}$$ 

<br>
<br>


σ 대신 s를 쓴다(σ 대신 추정치를 썼다는 것을 표시해주는 것이다.). $$s/\sqrt{n}$$는 표본 분산에 루트를 씌워서 구한 점 추정치이다. 이 경우 표준 편차가 아니라 **표준 오차(Standard Error)**라고 부른다. 표준오차는 쉽게 생각하면, 표준편차의 추정치라고 생각하면 된다. 

<br>
<br>


**모분산 $$σ^2$$에 대한 점 추정치 $$s^2$$의 성질**

$$s^2$$은 $$σ^2$$에 대한 불편추정치이다. 

<br>
<br>

<hr>

<br>

### 구간 추정 

참값인 모수가 속할 것으로 기대되는 범위를 구하는 과정이다. 다른 말로, 구간 추정은 우리가 모르는 **모수 $$θ$$의 특정 구간을 추정**하는 것이다. 구간 추정 수식은 다음과 같이 나타낼 수 있다. 

<br>

모수 $$θ$$에 대한 $$100(1-α)% (단, 0 < α < 1)$$ 신뢰구간은 

$$P( L(\hat{θ})  <  θ  < U(\hat{θ}) ) = 1-α$$

를 만족하는 구간이다.

<br>

$$1-α$$는 **신뢰 수준**을 뜻한다. 보통 0.01, 0.05, 0.1 등의 값을 많이 가지며 이에 따라 신뢰 구간은 99%, 95%, 90% 등이 많이 쓰인다. $$L(\hat{θ})$$는 low bound(하한선)이고, $$U(\hat{θ})$$는 upper bound(상한선)을 뜻한다.

즉, 예를 들어 95%의 신뢰 구간이라는 것은 **모수 $$θ$$가 low bound와 upper bound 사이의 경계에 존재할 확률이 95%**라는 것이다. 

<br>
<br>

**대표본일 경우**

표본 함수 $$X_i$$부터 $$X_n$$은 $$E(X_1) = μ, Var(X_1) = σ^2$$인 임의 표본 $$n > 25$$인 경우, 즉 **표본의 크기 n이 25보다 큰 '대표본'**인 경우는

중심극한정리에 따라 표준정규분포 $$N(0, 1)$$에 수렴하게 된다. 이에 따라, 모평균 $$μ$$가 하한선, 상한선 사이에 있게 될 확률이 $$1-α$$이다. 

※ 중심극한정리 : 표본의 크기 n이 충분히 클 때, 표집 분포는 표준정규분포 $$N(0, 1)$$에 수렴한다. 


하지만, 주의할 것은 완전히 표준정규분포가 되는 것이 아니라 '근사적'으로 표준정규분포에 수렴하는 것이므로 신뢰 구간 $$1-α$$ 역시 '근사적 신뢰구간'을 쓰게 된다. 이 경우에는 2가지로 나뉠 수 있다. 모수 σ를 아는 경우와 모르는 경우. 이 두 경우에 대한 근사적 신뢰구간은 다음과 같다.

- σ를 아는 경우 

$$\bar{X} ± z_{α/2} \frac{σ}{\sqrt{n}} $$

- σ를 모르는 경우

$$\bar{X} ± z_{α/2} \frac{s}{\sqrt{n}} $$

※ $$s/\sqrt{n}$$는 표준오차이다.

<br>
<br>

**소표본일 경우**

표본의 크기 n이 25보다 작은 경우 '소표본'이라고 하며 대표본과는 다른 구간 추정을 한다. 이때는 임의 표본 $$X$$가 반드시 정규분포 $$N(μ, σ^2)$$을 따른다는 가정이 필요하다. 또한, $$σ$$(시그마)를 모를 경우, 표준값 z-score는 추정치 s를 대입한 

<br>

$$\bar{X} - μ \over s/\sqrt{n} $$

<br>

와 같다. 추정치 s를 대입하는 이유는 표본의 크기 n이 작기 때문이다. 


<br>
<br>
