Paper: [Data Augmentation for Scene Text Recognition](https://arxiv.org/abs/2108.06949)

---

## 한줄 요약

STR 태스크에 적합한 Data Augmentation 36가지 기법을 제안

---

## 기존 방법론들의 한계

- STR모델은 실제 데이터로 평가되기 때문에 학습 데이터와 평가 데이터의 분포가 차이 나면 성능이 좋지 않음
- 기존에 객체 인식에 사용되는 Augmentation 기법은 STR에 적합하지 않음
  - CutOut, CutMix, Mixup 같은 기법은 중요 정보가 되는 글자를 없애기 때문
    - 한 영역을 없애거나 여러 이미지를 합치는 방법은 결국 글자를 없앰

---

## key-word

- STR
- Data Augmentation

---

## Motivation

1. STR태스크에 적합한 데이터셋도 없고 직접 라벨링 하는 것은 비용이 많이 듬
2. STR태스크는 보통 합성 데이터셋과 자동 어노테이션으로 생성된 데이터셋에 의존
3. 이러한 데이터셋들은 curved, noisy, distorted, blurry, under perspective transformation or rotated한 데이터에 취약했음
4. 데이터 어그멘테이션이 학습, 평가 데이터셋 간의 distribution 간극을 좁혀줄 수 있기 때문에 본 논문에서는 STR 태스크를 위한 데이터 어그멘테이션 기법을 제안
 - 각 기능은 실제 세계에서 볼 수 있는 text 이미지 특성을 따라함

---

## Real world data

- Real world에서의 Text는 다양한 환경에서 발견되고 있음
- Text 이미지는 폰트부터 모양, 크기, 색, 텍스쳐 등까지 다양한 세팅이 존재
- 이미지는 여러 환경에 영향을 받음
  - 카메라 센서 방향, 위치, 불완전성(blur, noise, geometric 왜곡 등)
- 날씨 같은 요소들이 Text 형태에 크게 영향을 미침
<img src="Pasted image 20221211143543.png" width="50%">

- 위 사진은 Real world에서 Text는 기계가 이해하기 힘들다는 것을 보여주는 사례

----

## Data Augmentation for STR

- [[Warp]]
- [[Geometry]]
- [[Pattern]]
- [[Noise]]
- [[Blur]]
- [[Weather]]
- [[Camera]]
- [[Process]]
