# Coarse for auxiliary and fine for lead loss

<img src="Pasted image 20221127200111.png" width="50%">

- Deep supervision을 이용
  - Deep supervision의 컨셉은 모델의 중간 레이어에 추가로 auxiliary head를 추가하는 것
    - 모델에 classifier를 여러 개 두어서 성능을 올림
- Auxiliary head는 학습에 도움을 주는 역할을 하는 head를 의미
- Lead head는 final output을 예측하는 head를 의미
- GT와 모델의 예측결과를 같이 쓰고 soft label로 지정하는 것을 **label assigner**라고 말함

기존 연구에서는 lead, auxiliary head가 동시에 있는 경우 soft label을 만들 수 없었음

<img src="Pasted image 20221127213600.png" width="20%">

위 그림 처럼 Independent하게 각 head의 soft label을 만듬

본 논문에서는 lead head의 예측값에 의해서 auxiliary head와 lead head를 정하는 새로운 label assignment 방법을 제안함

<img src="Pasted image 20221127212416.png" width="20%">

---

## Lead guided assigner

- lead head의 예측과 GT 기반으로 계산 및 최적화 과정을 통해 soft label을 만든다.
- soft label은 두 head의 target으로 학습시 사용된다.
- lead head는 상대적으로 강한 학습 능력을 갖고 있어서 lead head로부터 만들어진 soft label은 source와 target 간의 더 많은 상관관계를 표현함
- auxiliary head가 lead head가 만든 정보를 바로 학습하게 하면서, lead head는 학습하지 않았던 residual 정보를 더 집중해서 학습할 수 있다.

<img src="Pasted image 20221127212433.png" width="20%">

---

## Coarse-to-fine lead head guided label assigner

마찬가지로 soft label을 만드는데 lead head의 예측값과 GT를 사용
여기서는 2개의 soft label set을 만듬

1. coarse label

   - grid를 좀 더 positive target으로 여겨지도록 해서 생성된 label
   - auxiliary head의 학습 능력이 lead head만큼 강하지 않고, 학습되어야 하는 정보의 손실 방지를 위해서 사용
   - Auxiliary head 학습에 사용

2. fine label

   - Lead guided assigner의 soft label과 동일
   - Lead head 학습에 사용

## 결과 비교

<img src="Pasted image 20221127214100.png" width="50%">
<img src="Pasted image 20221127213426.png" width="50%">
