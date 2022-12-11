1. taskA를 우선 학습한다.
2. 모델에서 데이터A를 학습하는데 중요한 Weight, 중요하지 않은 Weight를 계산한다.
3. 새로운 taskB를 학습 시 Weight의 중요도에 따라 다르게 학습한다.
 1. 중요한 Weight은 최대한 변화하지 않도록 하고,
 2. 중요하지 않은 Weight들 위주로 학습하도록 한다.

<img src="Pasted image 20221113201834.png" width="50%">

L2 Regularization을 통해 A를 학습한 Weight의 변화량을 최소화 하면서 새로운 B를 학습하면,
task A,B 모두 제대로 수렴하지 못하게 된다.
 L2는 단순히 변화량이 작아지도록 정규화하기 때문

## Loss Function

<img src="Pasted image 20221113175924.png" width="50%">

$L_B(\theta)$는 task B 를 위한 Loss.
 ex) classification task인 경우 cross entropy
$F_i$는 3가지 특징을 갖고 있다.

- loss near a minimum의 이계도함수와 동일
- 도함수만으로 값을 구할 수 있기 때문에 모델이 커도 계산이 용이 (계산량이 적다)
- positive semi-definite을 보장
- task A에 대한 Weight의 중요도 정보를 갖고 있다.

$\theta$는 현재 Weight값, $\theta_A$는 데이터A를 학습한 후의 Weight값이다.

- 이 차이가 커질수록 기존 모델로부터 변화함을 뜻하며
- 이 중 중요한 Weight들의 변화가 커질수록 Loss값이 커지도록 설계되었다.

$\lambda$는 상수 값으로 중요한 Weight값들의 변화를 regularization 하는 역할이다.

*따라서 중요한 Weight의 변화는 줄이면서 학습하겠다는 의도*

## continual learning을 해결하려는 기존의 시도

- Network의 파라미터를 조절하는 것에 집중했음
- Standard regularization method에 집중했음
- 여러 task를 sequential 하게 학습 시 한계가 있음

## Prior work 보다 EWC의 좋은 점

- EWC는 많은 task를 순차적으로 학습해도 error가 낮은 편이다.
- catastrophic forgetting을 극복
