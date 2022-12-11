![[Pasted image 20221127202834.png | 700]]
## VoVNet
![[Pasted image 20221127203020.png | 300]]
- 마지막 Layer에서 모든 Channel을 Concat하자
## CSPVoVNet
![[Pasted image 20221127203335.png | 500]]
- VoVNet에 CSP 구조를 추가
- Base Layer의 feature map을 두 파트로 분할 후, 하나는 마지막에서 concat 다른하나는 DenseNet
## ELAN
- 기존 CSPVoVNet에 있던 중간에 concat 하는 과정을 생략
	- 가장 짧고 가장 긴 Gradient path간의 차이를 더 극대화 시킴
- Computational block을 특정 수준전까지 쌓아도 잘 학습되나 이를 벗어나게되면 안정성 하락
## E-ELAN
- Transition layer의 구조는 그대로, computational block의 구조만 변경
	- Group Conv 적용
	- Computational block의 Cardinality 사용
- ELAN구조를 유지하면서, 다른 그룹의 computational block이 다양한 피쳐를 학습하도록 함
