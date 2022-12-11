Object detection 모델은 Geometrical 변환에 민감하기 때문에 학습시 관련 augmentation을 적용해줌

## Augmentation

Random geometry transformation

- cropping
- expansion
- horizontal flip
- resize

---

## 2stage model 특징

- ROI기반으로 Sampling approach
- Feature map에서 region에 해당하는 부분을 반복적으로 crop
- 이러한 과정이 randomly crop하는 geometric augmentation을 대체한다고 저자들은 생각
- 본 논문 Faster-RCNN 학습 과정에서 random crop 기법은 적용하지 않음
