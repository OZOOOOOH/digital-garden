# Paper: [YOLOv7: Trainable bag-of-freebies sets new state-of-the-art for real-time object detectors](https://arxiv.org/abs/2207.02696)

## key-word

- Bag of Freebies
- RepConv
- Model scaling
- Label assignment

---

## 한줄 요약

Bag of freebies & 제안하는 방법을 이용해 실시간 Object Detecor SOTA 달성

---

## Architecture

- [[Model scaling for concatenation-based models]]
- [[E-ELAN]]

---

## Trainable bag-of-freebies

- [[Planned re-parameterized convolution]]
- [[Label assignment]]
- Batch normalization
- Implicit knowledge(학습,경험에 의한 지식) -> (YOLOR)
- EMA model

---

## 기존 방법론들의 한계

- how re-parameterized module replaces original module
- how dynamic label assignment strategy deals with assignment to different ouput layers

---

## 본 논문에서 제안하는 것

- New re-parameterization module
- 다양한 아키텍쳐를 위한 관련 application 전략 설계

---

## 실험

MS COCO 데이터 셋으로 실험 진행
모든 실험은 pretrained model을 사용하지 않고 scratch로 학습

Base Model
| GPU        | Model       |
| ---------- | ----------- |
| edge GPU   | YOLOv7-tiny |
| normal GPU | YOLOv7      |
| cloud GPU  | YOLOv7-W6   |

Base Model에 scaling을 추가

| Base Model | Method                                                 | Model                |
| ---------- | ------------------------------------------------------ | -------------------- |
| YOLOv7     | scaling on neck, compound scaling method(depth, width) | YOLOv7-X             |
| YOLOv7-W6  | compound scaling method                                | YOLOv7-E6, YOLOv7-D6 |
| YOLOv7-E6  | [[E-ELAN]]                                             | YOLOv7-E6E           |

---

## Proposed compound scaling method

제안된 compound scaling method는 computational block의 depth를 1.5배, transition block의 width를 1.25배 늘리는 것이다.

<img src="Pasted image 20221127184541.png" width="50%">

각각 width, depth만 늘린 모델과 비교했을 때 compound 방법이 더 효율적으로 성능을 끌어올린 것을 볼 수 있음

---

## 저자들이 집중한 점

- proposed planned re-parameterized model 입증
