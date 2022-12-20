Model re-parameterization
- Inference단계에서 다수의 computational 모듈을 하나로 합쳐줌
- 앙상블의 일종으로 볼 수 있음
	- module-레벨
		- 학습 시 하나의 모듈을 동일하거나 다른 여러 모듈로 나누고 추론 시 나눴던 모듈들을 다시 하나의 모듈로 결합
	- model-레벨
		- 모델 구조는 동일하되 데이터를 다르게 학습 후, 학습된 모델의 가중치를 평균냄
- 모든 re-parameterized module이 다른 아키텍쳐에 완벽하게 적용될 수 없는게 문제점
- 따라서 저자는 Planned re-parameterized convolution 제안

<img src="Pasted image 20221127205414.png" width="50%">

- RepConv가 VGG에서 좋은 효과를 보였지만 ResNet, DenseNet에서 오히려 효과가 떨어짐
- RepConv의 identity connection가 ResNet의 residual & DenseNet의 concatenation을 방해하는 걸 발견
	- RepConv는 3x3 conv, 1x1 conv, identity connection 으로 구성
- ex) (d)에서 2번째 RepConv의 identity connection와 Residual connection이 중복
- 따라서 Planned re-parameterized conv 구조를 설계하기 위해서 RepConvN을 제안
	- RepConvN은 identity connection이 없는 RepConv를 의미