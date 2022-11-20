Paper: [Bag of Freebies for Training Object Detection Neural Networks](https://arxiv.org/abs/1902.04103)

---
## key-word
- Bag of Freebies
	- 추론 시 추가 비용없이 성능을 올리는 effective & general한 방법
	- [[Visuallly coherent image mixup]]
	- [[Data Augmentation]]
	- [[LR scheduler]]
	- [[Synchronized Batch Normalization]]
	- 1stage model에 다양한 Input resolution
---
## 한줄 요약

Object detection Task에서 비용을 최소화 하면서 Stage 상관없이 성능을 올릴 수 있는 BoF 제안

---
## 기존 방법론들의 한계

- Stage에 따라 모델 구조도 다르고 그에 따른 데이터 전처리, 학습 파이프라인이 매우 다름
- 본 논문에서 제안하는 BoF는 Stage 상관 없고 적용 시 성능도 더 효과적임
---
## 실험
![[Pasted image 20221120161503.png | 300]]
Dataset: Pascal VOC

1Stage - Yolov3는 augmentaiton으로 약16% 성능차이를 보였고 BoF를 순차적으로 stack해서 3.43%가 더 높은 성능을 보여줌

2stage - Faster RCNN는 학습과정에서 feature map으로 crop하는 과정이 있기 때문에 augmentation해도 별 차이가 없음. 하지만 제안한 BoF를 통해 3.55% 더 높은 성능을 보여줌

### 추가 실험
![[Pasted image 20221120163612.png | 400]]
더 큰 데이터셋(MS COCO)에 대한 BoF 일반화 성능 확인을 위해서 추가 실험 진행

COCO 2017은 Pascal VOC보다 양이 10배 이상 크고, tiny한 객체들도 더 포함되어 있음

Faster-RCNN
- BoF를 적용하면서 성능을 더 올림
- 다른 Backbone에서도 적용 가능함을 보여줌
Yolov3
- BoF를 적용하면서 Faster-RCNN 성능과 비슷해짐
- 1stage 모델의 장점인 inference속도까지 유지시킴
- 다양한 input size에서도 적용 가능 (320, 416, 608)
---
## 저자들이 집중한 점
- BoF를 stack하면서 모델 성능 확인
- Mixup 검증
---
## 나의 생각

검증을 진행한 모델이 stage별로 1개씩이라 신뢰성이 높다고 생각하진 않고
2019년에 나온 논문이기 때문에 최신 모델에 적용 시 효과가 있는지 의문
대회에서 적용해볼 수 있는 것들은 Synchronized BN 제외하고 다 가능할 것 같다.