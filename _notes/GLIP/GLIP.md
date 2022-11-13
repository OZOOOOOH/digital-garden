Paper: [GLIP](https://arxiv.org/pdf/2112.03857.pdf)
# key-word
#multi-modal

- [[Grounded Data]] 
- [[Data Efficiency]] 
- [[Deploy Cost]]
- [[zero-shot]]
- [[Phrase Grounding]]
- deep fusion models
---
## 한줄 요약
CLIP에 motivated 받아 [[Grounded Data]] 를 활용해 mutli-modal concept을 Object Detection Task에 적용하고, [[Deploy Cost]]를 낮추고 새로운 Detection Task에 적용해도 성능이 좋음

---
## 기존 방법론들의 한계
- Visual recognition model들은 고정된 데이터셋으로 학습되기 때문에 현실의 문제 적용과 새로운 task, domain에는 추가적인 labeled 데이터가 필요했다.
- Image-Text pair 데이터 대량 학습한 CLIP이 이러한 문제를 해결했지만, Image Classification, Text-image retrieval task에 적용 가능했다.
---
## Motivation
- Object level에 있어서 CLIP같은 모델이 필요해!

---
## Idea

 - [[Phrase Grounding]]를 object detection task와 합쳐보자
 - 
 
---
## 저자들이 집중한 점
- Grounded Data가 language-aware, sematic-rich 하다는 점을 실험 결과를 통해서 증명하고자 함.
- 적은 cost로도 novel task에도 좋은 성능을 낸다는 점을 증명
- 
---
내 생각
- multi-modal 컨셉이 detection task에 확장되고 성능도 좋다는 점이 매우 인상적이다.
- CLIP과 다르게 deep fusion model이라는 컨셉을 사용했고 성능도 좋아서 신기하다.
- multi-modal 컨셉 자체가 신기하고 왜 잘 되는지에 대해서 좀 더 공부해보고 싶다.
- 자신들의 모델이 좋다고 설득하는 과정이 굉장히 논리적이라서 인상적이다.
- 앞으로 더 다양한 task에도 multi-modal 모델들이 등장할 것이다. 